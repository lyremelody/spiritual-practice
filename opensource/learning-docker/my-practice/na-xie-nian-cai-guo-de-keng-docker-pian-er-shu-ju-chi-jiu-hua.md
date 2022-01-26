---
description: '2018-02-04'
---

# 那些年踩过的坑--Docker篇（二）数据持久化

在Docker这块踩的另一个坑 -- 使用 bind mount 方式挂载文件到 Docker 容器遇到的相关内容。

## **问题**

在使用 Docker 容器的时候，我们常常需要做一些数据持久化，比如配置、数据等。

之前遇到个**问题，“启动容器通过 -v 映射宿主机的某配置文件到容器内部，结果修改宿主机的那个配置文件，容器内部没有同步修改”**。

用个例子来描述，创建容器的方法类似：

```bash
docker run -it --name=test -v /root/test.conf:/root/test.conf test_images:1.0
```

然后通过 vi 修改宿主机配置 /root/test.conf，结果容器 test 容器内的 /root/test.conf 文件没有同步修改。

过程中还发现，这样创建的容器，有时候是正常的 \(文件同步修改\)，有时候不正常（文件不同步修改）。

难道用法不对？

显然，这样运行容器是没问题的。这是 Docker 数据存储相关的 bind mount 用法，查看 Docker 的文档，这种用法可以针对文件和目录。

那又是什么原因呢？

## **原因**

还发现一个现象，创建容器后，通过 echo 追加字符到 /root/test.conf 的时候，文件内容都是同步的。

想到 vi 默认修改文件的机制，猜测是vi导致的。vi 默认修改文件时，会临时写个.swp 文件，保存的时候会将 .swp 文件重命名覆盖原文件，导致 docker 容器的 mount 信息被破坏。

其实 Docker 的 bind mount 就是调用的系统 mount 接口。我们知道Docker采用分层文件系统，Docker 在创建容器的时候，会在镜像层文件系统上创建容器文件系统读写层。在启动容器的时候，如果有挂载信息是 bind mount 的方式，会将宿主机的文件/目录通过 bind mount的方式挂载到创建的容器文件系统中的相应路径。这些可以开启Docker 调试模式，对应日志，看看 Docker 的源码，这里不展开，后面会专门开一个专题来分享。

那么这个问题就可以简化了，跟 Docker 关系不大，我们在系统上验证 mount --bind 就好了。

## **bind mount**

mount 命令是基于系统的 mount 接口实现的，我在此就不考究了。

问题变成了把文件 test.conf 通过 mount --bind 到 test.mountpoint，用vi修改 test.conf，再看test.m 。如下

```bash
mount --bind test.conf test.mountpoint
```

创建一个实验环境，对比内容和 inode 均不同，如下：

![](https://mmbiz.qpic.cn/mmbiz_png/nibF7zl1jcldt8iaF431UjOMxv6ebFo4o3E0ZrPaC59qb6BWel0iadAa2iadSRJ8aTflbscSqRurbBe0T3kbRyV3bA/640?wx_fmt=png)

通过 bind mount 将 test.conf 挂载到 test.mountpoint，对比内容和 inode 均相同：

![](https://mmbiz.qpic.cn/mmbiz_png/nibF7zl1jcldt8iaF431UjOMxv6ebFo4o3vKbtZicEBFDqqSW35dHwdHjibIib61fSjMUZX1ib97MMDWGq5apo46JITQ/640?wx_fmt=png)

通过 vi 编辑 test.conf，看到生成中间文件，原文件\(test.conf\) inode 变化：

![](https://mmbiz.qpic.cn/mmbiz_png/nibF7zl1jcldt8iaF431UjOMxv6ebFo4o3fHpFic2Rv8zhwsiacUGeVCHP49goSYIibLP3OM9501NZqqkic3ibQIZ28aw/640?wx_fmt=png)

可以看到通过 vi 编辑后，原文件 test.conf 的 inode 变化为中间文件\(.swp\)的inode，挂载点 test.mountpoint 与 test.conf 的关系被破坏。

## **总结**

之前的那个问题：启动容器通过 -v 映射宿主机的某配置文件到容器内部，有时候修改配置后，容器内部相应文件没有同步，真正的原因是 vi \(或者某些工具\) 破坏了 bind mount 挂载信息导致。

所以这个地方，要注意的是，对于文件做 bind mount，要注意对于文件修改工具的选择，可以指定 ro 只读权限来规避；我们可以**通过目录 bind mount 的方式，将需要修改的文件放到目录中**，这样比较不容易出错。

留一个问题，如果我们通过 bind mount 目录创建容器，然后在运行过程中，有程序在宿主机删除并重新创建同名目录，是否会出问题？

不过，如果你了解了这些原理，怎么用其实也没关系了。

### **性能问题**

“bind mount 对于宿主机文件系统读写性能几乎没有损耗”，这里可以解释了。

我们再看看联系容器与宿主机的 bind mount 文件的信息

![](https://mmbiz.qpic.cn/mmbiz_png/nibF7zl1jcldt8iaF431UjOMxv6ebFo4o3LXCGdVjiarmZNLKibHuT5FKHGCukxRbHqTjfze5otamYmW2rzwVYM3Bg/640?wx_fmt=png)

由上面的内容来看，Docker 通过 bind mount 创建的卷，实际上容器内文件的 inode 与宿主机是相同的，即与宿主机上的是同一个目录/文件 \(设备\)。

之前通过 fio 测试了 iops，对比一下确实是这样，关于这部分测试，后面会再分享。

bind mount 高性能的同时，管理上却是相对比较麻烦，这是它的限制。


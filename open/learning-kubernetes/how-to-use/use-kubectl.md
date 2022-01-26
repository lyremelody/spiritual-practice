# 使用 kubectl

kubectl 作为客户端CLI工具，可以让用户通过命令行的方式对 Kubernetes 集群进行操作。

## 1 基本用法

```text
$ kubectl [command] [TYPE] [NAME] [flags]
```

### 1.1 参数说明

1. command：子命令，用于操作 Kubernetes 集群资源对象的命令，如create、delete、describe、get、apply等。
2. TYPE：资源对象的类型，区分大小写，能以单数形式、复数形式或者简写形式表示。例如以下3种TYPE是等价的：
   1. kubectl get _**pod**_ pod1
   2. kubectl get _**pods**_ pod1
   3. kubectl get _**po**_ pod1
3. NAME：资源对象的名称，区分大小写。如果不指定名称，则系统将返回属于 TYPE 的全部对象的列表，例如 “_**kubectl get pods“**_ 将返回所有 Pod 的列表。
4. flags：kubectl 子命令的可选参数，例如使用 _**“-s“**_ 指定 apiserver 的 URL 地址而不用默认值。

### 1.2 查看帮助

```text
# 获取 command/子命令 列表
$ kubectl --help

# 获取 command/子命令 用法
$ kubectl <command> --help

# 获取全局选项列表
$ kubectl options
```

## 2 使用示例

### 2.1 创建资源

#### 2.1.1 创建 Deployment

```text
$ kubectl create deployment

```

### 2.2 查看资源信息

#### 2.2.1 查看节点信息

```text
$ kubectl get nodes

```

#### 2.2.2 查看 Deployment

```text
$ kubectl get deployment

```

#### 2.2.3 查看 Pods

```text
$ kubectl get pods

```

#### 2.2.4 查看 rc 和 service

```text
$ kubectl get rc, service

```

### 2.3 描述资源信息

#### 2.3.1 显示 Node 的详细信息

```text
$ kubectl describe nodes <node-name>

```

#### 2.3.2 显示 Pod 的详细信息

```text
$ kubectl describe pods/<pod-name>

```

#### 2.3.3 显示由RC管理的 Pod 的信息

```text
$ kubectl describe pods <rc-name>
```

### 2.4 执行容器的命令

#### 2.4.1 执行 Pod 的 date 命令

默认使用 Pod 中的第1个容器执行

```text
$ kubectl exec <pod-name> date

```

####  2.4.2 指定 Pod 中某个容器执行 date 命令

```text
$ kubectl exec <pod-name> -c <container-name> date

```

#### 2.4.3 通过 bash 获得 Pod 中某个容器的 TTY \(登录容器\)

```text
$ kubectl exec -it <pod-name> -c <container-name> /bin/bash

```

### 2.5 查看日志

#### 2.5.1 查看容器输出到 stdout 的日志

```text
$ kubectl logs <pod-name>

```

#### 2.5.2 跟踪查看容器的日志 \(类似 tail -f \)

```text
$ kubectl logs -f <pod-name> -c <container-name>

```

### 2.6 删除资源对象

#### 2.6.1 基于 pod.yaml 定义的名称删除 Pod

```text
$ kubectl delete -f pod.yaml

```

#### 2.6.2 删除所有包含某个 label 的 Pod 和 service

```text
$ kubectl delete pods,services -l name=<label-name>

```

#### 2.6.3 删除所有 Pod

```text
$ kubeclt delete pods --all

```

## 3 参考资料

1. [Kubernetes权威指南](https://book.douban.com/subject/27112874/)


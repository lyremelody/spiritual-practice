---
title: '微服务代码仓库管理的选择'
linkTitle: '微服务代码仓库管理的选择'
type: 'docs'
weight: 1651
bookFlatSection: true
bookHidden: false
date: 2023-08-10T17:06:56+08:00
---

# 微服务代码仓库管理的选择

## 1 代码仓库管理有哪些方式？

### 1.1 Monolith
### 1.2 Monorepo
Monorepo 将所有源代码组织在一个层次树中。相关的项目或组件可以分组在一起，使用户更容易发现项目之间的关系。
想象三个逻辑上不同的代码库，实现：
* macOS 应用程序；
* 应用程序提供的相同功能的命令行界面；
* 和一个打包存储库，用于将应用程序和CLI捆绑到单个 .pkg 文件中进行分发。

这三个项目通常会彼此分开修改，在某些情况下，甚至可能由完全不同的团队进行修改。

#### 1.2.1 
在 Manyrepo 中，这些可能被称为 <project>-app、 <project>-cli 和 <project>。它们之间的链接必须在浏览项目列表时从共享前缀或从项目中的文档中推断出来。

如果构建项目需要引用其他两个项目的特定修订版，则每个项目都必须定义临时解决方案 (有时是git子模块，有时是通过克隆到构建目录并检查指定修订版，有时是更具创意的解决方案)。

子模块可用于实现同步多项目提交。然后只需浏览层次结构就可以发现这种关系。

```
<department/etc.>
└── <sub-team>
    └── <project>
        ├── app
        ├── build
        └── cli
```

#### 1.2.2 简化依赖
在 Monorepo 中，很容易依赖另一个项目：只需使用层次结构中不同路径的代码即可。在 Google，这种依赖关系似乎是通过在其 Blaze（公开的Bazel）BUILD 文件中编码的构建依赖关系来跟踪的。当子树的依赖项都可以从BUILD 文件中提取，并且它的所有依赖项也在树内时，就可以确定完整的调用者集并在每次更改时运行他们的测试。

这个事实很重要，所以我要重申一下：对于 Monorepo，库版本控制不再被强调。相反，库应该维护稳定的 API，并在 API 必须更改时迁移其调用者。这取决于能够在整个世界状态中进行原子提交，这在 Manyrepo 中是不可能的。这也意味着需要非常复杂的依赖性跟踪或分析，以及出色的自动化测试。

### 1.3 Manyrepo(Multirepo)
### 1.4 Metarepo

## 参考资料
1. [单体仓库与多仓库都有哪些优势劣势，如何确定微服务落地的最佳实践？，Nieml's Blog](https://ssoor.github.io/2020/03/24/mono-repo-vs-multi-repo/)
2. [单体仓库与多仓库都有哪些优势劣势，如何确定微服务落地的最佳实践？，郭强](https://goframe.org/pages/viewpage.action?pageId=87246750)
3. [Monorepo 是什么，为什么大家都在用？](https://zhuanlan.zhihu.com/p/77577415)
4. [Monorepo，wikipedia](https://zh.wikipedia.org/zh-cn/Monorepo)
5. [Monorepo vs Multi-repo vs Monolith, medium.com](https://medium.com/@magenta2127/monorepo-vs-multi-repo-vs-monolith-7c4a5f476009)
6. [Advantages of monorepos, danluu.com](https://danluu.com/monorepo/)
7. [Monorepo, Manyrepo, Metarepo](https://notes.burke.libbey.me/metarepo/)
8. [为什么Google上十亿行代码都放在同一个仓库里?，高可用架构](https://mp.weixin.qq.com/s?__biz=MzAwMDU1MTE1OQ==&mid=2653548974&idx=1&sn=ba938a6eca76d1348b9635f0d8c2eb5e&chksm=813a6036b64de92083840effea93d496457fb04dec617a0b9800760f39108f4f7e12bdf1865d&scene=0#rd)
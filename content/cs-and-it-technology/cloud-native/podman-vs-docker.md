---
title: 'Podman vs Docker，有哪些差异？'
linkTitle: 'Podman vs Docker，有哪些差异？'
type: 'docs'
weight: 1659
bookFlatSection: true
bookHidden: false
date: 2023-06-09
---

# Podman vs Docker，有哪些差异？

本文是译文，原文见文末参考资料。

容器编排工具是当今最重要的 Web 开发技术之一，许多强大的技术都在争夺行业主导地位。

Podman 是一款 Red Hat 产品，旨在使用类似 Kubernetes 的方法构建、运行和管理容器，作为主要参与者的可靠替代品，它吸引了开发人员的注意力。

我们将比较 Podman 与 Docker，后者是近十年来的标准容器化工具，因为这两种技术存在根本差异，但也非常适合协同工作。

## 什么是容器编排？
容器是独立的软件包，包括代码及其依赖项：库、工具、设置和运行时。 业界迅速采用容器作为容器化架构的核心组件，因为它们提供了更快的部署和可扩展性，并且在开发和暂存阶段统一工作。

容器轻量级、便携且安全，可提供与任何环境兼容的隔离空间。 通过将软件与操作系统分离，容器可以转移到任何位置（例如，从 Linux 到 Windows 系统），避免阻止它们工作的错误和错误。

一些最流行的编排技术是Docker、Docker Swarm、 Kubernetes 和Nomad。

## 什么是Docker？
Docker 是标准的容器管理技术。它在行业中的分量如此之大，以至于当大多数人想到容器时，他们都会想到 Docker。

Docker成为容器编排的瑞士军刀，在其他专门的替代方案可用之前包含许多功能。它必须成长为一个独立的、自给自足的工具，能够随着管理容器的复杂性增加而处理开发人员的所有需求。

它很快成为一个包含为特定任务开发的工具的一体化解决方案。一个是 Docker Swarm，这是一种原生 Docker 功能，可让你集群化和调度 Docker 引擎，另外，它是一个旨在创建和管理容器群的工具。

Docker 的附属工具处理与容器编排相关的所有任务，从负载平衡到网络，使其成为行业的首选和既定的参考技术。

但这种自给自足有其缺点。尽管它是一个强大的系统，可以在其所有开发阶段运行和创建容器，但其他工具很难与之交互。随着近年来针对特定任务的许多其他专门工具开始出现，Docker 成为许多开发人员的起点，他们将一些操作分配给其他更轻量级的平台和工具。

## 什么是Podman？
Podman是一种开源的 Linux 原生工具，旨在根据 Open Container Initiative(OCI)标准开发、管理和运行容器和 Pod。作为Red Hat开发的用户友好的容器编排器，它是 RedHat 8 和 CentOS 8 中的默认容器引擎。

它是一组命令行工具中的一个，旨在处理容器化过程的不同任务，可以作为模块化框架工作。这套包括：
* Podman - pod 和容器镜像管理器
* Buildah - 容器构建器
* Skopeo - 容器镜像检查管理器
* runc - 容器运行器和 podman 和 buildah 的功能构建器
* crun - 可选运行时，为 rootless 容器提供更大的灵活性、控制和安全性

注：rootless container 是可以由非特权用户（相对于根用户）创建、运行和管理的容器。要被视为完全rootless，容器运行时和容器都必须在没有root权限的情况下运行。

这些工具还可以与任何与 OCI 兼容的容器引擎（如 Docker）一起使用，从而可以轻松过渡到 Podman或将其与现有的 Docker 安装一起使用。Kubernetes 可以使用 Podman 吗？是的，它可以。事实上，它们在某些方面是相似的。

Podman 对容器有不同的概念方法。顾名思义，Podman 可以创建协同工作的容器“pods”，这一功能类似于 Kubernetes pods。Pod 将单独的容器组织在一个共同的名称下，以将它们作为单个单元进行管理。

主要的好处是开发人员可以共享资源，在 pod 中为同一个应用程序使用不同的容器：一个容器用于前端，另一个用于后端，还有一个数据库。Pod 定义可以导出到与 Kubernetes 兼容的 YAML 文件并应用于 Kubernetes 集群，从而使容器能够更快地进入生产环境。

Podman的另一个定义特征是它是无守护进程的。守护进程是在后台运行的程序，用于处理没有用户界面的服务、进程和请求。这是容器引擎的独特之处，因为它实际上并不依赖于守护进程，而是将容器和 Pod 作为子进程启动。

您可能会问 “我为什么要使用 Podman？” 作为开发和管理工具，它具有独特的优势，使其成为在适当情况下可行且有趣的 Docker 替代品。或者是与 Docker 并肩工作的强大补充，因为它支持与 Docker 兼容的 CLI 界面。

## Podman和Docker：差异
根据谷歌趋势，Docker 和 Podman 在过去五年中的兴趣都在波动，其中 Docker 一直更受欢迎。但眼下，这两款容器编排工具已经达到了用户兴趣的顶峰。

<div align=center><img src="./podman-vs-docker/podman-trend.png"></div>
<div align=center>Podman's interest at Google's Trends 2015 - 2023</div>
<br>
<div align=center><img src="./podman-vs-docker/docker-trend.png"></div>
<div align=center>Docker's interest at Google's Trends 2015 - 2023</div>
<br>

Podman 和 Docker 有许多共同点，但也有一些根本区别。这些并不能使一个比另一个更好，但可能是决定最适合特定项目的决定性因素。

### 架构
Docker 使用 daemon，一个在后台运行的持续程序，来创建图像和运行容器。
Podman 具有无守护程序架构，这意味着它可以在启动容器的用户下运行容器。
Docker 有一个由守护进程调解的客户端-服务器逻辑；后者不需要调解员。

### root权限
由于 Podman 没有管理其活动的守护进程，因此还为其容器分配了 root 权限。
Docker 最近在其守护进程配置中添加了rootless模式，但 Podman 首先使用了这种方法，并将其作为一项基本功能进行了推广。这是因为下一点。

### 安全
Podman 比 Docker 更安全吗？Podman 允许容器使用非root权限。rootless容器被认为比具有root权限的容器更安全。在 Docker 中，守护进程具有 root 权限，这使它们成为攻击者的首选网关。Podman 中的容器默认没有 root 访问权限，在 root 和无 root 级别之间添加了天然屏障，提高了安全性。尽管如此，它仍然可以运行 root 和无 root 容器。

### Systemd
没有守护进程，Podman 需要另一个工具来管理服务并支持在后台运行容器。Systemd 为现有容器创建控制单元或生成新容器。Systemd 还可以与 Podman 集成，允许它运行默认启用 systemd 的容器，无需任何修改。

通过使用 systemd，供应商可以将他们的应用程序作为容器安装、运行和管理，因为现在大多数应用程序都是专门以这种方式打包和交付的。

### 构建镜像
作为一个自给自足的工具，Docker 可以自己构建容器镜像。Podman 需要另一个名为 Buildah 的工具的帮助，它表达了它的专业性质：它是为运行而不是自己构建容器而设计的。

### Docker Swarm
Podman 不支持 Docker Swarm，这可能会将其排除在使用此功能的项目的选项之外，因为使用 Docker Swarm 命令会产生错误。Podman 最近添加了对 Docker Compose 的支持，使其与 Swarm 兼容，克服了这一限制。Docker 自然而然地与 Swarm 配合得很好。

### 一体化vs模块化
也许这就是这两种技术的关键区别：
* Docker 是一个整体的、强大的、独立的工具，具有所有隐含的优点和缺点，处理整个周期中的所有容器化任务。
* Podman 采用模块化方法，依靠专门的工具来完成特定任务。

## 结论
Podman 和 Docker 都是强大的容器编排工具，具有独特的优势和差异。虽然 Docker 已成为近十年的行业标准，但 Podman 的创新架构和容器管理方法使其成为开发人员的可靠替代方案，尤其是那些在 Linux 环境中工作的开发人员。

无论您选择使用一种或另一种，还是两者结合使用，了解它们的异同将有助于您根据项目需求做出最佳决策。

## 常见问题
### Podman能否取代Docker？
是的，Podman 可以在许多用例中替代 Docker。它提供与 Docker 类似的容器运行时环境和工具，并且在某些情况下，它可能提供额外的好处，例如提高安全性和灵活性。

### Podman与Docker有何不同？
Podman 与 Docker 的不同之处在于它不需要单独的守护进程来运行容器，因此更加轻量和安全。它还更好地支持以非 root 用户身份运行容器，这可以提高安全性。此外，Podman 可以在本地运行 Kubernetes pod，而无需像 Docker Compose 这样的单独工具。

### Podman比Docker更安全吗？
Podman 有时被认为比 Docker 更安全，因为它不需要单独的守护进程来运行容器，这减少了潜在安全漏洞的攻击面。它还更好地支持以非 root 用户身份运行容器，这可以提高安全性。

### Podman比docker好吗？
Podman 是否优于 Docker 取决于具体的用例和要求。有时，Podman 可能提供更好的安全性和灵活性，但 Docker 可能更适合某些环境或应用程序。评估这两个选项对于确定哪个最能满足项目的需求很重要。

## 参考资料
1. [Podman vs Docker: What are the differences?](https://www.imaginarycloud.com/blog/podman-vs-docker/)
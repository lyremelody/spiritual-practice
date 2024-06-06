---
title: 'Kubernetes核心概念'
linkTitle: 'Kubernetes核心概念'
type: 'docs'
weight: 1654
bookFlatSection: true
bookHidden: false
date: 2018-02-04
isCJKLanguage: true
params:
  author: lyremelody
---

Kubernetes 包含若干用来表示系统状态的抽象层，包括：已部署的容器化应用和负载、与它们相关的网络和磁盘资源以及有关集群正在运行的其他操作的信息。这些抽象使用 Kubernetes API 对象来表示。

## 1 基本对象

基本的 Kubernetes 对象包括：

* Pod
* Service
* Volume
* Namespace

### 1.1 Pod

Pod 是 Kubernetes 应用程序的基本执行单元，即它是 Kubernetes 对象模型中创建或部署的最小和最简单的单元。Pod 封装了应用程序容器（或者在某些情况下封装多个容器）、存储资源、唯一网络 IP 以及控制容器应该如何运行的选项。

一个 Pod 简单来说是对一组容器的抽象，它里面会包含一个或多个容器。

#### 1.1.1 为什么要设计 Pod ？

主要有两个原因：

1. 在一组容器作为一个单元的情况下，我们难以对“整体“简单地进行判断及有效地行动。比如一个容器停止了，此时算是整体停止了么？是N/M的死亡率吗？引入业务无关并且不易死亡的Pause容器作为Pod的根容器，以它的状态代表整个容器组的状态，就简单、巧妙地解决了这个问题
2. Pod里的多个业务容器共享 Pause 容器的 IP 地址，共享 Pause 容器挂载的 Volume，这样既简化了密切关联的业务容器之间的通信问题，也很好地解决了它们之间的文件共享问题

#### 1.1.2 主要用途

Kubernetes 集群中的 Pod 可被用于以下两个主要用途：

* **运行单个容器的 Pod**。”每个 Pod 一个容器”模型是最常见的 Kubernetes 用例；在这种情况下，可以将 Pod 看作单个容器的包装器，并且 Kubernetes 直接管理 Pod，而不是容器。
* **运行多个协同工作的容器的 Pod**。 Pod 可能封装由多个紧密耦合且需要共享资源的共处容器组成的应用程序。 这些位于同一位置的容器可能形成单个内聚的服务单元 —— 一个容器将文件从共享卷提供给公众，而另一个单独的 sidecar 容器则刷新或更新这些文件。 Pod 将这些容器和存储资源打包为一个可管理的实体。

每个 Pod 表示运行给定应用程序的单个实例。如果希望横向扩展应用程序（例如，运行多个实例），则应该使用多个 Pod，每个应用实例使用一个 Pod 。在 Kubernetes 中，这通常被称为「**副本」**。通常使用一个称为**控制器**的抽象来创建和管理一组副本 Pod。

用户可以通过 Kubernetes 的 Pod API 生产一个 Pod，让 Kubernetes 对这个 Pod 进行调度，也就是把它放在某一个 Kubernetes 管理的节点上运行起来。

##### 1.1.2.1 共享资源

Pod 为其组成容器提供了两种共享资源：网络和存储。

###### 1.1.2.1.1 网络

每个 Pod 分配一个唯一的 IP 地址。 Pod 中的每个容器共享网络命名空间，包括 IP 地址和网络端口。**Pod 内的容器**可以使用 `localhost` 互相通信。 当 Pod 中的容器与 **Pod 之外**的实体通信时，它们必须协调如何使用共享的网络资源（例如端口）。

###### 1.1.2.1.2 存储

一个 Pod 可以指定一组共享存储卷。 Pod 中的所有容器都可以访问共享卷，允许这些容器共享数据。 卷还允许 Pod 中的持久数据保留下来，以防其中的容器需要重新启动。

##### 1.1.2.2 例子

比如像下面的这幅图里面，它包含了两个容器，每个容器可以指定它所需要资源大小。比如说，一个核一个 G，或者说 0.5 个核，0.5 个 G。

<div align=center><img src="./images/kubernetes-core-concepts-pod-01.png"></div>

当然在这个 Pod 中也可以包含一些其他所需要的资源：比如说我们所看到的 Volume 卷这个存储资源；比如说我们需要 100 个 GB 的存储或者 20GB 的另外一个存储。

在 Pod 里面，我们也可以去定义容器所需要运行的方式。比如说运行容器的 Command，以及运行容器的环境变量等等。Pod 这个抽象也给这些容器提供了一个共享的运行环境，它们会共享同一个网络环境，这些容器可以用 localhost 来进行直接的连接。而 Pod 与 Pod 之间，是互相有 isolation 隔离的。

### 1.2 Service

Service 是将运行在一组 Pod 上的应用程序公开为网络服务的抽象方法，这里的网络服务，一般可以看作是「微服务」。

Service 提供了一个或者多个 Pod 实例的稳定访问地址。

<div align=center><img src="./images/kubernetes-core-concepts-service-01.png"></div>

一个应用可能有两个甚至更多个完全相同的 Pod。对于一个外部的用户来讲，访问哪个 Pod 其实都是一样的，所以它希望做一次负载均衡，在做负载均衡的同时，我只想访问某一个固定的 VIP，也就是 Virtual IP 地址，而不希望得知每一个具体的 Pod 的 IP 地址。

这个 pod 本身可能 terminal go（终止），如果一个 Pod 失败了，可能会换成另外一个新的。

对一个外部用户来讲，提供了多个具体的 Pod 地址，这个用户要不停地去更新 Pod 地址，当这个 Pod 再失败重启之后，我们希望有一个抽象，把所有 Pod 的访问能力抽象成一个第三方的一个 IP 地址，实现这个的 Kubernetes 的抽象就叫 Service。

实现 Service 有多种方式，Kubernetes 支持 Cluster IP，上面我们讲过的 kuber-proxy 的组网，它也支持 nodePort、 LoadBalancer 等其他的一些访问的能力。

### 1.3 Volume

Volume 就是卷的概念，它是用来管理 Kubernetes 存储的，是用来声明在 Pod 中的容器可以访问文件目录的，一个卷可以被挂载在 Pod 中一个或者多个容器的指定路径下面。

而 Volume 本身是一个抽象的概念，一个 Volume 可以去支持多种的后端的存储。比如说 Kubernetes 的 Volume 就支持了很多存储插件，它可以支持本地的存储，可以支持分布式的存储，比如说像 ceph，GlusterFS ；它也可以支持云存储，比如说阿里云上的云盘、AWS 上的云盘、Google 上的云盘等等。

### 1.4 Namespace

Namespace 是用来做一个集群内部的逻辑隔离的，它包括鉴权、资源管理等。Kubernetes 的每个资源，比如 Pod、Deployment、Service 都属于一个 Namespace，同一个 Namespace 中的资源需要命名的唯一性，不同的 Namespace 中的资源可以重名。

<div align=center><img src="./images/kubernetes-core-concepts-namespace-01.png"></div>


## 2 控制器对象

Kubernetes 也包含大量的被称作 Controller 的高级抽象。控制器基于基本对象构建并提供额外的功能和方便使用的特性。具体包括：

* Deployment
* DaemonSet
* StatefulSet
* ReplicaSet
* Job

## 3 其他
### 3.1 IP

Kubernetes 里有三种「IP」：

* Node IP：Node 节点的 IP 地址
* Pod IP：Pod 的 IP 地址
* Cluster IP：Service 的 IP 地址

#### 3.1.1 Node IP

Node IP 是 Kubernetes 集群中每个节点的物理网卡的 IP 地址，这是一个真实存在的物理网络，所有属于这个网络的服务器之间都能通过这个网络直接通信，不管它们中是否有部分节点不属于这个 Kubernetes 集群。

Kubernetes 集群之外的节点访问 Kubernetes 集群之内的某个节点或者 TCP/IP 服务时，必须要通过 Node IP 进行通信。

#### 3.1.2 Pod IP

Pod IP 是每个 Pod 的 IP 地址。它是通过 Docker Engine 根据 docker 网桥\(如docker0\) 的 IP 地址段进行分配的，通常是一个虚拟的二层网络。

Kubernetes 里一个 Pod 里的容器访问另外一个 Pod 里的容器，就是通过 Pod IP 所在的虚拟二层网络进行通信的，而真实的 TCP/IP 流量则是通过 Node IP 所在的物理网卡流出的。

#### 3.1.3 Cluster IP

Cluster IP 是 Service 的 IP 地址，它是一个虚拟的、「伪造」的 IP：

* Cluster IP 没有一个「实体网络对象」，无法被 ping 通
* Cluster IP 仅仅作用于 Kubernetes Service 这个对象，并由 Kubernetes 管理和分配 IP 地址（来源于 Cluster IP 池）
* Cluster IP 只能结合 Service Port 组成一个具体的通信端口，单独的 Cluster IP 不具备 TCP/IP 通信的基础，并且它们属于 Kubernetes 集群这样一个封闭的空间，集群之外的节点如果要访问这个通信端口，则需要做一些额外的工作
* 在 Kubernetes 集群之内，Node IP 网、Pod IP 网、Cluster IP 网之间的通信，采用的是 Kubernetes 自己设计的一种编程方式的特殊的路由规则，与我们熟知的 IP 路由有很大的不同。

Cluster IP 属于 Kubernetes 集群内部的地址，无法在集群外部直接使用这个地址。

## 4 参考资料

1. [Kubernetes官方文档 - 概念](https://kubernetes.io/zh/docs/concepts/)
2. [Kubernetes官方文档 - 概念 - Pod 概览](https://kubernetes.io/zh/docs/concepts/workloads/pods/pod-overview/)
3. [云原生技术公开课](https://edu.aliyun.com/roadmap/cloudnative)，阿里云
4. [Kubernetes权威指南](https://book.douban.com/subject/27112874/)，2017
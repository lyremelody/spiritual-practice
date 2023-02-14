# IP

Kubernetes 里有三种「IP」：

* Node IP：Node 节点的 IP 地址
* Pod IP：Pod 的 IP 地址
* Cluster IP：Service 的 IP 地址

## 1 Node IP

Node IP 是 Kubernetes 集群中每个节点的物理网卡的 IP 地址，这是一个真实存在的物理网络，所有属于这个网络的服务器之间都能通过这个网络直接通信，不管它们中是否有部分节点不属于这个 Kubernetes 集群。

Kubernetes 集群之外的节点访问 Kubernetes 集群之内的某个节点或者 TCP/IP 服务时，必须要通过 Node IP 进行通信。

## 2 Pod IP

Pod IP 是每个 Pod 的 IP 地址。它是通过 Docker Engine 根据 docker 网桥\(如docker0\) 的 IP 地址段进行分配的，通常是一个虚拟的二层网络。

Kubernetes 里一个 Pod 里的容器访问另外一个 Pod 里的容器，就是通过 Pod IP 所在的虚拟二层网络进行通信的，而真实的 TCP/IP 流量则是通过 Node IP 所在的物理网卡流出的。

## 3 Cluster IP

Cluster IP 是 Service 的 IP 地址，它是一个虚拟的、「伪造」的 IP：

* Cluster IP 没有一个「实体网络对象」，无法被 ping 通
* Cluster IP 仅仅作用于 Kubernetes Service 这个对象，并由 Kubernetes 管理和分配 IP 地址（来源于 Cluster IP 池）
* Cluster IP 只能结合 Service Port 组成一个具体的通信端口，单独的 Cluster IP 不具备 TCP/IP 通信的基础，并且它们属于 Kubernetes 集群这样一个封闭的空间，集群之外的节点如果要访问这个通信端口，则需要做一些额外的工作
* 在 Kubernetes 集群之内，Node IP 网、Pod IP 网、Cluster IP 网之间的通信，采用的是 Kubernetes 自己设计的一种编程方式的特殊的路由规则，与我们熟知的 IP 路由有很大的不同。

Cluster IP 属于 Kubernetes 集群内部的地址，无法在集群外部直接使用这个地址。

## 4 参考资料

1. [Kubernetes权威指南](https://book.douban.com/subject/27112874/)，2017


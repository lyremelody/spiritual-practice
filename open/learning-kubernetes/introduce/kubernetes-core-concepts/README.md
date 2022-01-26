# Kubernetes核心概念

Kubernetes 包含若干用来表示系统状态的抽象层，包括：已部署的容器化应用和负载、与它们相关的网络和磁盘资源以及有关集群正在运行的其他操作的信息。这些抽象使用 Kubernetes API 对象来表示。

## 1 基本对象

基本的 Kubernetes 对象包括：

* [Pod](kubernetes-core-concepts-pod.md)
* [Service](kubernetes-core-concepts-service.md)
* [Volume](kubernetes-core-concepts-volume.md)
* [Namespace](kubernetes-core-concepts-namespace.md)

## 2 控制器对象

Kubernetes 也包含大量的被称作 [Controller](kubernetes-core-concepts-controller.md) 的高级抽象。控制器基于基本对象构建并提供额外的功能和方便使用的特性。具体包括：

* [Deployment](kubernetes-core-concepts-deployment.md)
* [DaemonSet](kubernetes-core-concepts-daemonset.md)
* [StatefulSet](kubernetes-core-concepts-statefulset.md)
* [ReplicaSet](kubernetes-core-concepts-replicaset.md)
* [Job](kubernetes-core-concepts-job.md)

## 3 参考资料

1. [Kubernetes官方文档 - 概念](https://kubernetes.io/zh/docs/concepts/)




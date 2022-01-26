# Kubernetes是什么？

## 1 **Kubernetes 是什么意思? k8s?**

名称 **Kubernetes** 源于希腊语，意为 “舵手” 或 “飞行员”， 且是英文 “governor” 和 [“cybernetic”](http://www.etymonline.com/index.php?term=cybernetics)的词根。 k8s 是通过将 8 个字母 “ubernete” 替换为 8 而导出的缩写。另外，在中文里，k8s 的发音与 Kubernetes 的发音比较接近。

Kubernetes 为什么要用“舵手”来命名呢？可以看一下这张图：

![](../../../.gitbook/assets/image%20%281%29.png)

这是一艘载着一堆集装箱的轮船，轮船在大海上运着集装箱奔波，把集装箱送到它们该去的地方。 容器英文container， 这个英文单词也有另外的一个意思就是“集装箱”。Kubernetes 也就借着这个寓意，希望成为运送集装箱的一个轮船，来帮助我们管理这些集装箱，也就是管理这些容器。

上面是这个名称的由来，那么Kubernetes是什么呢？

Kubernetes 是一个跨主机集群的 [开源的容器调度平台，它可以自动化应用容器的部署、扩展和操作](http://www.slideshare.net/BrianGrant11/wso2con-us-2015-kubernetes-a-platform-for-automating-deployment-scaling-and-operations) , 提供以容器为中心的基础架构。

Kubernetes 是一个工业级的容器编排平台。

Kubernetes是Google多年大规模容器管理技术Borg的开源版本，也是CNCF最重要的项目之一，是容器编排领域的事实标准。

## 2 Kubernetes 有哪些功能？

Kubernetes 可以在物理或虚拟机集群上调度和运行应用程序容器

主要功能包括:

* 服务发现和负载均衡
* 基于容器的应用部署、维护和滚动升级
  * 自动容器恢复
  * 自动发布与回滚
  * 自动伸缩
* 存储编排、广泛的Volume支持
* 配置与密文管理
* 批量执行
* 跨机器和跨地区的集群调度
* 无状态服务和有状态服务
* 插件机制保证扩展性



## 3 参考资料

1. [Kubernetes官方文档 - Concepts - What is Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)


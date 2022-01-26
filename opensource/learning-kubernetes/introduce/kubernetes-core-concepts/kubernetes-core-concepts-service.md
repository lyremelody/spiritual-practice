# Service

Service 是将运行在一组 Pod 上的应用程序公开为网络服务的抽象方法，这里的网络服务，一般可以看作是「微服务」。

Service 提供了一个或者多个 Pod 实例的稳定访问地址。

![](../../../../.gitbook/assets/image%20%285%29.png)

一个应用可能有两个甚至更多个完全相同的 Pod。对于一个外部的用户来讲，访问哪个 Pod 其实都是一样的，所以它希望做一次负载均衡，在做负载均衡的同时，我只想访问某一个固定的 VIP，也就是 Virtual IP 地址，而不希望得知每一个具体的 Pod 的 IP 地址。

这个 pod 本身可能 terminal go（终止），如果一个 Pod 失败了，可能会换成另外一个新的。

对一个外部用户来讲，提供了多个具体的 Pod 地址，这个用户要不停地去更新 Pod 地址，当这个 Pod 再失败重启之后，我们希望有一个抽象，把所有 Pod 的访问能力抽象成一个第三方的一个 IP 地址，实现这个的 Kubernetes 的抽象就叫 Service。

实现 Service 有多种方式，Kubernetes 支持 Cluster IP，上面我们讲过的 kuber-proxy 的组网，它也支持 nodePort、 LoadBalancer 等其他的一些访问的能力。

## 参考资料

1. [云原生技术公开课](https://edu.aliyun.com/roadmap/cloudnative)，阿里云
2. [Kubernetes权威指南](https://book.douban.com/subject/27112874/)，2017




# Pod 健康检查

对 Pod 对健康检查可以通过三类探针来检查

1. LivenessProbe
2. ReadinessProbe
3. StartupProbe（kubernetes v1.16 alpha）

## 1 LivenessProbe 

LivenessProbe ，「存活探针」，用于判断容器是否存活（running状态）。

如果 LivenessProbe 探测到容器不健康，则 kubelet 将杀掉该容器，并根据容器的重启策略做相应的处理。如果一个容器不包含 LivenessProbe ，那么 kubelet 认为该容器的 LivenessProbe 返回的值永远是 “Success“。

### 1.1 实现方式

LivenessProbe 有三种实现方式：

1. ExecAction
2. TCPSocketAction
3. HTTPGetAction

#### 1.1.1 ExecAction

在容器内部执行一个命令，如果该命名的返回码为 0，则表明容器健康。

#### 1.1.2 TCPSocketAction

通过容器的 IP 地址和端口号执行 TCP 检查，如果能够建立 TCP 连接，则表明容器健康。

#### 1.1.3 HTTPGetAction

通过容器 IP 地址、端口号及路径调用 HTTP Get 方法，如果响应的状态码大于等于 200 且小于 400，则认为容器状态健康。

### 1.2 探针参数

每种实现方式，都需要设置 initialDelaySeconds 和 timeoutSeconds 两个参数：

* initialDelaySeconds：启动容器后进行首次健康检查的等待时间，单位为 s。
* timeoutSeconds：健康检查发送请求后等待响应的超时时间，单位为 s。当超时发生时，kubelet 会认为容器已经无法提供服务，将会重启该容器。

### 1.3 实践注意事项

#### 1.3.1 应该检查什么

简易的存活探针仅仅检查了服务器是否响应。

为了更好地进行存活检查，需要将探针配置为请求特定的URL路径（例如 /healthz），并让应用从内部运行的所有重要组件执行状态检查，以确保它们都没有终止或停止响应。

要确保 /healthz HTTP 端点不需要认证，否则探测会一直失败，导致容器无限重启。

一定要检查应用程序的内部，而没有任何外部因素的影响。比如，当无法连接到后端数据库时，前端 Web 服务器的存活探针不应该返回失败；因为如果问题的原因在数据库，重启 Web 服务器容器不会解决问题。

#### 1.3.2 保持探针轻量

存活探针不应该消耗太多的计算资源，并且运行不应该花太长时间。默认情况下，探测器执行的频率相对较高，必须在一秒内执行完毕。一个过重的探针会大大减慢容器的运行。

#### 1.3.3 无须在探针中实现重试循环

探针的失败阈值是可配置的，并且通常在容器终止之前，探针必须失败多次。

即使将失败阈值设置为 1 ，Kubernetes 为了确认一次探测的失败，会尝试若干次。

## 2 ReadinessProbe 

ReadinessProbe ，「就绪探针」，用于判断容器是否启动完成（ready状态），可以接收请求。

就绪探测器会周期调用，并确定特定的 Pod 是否接收客户端请求。

当容器的准备就绪探测返回成功时，表示容器已准备好接收请求。

如果就绪探针检测到失败，则 Pod 的状态将被修改。Endpoint Controller 将从 Service 的 Endpoint 中删除包含该容器所在 Pod 的 Endpoint。

「准备就绪」的概念是每个容器特有的东西，Kubernetes 只能检查在容器中运行的应用程序是否响应一个简单的 GET / 请求，或者它可以响应特定的 URL 路径。考虑到应用程序的具体情况，这种确切的准备就绪的判定是应用程序开发人员的责任。

### 2.1 实现方式

同 1.1

### 2.2 探针参数

同 1.2 

### 2.3 实践注意事项

#### 2.3.1 务必定义就绪探针

如果没有将就绪探针添加到 Pod 中，它们几乎会立即成为服务端点。如果应用程序需要很长时间才能开始监听和处理请求，那么在服务启动但尚未准备好时，客户端请求将会被转发到该 Pod ，因此，客户端会看到“连接被拒绝“类型的错误。

#### 2.3.2 不要将停止 Pod 的逻辑纳入就绪探针中

当一个容器关闭时，运行在其中的应用程序通常会在接收终止信号后立即停止接收连接。因此，可能认为只要启动关机程序，就需要让就绪探针返回失败，以确保从所有服务中删除该 Pod，类似于 Linux 系统关闭时对于服务的处理。但这不是必需的，因为只要删除该容器，Kubernetes 就会从所有服务中移除该容器。

## 3 StartupProbe

StartupProbe，「启动探针」，用于判断容器中的应用程序是否已启动。

如果提供了启动探针，则将禁用所有其他探针，直到成功。如果启动探针失败，则kubelet将杀死Container，并且Container将接受其重启策略。

如果容器未提供启动探针，则默认状态为`Success`。

## 4 一种实践

应用服务定义健康检查接口：

1. GET /health/alive
2. GET /health/ready

定义配置

```text
ports:
- name: liveness-port
  containerPort: 8080
  hostPort: 8080


readinessProbe:
  httpGet:
    path: /health/ready
    port: liveness-port
  failureThreshold: 1
  periodSeconds: 10

livenessProbe:
  httpGet:
    path: /health/alive
    port: liveness-port
  failureThreshold: 1
  periodSeconds: 10

startupProbe:
  httpGet:
    path: /health/alive
    port: liveness-port
  failureThreshold: 30
  periodSeconds: 10
```

## 5 参考资料

1. Kubernetes in Action 中文版，2019
2. [Kubernetes权威指南](https://book.douban.com/subject/27112874/)，2017




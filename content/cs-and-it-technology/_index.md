---
type: docs
title: '计算机与信息技术'
linkTitle: '计算机与信息技术'
weight: 16
bookCollapseSection: true
date: 2021-11-29
menu:
  main:
    weight: 30
    pre: <i class='fa fa-cogs'></i>
cascade:
  type: "docs"
---


## 3.技术能力(Technical Skills)
### 3.1 计算机基础(Computer Fundamentals)
#### 3.1.1 程序设计(Programming)

#### 3.1.2 数据结构(Data Structure)
* 栈和队列
* 链表
* 散列表
* 二叉搜索树
* [前缀树 Trie](./fundamentals/data-structures/trie.md)
* 红黑树
* B树
* 斐波那契堆
* 图
* 最小生成树

#### 3.1.3 基础算法(Primary Algorithms)
* 算法分析
* 分治策略
* 插入排序
* [快速排序](./fundamentals/primary-algorithms/quick-sort.md)
* [最大堆和堆排序](./fundamentals/primary-algorithms/heap-sort.md)
* 线性时间排序
  * 计数排序
  * 基数排序
  * 桶排序
* 动态规划
* 贪心算法
* 摊还分析
* 图算法
  * 广度优先搜索
  * 深度优先搜索
  * 拓扑排序
* Kruskal算法和Prim算法

#### 3.1.4 计算机系统(Computer System)
* 计算机系统概述
* 程序结构和执行
  * 信息的表示和处理
  * 程序的机器级表示
  * 处理器体系结构
  * 优化程序性能
  * 存储器层次结构
* 在系统上运行程序
  * 链接
  * 异常控制流
  * 虚拟内存
* 程序间的交互和通信
  * 系统级I/O
  * 网络编程
  * 并发编程

#### 3.1.5 操作系统(Operating System)
* 操作系统基本概念
* 系统调用
* 进程
  * 进程模型和线程
  * 进程间通信
  * 经典IPC问题
  * 进程调度
* 输入/输出系统
  * I/O硬件原理
  * I/O软件原理
  * 死锁
  * 块设备
  * RAM盘
  * 磁盘
  * 时钟
  * 终端
* 存储器原理
  * 基本内存管理
  * 交换
  * 虚拟存储器
  * 页面替换算法
  * 分页系统中的设计问题
  * 分段
* 文件系统
  * 文件和目录
  * 文件系统的实现
  * 安全性
  * 保护机制

#### 3.1.6 计算机网络(Network)
* 计算机网络概述
* 应用层
* 传输层
* 网络层：数据平面
* 网络层：控制平面
* 链路层
* 局域网
* 无线网络和移动网络
* 网络构建关键技术
  * 网络高可用设计
  * IPv4与IPv6融合组网技术
  * SDN技术
* 网络构建和设计方法
  * 网络需求分析
  * 网络技术选型和设计
  * 网络安全
  * 绿色网络设计方法

#### 3.1.7 数据库(Database)
* 数据库系统概述
* 关系数据库
  * 关系模型
  * SQL
  * 形式化关系查询语言
* 数据库设计
  * 数据库设计和E-R模型
  * 关系数据库设计
  * 应用设计和开发
* 数据存储和查询
  * 存储和文件结构
  * 索引与散列
  * 查询处理
  * 查询优化
* 事务管理
  * 事务
  * 并发控制
  * 恢复系统
* 系统体系结构
  * 数据库系统体系结构
  * 并行数据库
  * 分布式数据库
* 数据仓库与数据挖掘
* 信息检索
* 特种数据库
  * 基于对象的数据库
  * XML
* 高级应用开发
* 时空数据和移动性
* 高级事务处理

#### 3.1.8 实践和题解(Practice)
* [Leetcode](https://github.com/lyremelody/leetcode)
* [ProjectEuler](https://github.com/lyremelody/projecteuler)

### 3.2 分布式系统(Distributed System)
### 3.3 领域技术
#### 3.3.1 负载均衡
* LVS(Linux Virtual Server)
* nginx

#### 3.3.2 云技术 (Cloud Technology)
#### 3.3.3 云原生技术(Cloud Native)
##### 3.3.3.1 容器(Container)
* [Podman vs Docker，有哪些差异？](./cloud-native/podman-vs-docker.md)
* Docker
  * [那些年踩过的坑--Docker篇](./cloud-native/docker/docker-practice-20170713.md)
  * [那些年踩过的坑--Docker篇（二）数据持久化](./cloud-native/docker/docker-practice-20180204.md)
* Kubernetes
  * [Kubernetes是什么？](./cloud-native/kubernetes/what-is-kubernetes.md)
  * [Kubernetes 核心概念](./cloud-native/kubernetes/kubernetes-concepts.md)
  * [使用 kubectl](./cloud-native/kubernetes/kubernetes-use-kubectl.md)
  * [Pod 健康检查](./cloud-native/kubernetes/kubernetes-pod-health-check.md)
* Helm
  * [Helm是什么？](./cloud-native/helm/what-is-helm.md)

##### 3.3.3.2 微服务框架(Microservice Framework)

##### 3.3.3.3 服务网格(Service Mesh)

##### 3.3.3.4 分布式应用运行时(Distributed Application Runtime)
* Dapr
* Layotto

##### 3.3.3.5 资料(链接)收集
* **公司/社区资料**
  1. [CNCF，云原生计算基金会](https://www.cncf.io/)
  2. [云原生技术公开课](https://edu.aliyun.com/roadmap/cloudnative)，阿里云
* **博客/文章**
  1. [云原生已来，只是分布不均](https://mp.weixin.qq.com/s/apihIHmPwyVdZZi5d7U0Wg)，2020-06-17
  2. [云原生科普丨云原生才是「吞噬世界」的那条大鱼...](https://mp.weixin.qq.com/s?__biz=MjM5NTEwMTAwNg==&mid=2650219017&idx=1&sn=b74b0b438ad9b6883fc1298bb11ba7c4&chksm=befe22288989ab3ee981797797205053d21bfd511feb2d1169fbae9d9e24feadc1c887b79480&scene=0&xtrack=1)，2020-02-05
  3. [为何云原生在吞噬世界](http://www.sohu.com/a/353123831_465914)，2019-11-11
  4. [谷歌：云原生架构的5条原则](https://www.infoq.cn/article/B5Zk1p*8SGk5ZIVk27gv)，2019-07-08
  5. [畅谈云原生（下）：云原生的飞轮理论](https://www.infoq.cn/article/HMizcSG_FgcJKGzkE08L)，2019-03-01
  6. [畅谈云原生（上）：云原生应用应该是什么样子？](https://www.infoq.cn/article/fA42rfjV*dYGAvRANFqE)，2019-02-27
  7. [Cloud Native Application Maturity Model](https://dzone.com/articles/cloud-native-application)，2015-03-27
* **笔记**
  1. [CloudNative学习笔记](https://skyao.io/learning-cloudnative/)，skyao
* **Kubernetes资料**
  1. [深入剖析Kubernetes@极客时间](https://time.geekbang.org/column/intro/116)
  2. [云原生技术公开课](https://edu.aliyun.com/roadmap/cloudnative)，阿里云
  3. [Kubernetes指南](https://feisky.gitbooks.io/kubernetes/)，很好的中文资料
  4. [Kubernetes Handbook](https://jimmysong.io/kubernetes-handbook/)，很好的中文资料
  5. [Kubernetes中文社区](https://www.kubernetes.org.cn/)
  6. [Kubernetes Learning Path](https://azure.microsoft.com/en-us/resources/kubernetes-learning-path/)，Microsoft Azure
  7. [Kubernetes production best practices](https://learnk8s.io/production-best-practices)，learnk8s.io
  8.  [Kubernetes troubleshooting flowchart](https://learnk8s.io/troubleshooting-deployments)，learnk8s.io
* **Helm资料**
  1. [Helm 用户指南](https://whmzsu.github.io/helm-doc-zh-cn/)，中文资料
* **其他**
  1. [awesome-cloud-native](https://github.com/rootsongjc/awesome-cloud-native)
  2. [Architecting Cloud-Aware Applications Rev. 1.0](http://www.oaca-project.org/wp-content/uploads/2018/07/Architecting-Cloud-Aware-Applications-Best-Practices-Rev-1.0.pdf)，OPEN DATA CENTER ALLIANCE，PDF 


#### 3.3.4 数据库(Database)
##### 3.3.4.1 关系数据库(Relational Database)
* MySQL
* MariaDB

##### 3.3.4.2 NoSQL
* Redis
* MongoDB
* Etcd

#### 3.3.5 消息队列(Message Queue)
* [什么是消息队列？](./infrastructure/what-is-message-queue.md)
* Kafka
* NSQ
* RabbitMQ

#### 3.3.6 搜索引擎(Search Engine)
* [初识搜索引擎](./infrastructure/search-engine-20180427.md)
* Elasticsearch
  * [Elasticsearch Rally](./infrastructure/elasticsearch/elasticsearch-rally-20180123.md)
  * [Elasticsearch 热温数据迁移验证](./infrastructure/elasticsearch/elasticsearch-hot-warm-20181211.md)
* OpenSearch

#### 3.3.7 信息安全(Information Security)

#### 3.3.8 通用人工智能(Artificial General Intelligence)

### 3.4 故障排查(Troubleshooting)
* [Kubernetes Troubleshooting](./troubleshooting/kubernetes-troubleshooting.md)


### 3.5 其他技术问题(Others)
* [全球化系统中的日期时间处理问题](./others/problems/globalization-datatime.md)

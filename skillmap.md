[返回首页](./README.md)

# 知识体系梳理

<p align="left">
  <a href="https://github.com/lyremelody/architect-notes">
      <img alt="star" class="no-zoom" src="https://img.shields.io/github/stars/lyremelody/architect-notes?style=social">
  </a>
  <a href="https://github.com/lyremelody/architect-notes">
      <img alt="watch" class="no-zoom" src="https://img.shields.io/github/watchers/lyremelody/architect-notes?style=social">
  </a>
  <a href="https://github.com/lyremelody/architect-notes">
      <img alt="last-commit" class="no-zoom" src="https://img.shields.io/github/last-commit/lyremelody/architect-notes?style=social">
  </a>
</p>

TODO：缺一张图

- [知识体系梳理](#知识体系梳理)
  - [1.概念和发展史(Concepts and Timelines)](#1概念和发展史concepts-and-timelines)
    - [1.1 概念理解(Understanding Concepts)](#11-概念理解understanding-concepts)
      - [1.1.1 设计相关概念](#111-设计相关概念)
      - [1.1.2 系统能力和质量属性概念](#112-系统能力和质量属性概念)
      - [1.1.3 分布式系统概念](#113-分布式系统概念)
      - [1.1.4 其他领域概念](#114-其他领域概念)
    - [1.2 发展史(Timelines)](#12-发展史timelines)
  - [2.思想和原则(Culture and Principles)](#2思想和原则culture-and-principles)
    - [2.1 设计思想](#21-设计思想)
    - [2.2 思维误区](#22-思维误区)
    - [2.3 原则](#23-原则)
  - [3.技术能力(Technical Skills)](#3技术能力technical-skills)
    - [3.1 计算机基础(Computer Fundamentals)](#31-计算机基础computer-fundamentals)
      - [3.1.1 程序设计(Programming)](#311-程序设计programming)
      - [3.1.2 数据结构(Data Structure)](#312-数据结构data-structure)
      - [3.1.3 基础算法(Primary Algorithms)](#313-基础算法primary-algorithms)
      - [3.1.4 计算机系统(Computer System)](#314-计算机系统computer-system)
      - [3.1.5 操作系统(Operating System)](#315-操作系统operating-system)
      - [3.1.6 计算机网络(Network)](#316-计算机网络network)
      - [3.1.7 数据库(Database)](#317-数据库database)
      - [3.1.8 实践和题解(Practice)](#318-实践和题解practice)
    - [3.2 分布式系统(Distributed System)](#32-分布式系统distributed-system)
    - [3.3 领域技术](#33-领域技术)
      - [3.3.1 负载均衡](#331-负载均衡)
      - [3.3.2 云技术 (Cloud Technology)](#332-云技术-cloud-technology)
      - [3.3.3 云原生技术(Cloud Native)](#333-云原生技术cloud-native)
        - [3.3.3.1 容器(Container)](#3331-容器container)
        - [3.3.3.2 微服务框架(Microservice Framework)](#3332-微服务框架microservice-framework)
        - [3.3.3.3 服务网格(Service Mesh)](#3333-服务网格service-mesh)
        - [3.3.3.4 分布式应用运行时(Distributed Application Runtime)](#3334-分布式应用运行时distributed-application-runtime)
        - [3.3.3.5 资料(链接)收集](#3335-资料链接收集)
      - [3.3.4 数据库(Database)](#334-数据库database)
        - [3.3.4.1 关系数据库(Relational Database)](#3341-关系数据库relational-database)
        - [3.3.4.2 NoSQL](#3342-nosql)
      - [3.3.5 消息队列(Message Queue)](#335-消息队列message-queue)
      - [3.3.6 搜索引擎(Search Engine)](#336-搜索引擎search-engine)
      - [3.3.7 信息安全(Information Security)](#337-信息安全information-security)
      - [3.3.8 通用人工智能(Artificial General Intelligence)](#338-通用人工智能artificial-general-intelligence)
    - [3.4 故障排查(Troubleshooting)](#34-故障排查troubleshooting)
    - [3.5 其他技术问题(Others)](#35-其他技术问题others)
  - [4.软件工程(Software Engineering)](#4软件工程software-engineering)
    - [4.1 软件过程(Software Process)](#41-软件过程software-process)
      - [4.1.1 软件过程模型(Software Process Models)](#411-软件过程模型software-process-models)
      - [4.1.2 敏捷(Agile)](#412-敏捷agile)
    - [4.2 建模(Modeling)](#42-建模modeling)
      - [4.2.1 理解需求(Understanding Requirements)](#421-理解需求understanding-requirements)
      - [4.2.2 架构设计(Architectural Design)](#422-架构设计architectural-design)
        - [4.2.2.1 架构框架/架构方法论(Architecture Frameworks)](#4221-架构框架架构方法论architecture-frameworks)
        - [4.2.2.2 架构风格/模式(Architectural Styles/Patterns)](#4222-架构风格模式architectural-stylespatterns)
        - [4.2.2.3 架构描述(Architectural Description)](#4223-架构描述architectural-description)
        - [4.2.2.4 解决方案架构](#4224-解决方案架构)
      - [4.2.3 组件级设计(Component-level Design)](#423-组件级设计component-level-design)
        - [4.2.3.1 API设计](#4231-api设计)
          - [4.2.3.1.1 资料(链接)收集](#42311-资料链接收集)
      - [4.2.4 用户体验设计(User Experience Design)](#424-用户体验设计user-experience-design)
    - [4.3 质量与安全(Quality and Security)](#43-质量与安全quality-and-security)
      - [4.3.1 软件质量保证(Software Quality Assurance)](#431-软件质量保证software-quality-assurance)
      - [4.3.2 软件安全性工程(Software Security Engineering)](#432-软件安全性工程software-security-engineering)
      - [4.3.3 软件测试(Software Testing)](#433-软件测试software-testing)
      - [4.3.4 软件配置管理(Software Configuration Management)](#434-软件配置管理software-configuration-management)
      - [4.3.5 软件度量和分析(Software Measurement and Analytics)](#435-软件度量和分析software-measurement-and-analytics)
    - [4.4 软件项目管理(Software Project Management)](#44-软件项目管理software-project-management)
      - [4.4.1 软件计划(Software Project Plans)](#441-软件计划software-project-plans)
      - [4.4.2 风险管理(Risk Management)](#442-风险管理risk-management)
      - [4.4.3 软件支持(Software Support)](#443-软件支持software-support)
  - [5.业务与市场(Business and Market)](#5业务与市场business-and-market)
    - [5.1 Cloud Management Tooling](#51-cloud-management-tooling)
      - [5.1.1 市场分析](#511-市场分析)
      - [5.1.2 产品分析](#512-产品分析)
    - [5.2 Content Services Platform](#52-content-services-platform)
      - [5.2.1 市场分析](#521-市场分析)
      - [5.2.2 产品分析](#522-产品分析)
    - [5.3 Application Performance Monitoring and Observability](#53-application-performance-monitoring-and-observability)
      - [5.3.1 市场分析](#531-市场分析)
      - [5.3.2 产品分析](#532-产品分析)
    - [5.4 Enterprise Backup and Recovery Software Solutions](#54-enterprise-backup-and-recovery-software-solutions)
      - [5.4.1 市场分析](#541-市场分析)
      - [5.4.2 产品分析](#542-产品分析)
    - [5.5 Identity and Access Management](#55-identity-and-access-management)
      - [5.5.1 市场分析](#551-市场分析)
      - [5.5.2 产品分析](#552-产品分析)
  - [6.管理能力(Management)](#6管理能力management)
    - [6.1 目标管理(Management by Objectives)](#61-目标管理management-by-objectives)
    - [6.2 沟通管理(Communication Management)](#62-沟通管理communication-management)
    - [6.3 情绪管理(Emotion Management)](#63-情绪管理emotion-management)
    - [6.4 时间管理(Time Management)](#64-时间管理time-management)
  - [7.领导力(Leadership)](#7领导力leadership)
  - [8.学习和论文翻译(Studis and Papers)](#8学习和论文翻译studis-and-papers)
    - [8.1 Openness](#81-openness)
    - [8.2 SLA](#82-sla)
    - [8.3 多租户](#83-多租户)



## 1.概念和发展史(Concepts and Timelines)
### 1.1 概念理解(Understanding Concepts)
#### 1.1.1 设计相关概念
* [谈谈设计之「自顶向下」和「自底向上」](./concepts/talk-about-top-down-and-bottom-up.md)
* [抽象和关注点分离](./concepts/abstraction-and-suparation-of-concerns.md)
  * [Abstraction 抽象](./concepts/abstraction-and-suparation-of-concerns.md#abstraction-抽象)
  * [关注点分离](./concepts/abstraction-and-suparation-of-concerns.md#关注点分离)
    * [分而治之](./concepts/abstraction-and-suparation-of-concerns.md#分而治之)
    * [模块化](./concepts/abstraction-and-suparation-of-concerns.md#模块化)
    * [信息隐蔽](./concepts/abstraction-and-suparation-of-concerns.md#信息隐蔽)
    * [功能独立](./concepts/abstraction-and-suparation-of-concerns.md#功能独立)
    * [内聚性](./concepts/abstraction-and-suparation-of-concerns.md#内聚性)
    * [耦合性](./concepts/abstraction-and-suparation-of-concerns.md#耦合性)
    * [求精](./concepts/abstraction-and-suparation-of-concerns.md#求精)
* [TODO: 控制反转 Inversion of Control](./concepts/inversion-of-control.md)

#### 1.1.2 系统能力和质量属性概念
* [可用性 availability](./concepts/availability.md)
  * [不同领域的「Availability」](./concepts/availability.md#1-不同领域的availability)
    * [信息安全里的「Availability」](./concepts/availability.md#11-信息安全里的availability)
    * [CAP定理中的「Availability」](./concepts/availability.md#12-cap定理中的availability)
    * [软件质量模型中的「Availability」](./concepts/availability.md#13-软件质量模型中的availability)
    * [AWS 定义的(云服务)「Availability」](./concepts/availability.md#14-aws-定义的云服务availability)
  * [软件系统的可用性「Availability」](./concepts/availability.md#2-软件系统的可用性availability)
    * [什么会导致了低可用性(不可用)？](./concepts/availability.md#21-什么会导致了低可用性不可用)
      * [业界总结的服务不可用的因素](./concepts/availability.md#211-业界总结的服务不可用的因素)
      * [总结影响服务不可用的场景和因素](./concepts/availability.md#212-总结影响服务不可用的场景和因素)
      * [业界的故障分级](./concepts/availability.md#213-业界的故障分级)
    * [系统不可用的影响](./concepts/availability.md#22-系统不可用的影响)
    * [如何度量可用性？](./concepts/availability.md#23-如何度量可用性)
* [容错 fault tolerance](./concepts/fault-tolerance.md)
* [可靠性 reliability](./concepts/reliability.md)
* [可伸缩性 scalability](./concepts/scalability.md)
* [弹性 elasticity](./concepts/elasticity.md)
* [开放和开放性 Open and Openness](./concepts/open-and-openness.md)

#### 1.1.3 分布式系统概念
* [CAP/ACID/BASE](./concepts/CAP-ACID-BASE.md)
* [一致性 Consistency](./concepts/consistency.md)

#### 1.1.4 其他领域概念
* [云原生 cloud native](./concepts/what-is-cloud-native.md)
* [可观测性 Observability](./concepts/observability.md)
* [访问控制 Access Control](./concepts/access-control.md)
  * [Authentication 身份验证/认证](./concepts/access-control.md#22-authentication-身份验证认证)
  * [Authorization 授权(OAuth 2.0/SSO)](./concepts/access-control.md#23-authorization-授权)
  * [Access Control Models 访问控制模型(DAC/MAC/RBAC)](./concepts/access-control.md#24-access-control-models-访问控制模型)
  * [4A](./concepts/access-control.md#4-4a)
  * [IAM](./concepts/access-control.md#5-iam)
* [RPO/RTO](./concepts/RPO-RTO.md)
* [TODO: 软件引擎 Software Engine](./concepts/software-engine.md)
* [业务价值](./concepts/business-value.md)
* [API管理与API网关](./concepts/api-management-and-api-gateway.md)

### 1.2 发展史(Timelines)
* [计算机发展史](./timelines/computer-timeline.md)
* 操作系统发展史
* 计算机网络发展史
* [软件架构发展史](./timelines/software-architecture-timeline.md)
* [云计算发展史](./timelines/cloud-computing-timeline.md)
* [云原生发展史](./timelines/cloudnative-timeline.md)
* [DevOps起源](./timelines/devops-timeline.md)
* [Kubernetes发展史](./timelines/kubernetes-timeline.md)
* [消息队列发展史](./timelines/message-queue-timeline.md)


## 2.思想和原则(Culture and Principles)
### 2.1 设计思想
* [简约之美：软件设计之道](./culture-and-principles/code-simplicity-the-science-of-development.png)

### 2.2 思维误区
* [分布式计算的8个错误假设](./culture-and-principles/8-fallacies-of-distributed-computing.md)

### 2.3 原则
* [软件工程实践原则](./culture-and-principles/software-engineering-principles.md)
  - [软件工程整体实践原则](./culture-and-principles/software-engineering-principles.md#1-软件工程整体实践原则)
  - [核心原则-指导软件过程的原则](./culture-and-principles/software-engineering-principles.md#21-核心原则-指导软件过程的原则)
  - [核心原则-指导实践的原则](./culture-and-principles/software-engineering-principles.md#22-核心原则-指导实践的原则)
  - [指导框架活动的原则-沟通原则](./culture-and-principles/software-engineering-principles.md#31-指导框架活动的原则-沟通原则)
  - [指导框架活动的原则-策划原则](./culture-and-principles/software-engineering-principles.md#32-指导框架活动的原则-策划原则)
  - [指导框架活动的原则-建模原则](./culture-and-principles/software-engineering-principles.md#33-指导框架活动的原则-建模原则)
  - [指导框架活动的原则-构建原则](./culture-and-principles/software-engineering-principles.md#34-指导框架活动的原则-构建原则)
    - [指导框架活动的原则-构建原则-编码原则](./culture-and-principles/software-engineering-principles.md#341-指导框架活动的原则-构建原则-编码原则)
    - [指导框架活动的原则-构建原则-测试原则](./culture-and-principles/software-engineering-principles.md#342-指导框架活动的原则-构建原则-测试原则)
  - [指导框架活动的原则-部署原则](./culture-and-principles/software-engineering-principles.md#35-指导框架活动的原则-部署原则)
  - [建模-需求分析的经验原则](./culture-and-principles/software-engineering-principles.md#41-建模-需求分析的经验原则)
  - [建模-需求建模原则](./culture-and-principles/software-engineering-principles.md#42-建模-需求建模原则)
  - [建模-设计过程-质量指导原则](./culture-and-principles/software-engineering-principles.md#43-建模-设计过程-质量指导原则)
  - [建模-设计建模原则](./culture-and-principles/software-engineering-principles.md#44-建模-设计建模原则)
    - [建模-设计建模原则-基本原则](./culture-and-principles/software-engineering-principles.md#441-建模-设计建模原则-基本原则)
    - [建模-设计建模原则-架构可靠性的设计原则](./culture-and-principles/software-engineering-principles.md#442-建模-设计建模原则-架构可靠性的设计原则)
  - [建模-组件级设计-基本设计原则](./culture-and-principles/software-engineering-principles.md#45-建模-组件级设计-基本设计原则)
  - [TODO: 建模-用户体验设计-可用性准则](./culture-and-principles/software-engineering-principles.md#46-建模-用户体验设计-可用性准则)
  - [TODO: 建模-用户体验设计-可访问性准则](./culture-and-principles/software-engineering-principles.md#47-建模-用户体验设计-可访问性准则)
  - [TODO: 质量与安全-正式技术评审-评审指导原则](./culture-and-principles/software-engineering-principles.md#51-质量与安全-正式技术评审-评审指导原则)
  - [TODO: 质量与安全-移动测试准则](./culture-and-principles/software-engineering-principles.md#52-质量与安全-移动测试准则)
  - [软件项目管理原则-Boehm W5HH原则](./culture-and-principles/software-engineering-principles.md#61-软件项目管理原则-boehm-w5hh原则)
  - [TODO: 软件项目管理-项目进度安排-基本原则](./culture-and-principles/software-engineering-principles.md#62-软件项目管理-项目进度安排-基本原则)

## 3.技术能力(Technical Skills)
### 3.1 计算机基础(Computer Fundamentals)
#### 3.1.1 程序设计(Programming)

#### 3.1.2 数据结构(Data Structure)
* 栈和队列
* 链表
* 散列表
* 二叉搜索树
* [前缀树 Trie](./technology/fundamentals/data-structures/trie.md)
* 红黑树
* B树
* 斐波那契堆
* 图
* 最小生成树

#### 3.1.3 基础算法(Primary Algorithms)
* 算法分析
* 分治策略
* 插入排序
* [快速排序](./technology/fundamentals/primary-algorithms/quick-sort.md)
* [最大堆和堆排序](./technology/fundamentals/primary-algorithms/heap-sort.md)
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
* [Podman vs Docker，有哪些差异？](./technology/cloud-native/podman-vs-docker.md)
* Docker
  * [那些年踩过的坑--Docker篇](./technology/cloud-native/docker/docker-practice-20170713.md)
  * [那些年踩过的坑--Docker篇（二）数据持久化](./technology/cloud-native/docker/docker-practice-20180204.md)
* Kubernetes
  * [Kubernetes是什么？](./technology/cloud-native/kubernetes/what-is-kubernetes.md)
  * [Kubernetes 核心概念](./technology/cloud-native/kubernetes/kubernetes-concepts.md)
  * [使用 kubectl](./technology/cloud-native/kubernetes/kubernetes-use-kubectl.md)
  * [Pod 健康检查](./technology/cloud-native/kubernetes/kubernetes-pod-health-check.md)
* Helm
  * [Helm是什么？](./technology/cloud-native/helm/what-is-helm.md)

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
* [什么是消息队列？](./technology/infrastructure/what-is-message-queue.md)
* Kafka
* NSQ
* RabbitMQ

#### 3.3.6 搜索引擎(Search Engine)
* [初识搜索引擎](./technology/infrastructure/search-engine-20180427.md)
* Elasticsearch
  * [Elasticsearch Rally](./technology/infrastructure/elasticsearch/elasticsearch-rally-20180123.md)
  * [Elasticsearch 热温数据迁移验证](./technology/infrastructure/elasticsearch/elasticsearch-hot-warm-20181211.md)
* OpenSearch

#### 3.3.7 信息安全(Information Security)

#### 3.3.8 通用人工智能(Artificial General Intelligence)

### 3.4 故障排查(Troubleshooting)
* [Kubernetes Troubleshooting](./technology/troubleshooting/kubernetes-troubleshooting.md)


### 3.5 其他技术问题(Others)
* [全球化系统中的日期时间处理问题](./technology/others/problems/globalization-datatime.md)


## 4.软件工程(Software Engineering)
* [软件工程总览](./software-engineering/software-engineering.md)

### 4.1 软件过程(Software Process)
#### 4.1.1 软件过程模型(Software Process Models)
#### 4.1.2 敏捷(Agile)

### 4.2 建模(Modeling)
#### 4.2.1 理解需求(Understanding Requirements)
* [需求工程](./software-engineering/requirements/requirement-engineering.md)
* [需求建模(Requirement Modeling)](./software-engineering/requirements/requirement-modeling.md)
* [方法：事件风暴(Event Storming)](./software-engineering/requirements/event-storming.md)
* 方法：实例化需求

#### 4.2.2 架构设计(Architectural Design)
##### 4.2.2.1 架构框架/架构方法论(Architecture Frameworks)
* [ADMEMS, Architecture Design Method has been Extended to Method System](./software-engineering/design/architectural-design/architecture-frameworks/admems.md)
* TOGAF, The Open Group Architecture Framework
* DoDAF

##### 4.2.2.2 架构风格/模式(Architectural Styles/Patterns)
* [架构风格概述](./software-engineering/design/architectural-design/architectural-styles/README.md)
* [事件驱动风格(Event Driven)](./software-engineering/design/architectural-design/architectural-styles/event-driven.md)
  * 基于事件的集成风格(Event-based Integration，EBI)
  * 基于事件的集成风格也被称作隐式调用(implicit invocation)风格或者事件系统(event system)风格
* 数据流风格(Data-flow Styles)
* 管道和过滤器风格(Pipe and Filter，PF)
* 统一管道和过滤器风格(Uniform Pipe and Filter，UPF)
* 复制风格(Replication Styles)
* 复制仓库风格(Replicated Repository，RR)
* 缓存风格(Cache，$)
* 分层风格(Hierarchical Styles)
* 客户-服务器风格(Client-Server，CS)
* 分层系统风格(Layered System，LS)
* 分层-客户-服务器风格(Layered-Client-Server，LCS)
* 客户-无状态-服务器风格(Client-Stateless-Server，CSS)
* 客户-缓存-无状态-服务器风格(Client-Cache-Stateless-Server，C$SS)
* 分层-客户-缓存-无状态-服务器风格(Layered-Client-Cache-Stateless-Server，LC$SS)
* 远程会话风格(Remote Session，RS)
* 远程数据访问风格(Remote Data Access，RDA)
* 移动代码风格(Mobile Code Styles)
* 虚拟机风格(Virtual Machine，VM)
* 远程求值风格(Remote Evaluation，REV)
* 按需代码风格(Code on Demand，COD)
* 分层-按需代码-客户-缓存-无状态-服务器风格(Layered-Code-on-Demand-Client-Cache-Stateless-Server，LCODC$SS)
* 移动代理风格(Mobile Agent，MA)
* 点对点风格(Peer-to-Peer Styles)
* C2风格
* 分布式对象风格(Distributed Objects，DO)
* 被代理的分布式对象风格(Brokered Distributed Objects，BDO)
* 面向对象
* REST架构风格(表述性状态转移架构风格)
* SOA

##### 4.2.2.3 架构描述(Architectural Description)
* [架构描述概述](./software-engineering/design/architectural-design/architectural-description/README.md)
* [“4+1”视图模型](./software-engineering/design/architectural-design/architectural-description/4+1-architectural-view-model.md)
* [C4模型](./software-engineering/design/architectural-design/architectural-description/c4-model.md)
* [UML](./software-engineering/design/architectural-design/architectural-description/uml.md)
* [解决方案架构](./software-engineering/design/architectural-design/architectural-description/solution-architecture.md)
  * [解决方案架构文档模版](./software-engineering/design/architectural-design/architectural-description/solution-architecture-document.md)

##### 4.2.2.4 解决方案架构
* [高可用架构设计](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md)
  * [什么是可用性？](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#1-什么是可用性)
  * [高可用技术架构](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#5-高可用技术架构)
    * [如何梳理可用性需求或者说可用性目标？](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#51-如何梳理可用性需求或者说可用性目标)
    * [高可用技术架构目标](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#52-高可用技术架构目标)
    * [高可用架构实现机制](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#53-高可用架构实现机制)
    * [高可用方案总览](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#54-高可用方案总览)
    * [服务级高可用设计](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#55-服务级高可用设计)
    * [存储高可用设计](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#56-存储高可用设计)
    * [计算高可用设计](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#57-计算高可用设计)
    * [业务高可用设计](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-availability.md#58-业务高可用设计)
* [性能优化设计](./software-engineering/design/architectural-design/solution-architecture/architecting-for-high-performance.md)
* [RESTful API 设计](./software-engineering/design/architectural-design/solution-architecture/restful-api-design.md)
* [身份认证与授权方案设计](./software-engineering/design/architectural-design/solution-architecture/architecting-for-identity-authentication-and-authorization.md)

#### 4.2.3 组件级设计(Component-level Design)
* [组件级设计概述](./software-engineering/design/component-level-design/README.md)
* 面向对象分析与设计
* [设计模式](./software-engineering/design/component-level-design/design-patterns/)
  * 创建型模式
    * 抽象工厂模式(Abstract Factory Pattern)
    * 生成器模式(Builder Pattern)
    * 工厂方法模式(Factory Method Pattern)
    * 原型模式(Prototype Pattern)
    * 单例模式(Singleton Pattern)
  * 结构型模式
    * 适配器模式(Adapter Pattern)
    * 桥接模式(Bridge Pattern)
    * 装饰者模式(Decorator Pattern)
    * 组合模式(Composite Pattern)
    * 外观模式(Facade Pattern)
    * 享元模式(Flyweight Pattern)
    * 代理模式(Proxy Pattern)
  * 行为型模式
    * 责任链模式(Chain of Responsibility)
    * 命令模式(Command Pattern)
    * 解释器模式(Interpreter Pattern)
    * 迭代器模式(Iterator Pattern)
    * 中介者模式(Mediator Pattern)
    * 备忘录模式(Memento Pattern)
    * 观察者模式(Observer Pattern)
    * 状态模式(State Pattern)
    * 策略模式(Strategy Pattern)
    * 模版方法模式(Template Method Pattern)
    * 访问者模式(Visitor Pattern)

##### 4.2.3.1 API设计

###### 4.2.3.1.1 资料(链接)收集
* **API**
  1. [Why should you categorize your APIs? ](https://www.osaango.com/blog/why-should-you-categorize-your-apis)2018-05-13
  2. [Internal vs External APIs](https://blog.restcase.com/internal-vs-external-apis/), 2017-03-25
  3. [API Strategy 201: Private APIs vs. Open APIs](https://apiacademy.co/2015/04/api-strategy-201-private-apis-vs-open-apis/), 2015-04-09
* **论文**
  1. [《Architectural Styles and the Design of Network-based Software Architectures》](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)，Roy Fielding，2000
  2. [中文版，《架构风格与基于网络的软件架构设计》](https://www.infoq.cn/article/dissertation-rest-cn)
* **企业的设计指南**
  1. [《REST API Guidelines》](https://github.com/microsoft/api-guidelines/blob/vNext/Guidelines.md), Microsoft
  2. [《API Design Guidelines》](https://github.com/paypal/api-standards/blob/master/api-style-guide.md), PayPal
  3. [《API 设计指南》](https://cloud.google.com/apis/design/), Google
  4. [《Zalando RESTful API and Event Scheme Guidelines》](https://opensource.zalando.com/restful-api-guidelines/#), Zalando
  5. [《REST API Guidelines》](https://github.com/watson-developer-cloud/api-guidelines), IBM Wason
* **博客**
  1. [《Best Practices for Designing a Pragmatic RESTful API》](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)
  2. [《Idea REST API design》](https://betimdrenica.wordpress.com/2015/03/09/ideal-rest-api-design/)
  3. [《The Web API Checklist — 43 Things To Think About When Designing, Testing, and Releasing your API》](https://mathieu.fenniak.net/the-api-checklist/)
  4. [《Richardson Maturity Model》](https://martinfowler.com/articles/richardsonMaturityModel.html)
* **REST API文档规范**
  1. [《The OpenAPI Specification》 ](https://github.com/OAI/OpenAPI-Specification)
* **其他**
  1. [awesome-rest@GitHub](https://github.com/marmelab/awesome-rest)


#### 4.2.4 用户体验设计(User Experience Design)
* 用户体验设计元素
* 黄金规则
* 用户界面分析和设计
* 用户体验分析
* 用户体验设计
* 设计评估
* 用户界面设计模式
* 移动设计模式

### 4.3 质量与安全(Quality and Security)
* [什么是质量?](./software-engineering/software-quality/what-is-quality.md)
* [什么是软件质量?](./software-engineering/software-quality/what-is-software-quality.md)
* [实现软件质量](./software-engineering/software-quality/implement-software-quality.md)

#### 4.3.1 软件质量保证(Software Quality Assurance)

#### 4.3.2 软件安全性工程(Software Security Engineering)

#### 4.3.3 软件测试(Software Testing)
* 软件测试-组件级
* 软件测试-集成级
* 软件测试-专门的移动性测试

#### 4.3.4 软件配置管理(Software Configuration Management)
* [代码分支模型](./software-engineering/software-configuration-management/source-control-branching-model.md)
* [微服务代码仓库管理的选择](./software-engineering/software-configuration-management/source-code-repo-management.md)

#### 4.3.5 软件度量和分析(Software Measurement and Analytics)

### 4.4 软件项目管理(Software Project Management)
* 项目管理概念

#### 4.4.1 软件计划(Software Project Plans)
* 制定可行的软件计划

#### 4.4.2 风险管理(Risk Management)
#### 4.4.3 软件支持(Software Support)

## 5.业务与市场(Business and Market)
* PMF
* NPS
* STP(Segmenting、Targeting、Positioning)
* 4P(Price、Product、Place、Promotion)
* 创新的扩散
* [Market Categories, Gartner](https://www.gartner.com/reviews/markets)

### 5.1 Cloud Management Tooling
云管理工具(Cloud Management Tooling) 使组织能够管理混合云和多云（即本地、公共云和边缘）服务和资源，包括为跨多个功能领域的托管云基础设施资源提供治理、生命周期管理、代理和自动化。该工具可由中央 IT 组织（例如，I&O、云卓越中心 [CCOE] 和平台工程/运营）或在特定业务线内采购和运营，并且可以部署在客户公共场所的本地云帐户或作为SaaS服务购买。

[Cloud Management Tooling, Gartner](https://www.gartner.com/reviews/market/cloud-management-tooling)

#### 5.1.1 市场分析
#### 5.1.2 产品分析
* [Microsoft System Center 产品分析](./business-and-market/cloud-management-tooling/microsoft-system-center.md)

### 5.2 Content Services Platform
内容服务平台(CSP)是管理和利用组织内内容的基础。CSP技术使员工能够跨设备和组织边界以现代无缝方式检索和处理内容。核心CSP功能包括内容捕获、创建、合并、处理和保留，以支持个人、团队、部门和企业业务运营。

[Content Services Platform, Gartner](https://www.gartner.com/reviews/market/content-services-platforms)

#### 5.2.1 市场分析
#### 5.2.2 产品分析
* [IBM FileNet Content Manager 架构分析](./business-and-market/content-services/ibm-filenet-content-manager.md)
* [OpenText Documentum 架构分析](./business-and-market/content-services/opentext-documentum.md)

### 5.3 Application Performance Monitoring and Observability
Gartner 将应用程序性能监控和可观察性市场定义为能够观察和分析应用程序运行状况和用户体验的软件。目标角色是 IT 运营、站点可靠性工程师、云和平台运营、应用程序开发人员和产品所有者。这些解决方案可以作为供应商管理的托管环境或通过 SaaS 提供自托管部署。

[Application Performance Monitoring and Observability, Gartner](https://www.gartner.com/reviews/market/application-performance-monitoring-and-observability)

#### 5.3.1 市场分析
#### 5.3.2 产品分析

### 5.4 Enterprise Backup and Recovery Software Solutions
企业备份和恢复软件解决方案旨在捕获本地、混合、多云和 SaaS 环境中企业工作负载的时间点副本（备份），并将数据写入二级存储目标以供在丢失的情况下恢复这些数据的目的。备份和恢复解决方案具有多项核心功能。其中包括本地数据中心的操作系统、文件、数据库和应用程序的备份和恢复；公有云IaaS、PaaS、SaaS数据备份与恢复；创建多个备份副本以支持弹性、灾难恢复和其他用例；分配符合组织恢复目标的多个备份和保留策略；报告备份/恢复任务的成功和失败。

[Enterprise Backup and Recovery Software Solutions, Gartner](https://www.gartner.com/reviews/market/enterprise-backup-and-recovery-software-solutions)

#### 5.4.1 市场分析
#### 5.4.2 产品分析

### 5.5 Identity and Access Management
#### 5.5.1 市场分析
#### 5.5.2 产品分析
* Auth0
* Keycloak
* ORY
* Authing

## 6.管理能力(Management)
### 6.1 目标管理(Management by Objectives)
### 6.2 沟通管理(Communication Management)
### 6.3 情绪管理(Emotion Management)
### 6.4 时间管理(Time Management)

## 7.领导力(Leadership)

## 8.学习和论文翻译(Studis and Papers)
### 8.1 Openness
* [「Openness」开放性：一个框架及简史](./papers-reading/Openness-with-and-without-Information-Technology-a-framework-and-a-brief-history.md)
* [开放平台: How, When and Why?](./papers-reading/opening-platform-how-when-and-why.md)

### 8.2 SLA
* [一文理解「SLA/服务等级协议」](./papers-reading/about-sla.md)

### 8.3 多租户
* [Force.com 多租户互联网应用开发平台的设计](./papers-reading/translatep889-weissman-1-pdf.md)

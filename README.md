# 架构师笔记 Architect Notes

- [架构师笔记 Architect Notes](#架构师笔记-architect-notes)
  - [1.概念和发展史(Concepts and Timelines)](#1概念和发展史concepts-and-timelines)
    - [1.1 概念理解(Understanding Concepts)](#11-概念理解understanding-concepts)
    - [1.2 发展史(Timelines)](#12-发展史timelines)
  - [2.原则(Principles)](#2原则principles)
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
    - [3.2 基础设施组件(Infrastructure Components)](#32-基础设施组件infrastructure-components)
    - [3.3 其他技术问题(Others)](#33-其他技术问题others)
  - [4.软件工程(Software Engineering)](#4软件工程software-engineering)
    - [4.1 软件过程(Software Process)](#41-软件过程software-process)
    - [4.2 建模(Modeling)](#42-建模modeling)
      - [4.2.1 理解需求(Understanding Requirements)](#421-理解需求understanding-requirements)
      - [4.2.2 架构设计(Architectural Design)](#422-架构设计architectural-design)
      - [4.2.3 组件级设计(Component-level Design)](#423-组件级设计component-level-design)
    - [4.3 质量与安全(Quality and Security)](#43-质量与安全quality-and-security)
    - [4.4 软件项目管理(Software Project Management)](#44-软件项目管理software-project-management)
  - [5.业务与市场(Business and Market)](#5业务与市场business-and-market)
    - [5.1 Content Services](#51-content-services)
    - [5.2 Monitoring, Observability](#52-monitoring-observability)
  - [6.软技能(Soft-Skills)](#6软技能soft-skills)
    - [6.1 目标管理(Management by Objectives)](#61-目标管理management-by-objectives)
    - [6.2 沟通管理(Communication Management)](#62-沟通管理communication-management)
    - [6.3 情绪管理(Emotion Management)](#63-情绪管理emotion-management)
    - [6.4 时间管理(Time Management)](#64-时间管理time-management)
  - [7.学习和论文翻译(Studis and Papers)](#7学习和论文翻译studis-and-papers)


## 1.概念和发展史(Concepts and Timelines)
### 1.1 概念理解(Understanding Concepts)
* [谈谈设计之「自顶向下」和「自底向上」](./concepts/talk-about-top-down-and-bottom-up.md)
* [可用性 availability](./concepts/availability.md)
* [容错 fault tolerance](./concepts/fault-tolerance.md)
* [可靠性 reliability](./concepts/reliability.md)
* [可伸缩性 scalability](./concepts/scalability.md)
* [弹性 elasticity](./concepts/elasticity.md)
* [云原生 cloud native](./concepts/what-is-cloud-native.md)
* [可观测性 Observability](./concepts/observability.md)
* [访问控制 Access Control](./concepts/access-control.md)
* [RPO/RTO](./concepts/RPO-RTO.md)
* [CAP/ACID/BASE](./concepts/CAP-ACID-BASE.md)
* [一致性 Consistency](./concepts/consistency.md)
* [开放和开放性 Open and Openness](./concepts/open-and-openness.md)
* [抽象和关注点分离](./concepts/abstraction-and-suparation-of-concerns.md) ：模块化、信息隐蔽、功能独立、内聚性、耦合性、求精

### 1.2 发展史(Timelines)
* [云计算发展史](./timelines/cloud-computing-timeline.md)
* [云原生发展史](./timelines/cloudnative-timeline.md)
* [DevOps起源](./timelines/devops-timeline.md)
* [Kubernetes发展史](./timelines/kubernetes-timeline.md)


## 2.原则(Principles)
* [软件工程实践原则](./principles/software-engineering-principles.md)
* [分布式计算的8个错误假设](./principles/8-fallacies-of-distributed-computing.md)
* [简约之美：软件设计之道](./principles/code-simplicity-the-science-of-development.png)

## 3.技术能力(Technical Skills)
### 3.1 计算机基础(Computer Fundamentals)
#### 3.1.1 程序设计(Programming)

#### 3.1.2 数据结构(Data Structure)
* [Trie](./fundamentals/data-structures/trie.md)

#### 3.1.3 基础算法(Primary Algorithms)
* [快速排序](./fundamentals/primary-algorithms/quick-sort.md)
* [最大堆和堆排序](./fundamentals/primary-algorithms/heap-sort.md)

#### 3.1.4 计算机系统(Computer System)

#### 3.1.5 操作系统(Operating System)

#### 3.1.6 计算机网络(Network)

#### 3.1.7 数据库(Database)

#### 3.1.8 实践和题解(Practice)
* [Leetcode](https://github.com/lyremelody/leetcode)
* [ProjectEuler](https://github.com/lyremelody/projecteuler)

### 3.2 基础设施组件(Infrastructure Components)
* [Podman vs Docker，有哪些差异？](./infrastructure/podman-vs-docker.md)
* [什么是消息队列？](./infrastructure/what-is-message-queue.md)
* 搜索引擎
  * [初识搜索引擎](./infrastructure/search-engine-20180427.md)
* Docker
  * [那些年踩过的坑--Docker篇](./infrastructure/docker/docker-practice-20170713.md)
  * [那些年踩过的坑--Docker篇（二）数据持久化](./infrastructure/docker/docker-practice-20180204.md)
* Kubernetes
  * [Kubernetes是什么？](./infrastructure/kubernetes/what-is-kubernetes.md)
  * [Kubernetes 核心概念](./infrastructure/kubernetes/kubernetes-concepts.md)
  * [使用 kubectl](./infrastructure/kubernetes/kubernetes-use-kubectl.md)
  * [Pod 健康检查](./infrastructure/kubernetes/kubernetes-pod-health-check.md)
* Helm
  * [Helm是什么？](./infrastructure/helm/what-is-helm.md)
* Elasticsearch
  * [Elasticsearch Rally](./infrastructure/elasticsearch/elasticsearch-rally-20180123.md)
  * [Elasticsearch 热温数据迁移验证](./infrastructure/elasticsearch/elasticsearch-hot-warm-20181211.md)
* Redis
* MongoDB

### 3.3 其他技术问题(Others)
* Troubleshooting 故障排查
  * [Kubernetes Troubleshooting](./others/troubleshooting/kubernetes-troubleshooting.md)
* [全球化系统中的日期时间处理问题](./others/problems/globalization-datatime.md)


## 4.软件工程(Software Engineering)
* [软件工程总览](./software-engineering/software-engineering.md)

### 4.1 软件过程(Software Process)

### 4.2 建模(Modeling)

#### 4.2.1 理解需求(Understanding Requirements)
* [需求工程](./software-engineering/requirements/requirement-engineering.md)
* [需求建模(Requirement Modeling)](./software-engineering/requirements/requirement-modeling.md)
* [方法：事件风暴(Event Storming)](./software-engineering/requirements/event-storming.md)

#### 4.2.2 架构设计(Architectural Design)
* [架构概念总览](./software-engineering/design/architecture-design/architecture.md)
* [架构风格](./software-engineering/design/architecture-design/architecture-styles/)
* [架构描述](./software-engineering/design/architecture-design/architecture-description/)
  * [“4+1”视图模型](./software-engineering/design/architecture-design/architecture-description/4+1-architectural-view-model.md)
  * [C4模型](./software-engineering/design/architecture-design/architecture-description/c4-model.md)
  * [UML](./software-engineering/design/architecture-design/architecture-description/uml.md)
  * [解决方案架构](./software-engineering/design/architecture-design/architecture-description/solution-architecture.md)
    * [解决方案架构文档模版](./software-engineering/design/architecture-design/architecture-description/solution-architecture-document.md)
* [企业架构框架](./software-engineering/design/architecture-design/enterprise-architecture-frameworks/)
* [解决方案架构设计](./software-engineering/design/architecture-design/solution-architecture)
  * [高可用架构设计](./software-engineering/design/architecture-design/solution-architecture/architecting-for-high-availability.md)
  * [高性能架构设计](./software-engineering/design/architecture-design/solution-architecture/architecting-for-high-performance.md)
  * [RESTful API 设计](./software-engineering/design/architecture-design/solution-architecture/restful-api-design.md)

#### 4.2.3 组件级设计(Component-level Design)
* [设计模式](./software-engineering/design/component-level-design/design-patterns/)

### 4.3 质量与安全(Quality and Security)
* [什么是质量](./software-engineering/software-quality/what-is-quality.md)
* [什么是软件质量](./software-engineering/software-quality/what-is-software-quality.md)
* [实现软件质量](./software-engineering/software-quality/implement-software-quality.md)

### 4.4 软件项目管理(Software Project Management)


## 5.业务与市场(Business and Market)
### 5.1 Content Services
### 5.2 Monitoring, Observability


## 6.软技能(Soft-Skills)
### 6.1 目标管理(Management by Objectives)
### 6.2 沟通管理(Communication Management)
### 6.3 情绪管理(Emotion Management)
### 6.4 时间管理(Time Management)

## 7.学习和论文翻译(Studis and Papers)
* [学习资料](./info-list.md)
* Openness
  * [「Openness」开放性：一个框架及简史](./papers-reading/Openness-with-and-without-Information-Technology-a-framework-and-a-brief-history.md)
  * [开放平台: How, When and Why?](./papers-reading/opening-platform-how-when-and-why.md)
* SLA
  * [一文理解「SLA/服务等级协议」](./papers-reading/about-sla.md)
* 多租户
  * [Force.com 多租户互联网应用开发平台的设计](./papers-reading/translatep889-weissman-1-pdf.md)

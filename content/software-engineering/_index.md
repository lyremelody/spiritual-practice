---
type: docs
title: "软件工程"
linkTitle: "软件工程"
weight: 17
bookCollapseSection: true
date: 2021-11-29
menu:
  main:
    weight: 30
    pre: <i class='fa fa-cogs'></i>
cascade:
  type: "docs"
isCJKLanguage: true
params:
  author: lyremelody
---

* [软件工程总览](./software-engineering.md)

### 4.1 软件过程(Software Process)
#### 4.1.1 软件过程模型(Software Process Models)
#### 4.1.2 敏捷(Agile)

### 4.2 建模(Modeling)
#### 4.2.1 理解需求(Understanding Requirements)
* [需求工程](./modeling/requirements/requirement-engineering.md)
* [需求建模(Requirement Modeling)](./modeling/requirements/requirement-modeling.md)
* [方法：事件风暴(Event Storming)](./modeling/requirements/event-storming.md)
* 方法：实例化需求

#### 4.2.2 架构设计(Architectural Design)
##### 4.2.2.1 架构框架/架构方法论(Architecture Frameworks)
* [ADMEMS, Architecture Design Method has been Extended to Method System](./modeling/architectural-design/architecture-frameworks/admems.md)
* TOGAF, The Open Group Architecture Framework
* DoDAF

##### 4.2.2.2 架构风格/模式(Architectural Styles/Patterns)
* [架构风格概述](./modeling/architectural-design/architectural-styles/README.md)
* [事件驱动风格(Event Driven)](./modeling/architectural-design/architectural-styles/event-driven.md)
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
* [“4+1”视图模型](./modeling/architectural-design/architectural-description/4+1-architectural-view-model.md)
* [C4模型](./modeling/architectural-design/architectural-description/c4-model.md)
* [UML](./modeling/architectural-design/architectural-description/uml.md)
* [解决方案架构](./modeling/architectural-design/architectural-description/solution-architecture.md)
  * [解决方案架构文档模版](./modeling/architectural-design/architectural-description/solution-architecture-document.md)

##### 4.2.2.4 解决方案架构
* [高可用架构设计](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md)
  * [什么是可用性？](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#1-什么是可用性)
  * [高可用技术架构](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#5-高可用技术架构)
    * [如何梳理可用性需求或者说可用性目标？](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#51-如何梳理可用性需求或者说可用性目标)
    * [高可用技术架构目标](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#52-高可用技术架构目标)
    * [高可用架构实现机制](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#53-高可用架构实现机制)
    * [高可用方案总览](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#54-高可用方案总览)
    * [服务级高可用设计](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#55-服务级高可用设计)
    * [存储高可用设计](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#56-存储高可用设计)
    * [计算高可用设计](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#57-计算高可用设计)
    * [业务高可用设计](./modeling/architectural-design/solution-architecture/architecting-for-high-availability.md#58-业务高可用设计)
* [性能优化设计](./modeling/architectural-design/solution-architecture/architecting-for-high-performance.md)
* [RESTful API 设计](./modeling/architectural-design/solution-architecture/restful-api-design.md)
* [身份认证与授权方案设计](./modeling/architectural-design/solution-architecture/architecting-for-identity-authentication-and-authorization.md)

#### 4.2.3 组件级设计(Component-level Design)
* [组件级设计概述](./modeling/component-level-design/README.md)
* 面向对象分析与设计
* [设计模式](./modeling/component-level-design/design-patterns/)
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
* [什么是质量?](./software-quality/what-is-quality.md)
* [什么是软件质量?](./software-quality/what-is-software-quality.md)
* [实现软件质量](./software-quality/implement-software-quality.md)

#### 4.3.1 软件质量保证(Software Quality Assurance)

#### 4.3.2 软件安全性工程(Software Security Engineering)

#### 4.3.3 软件测试(Software Testing)
* 软件测试-组件级
* 软件测试-集成级
* 软件测试-专门的移动性测试

#### 4.3.4 软件配置管理(Software Configuration Management)
* [代码分支模型](./software-quality/software-configuration-management/source-control-branching-model.md)
* [微服务代码仓库管理的选择](./software-quality/software-configuration-management/source-code-repo-management.md)

#### 4.3.5 软件度量和分析(Software Measurement and Analytics)

### 4.4 软件项目管理(Software Project Management)
* 项目管理概念

#### 4.4.1 软件计划(Software Project Plans)
* 制定可行的软件计划

#### 4.4.2 风险管理(Risk Management)
#### 4.4.3 软件支持(Software Support)

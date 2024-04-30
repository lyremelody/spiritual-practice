---
title: '云原生是什么？'
linkTitle: '云原生是什么？'
type: 'docs'
weight: 1141
bookFlatSection: true
bookHidden: false
date: 2023-06-08T17:06:56+08:00
---

# 云原生是什么？

## 1 业界对于云原生的定义
总结下来，业界对于云原生涉及的范围大致会定义在4个方面：

1. 方法论和设计原则：
   1. 12 factor +3
   2. 微服务架构模式
   3. 声明式 API
   4. 不可变基础设施
2. 技术和架构：
   1. 微服务架构
   2. 服务网格
   3. Serverless
   4. 容器和容器编排
3. 流程规范
   1. DevOps
   2. CI/CD
4. 基础设施和工具
   1. 云服务：如RDS、S3
   2. 以容器技术为基础的云原生基础设施
   3. Kubernetes、Docker、Helm
   4. Etcd
   5. OPA、Hydra
   6. Prometheus
   7. Istio

下面看看一些具有代表性的公司和组织对于「云原生」相关的定义。

### 1.1 Gartner
_**18 February 2020，《Hype Cycle for Cloud Computing, 2019》**_

如果某事物是为利用云特征而创建的，则它被认为是云原生的。

这些云特征是云计算最初定义的一部分，并且包括作为服务交付的功能，这些功能具有可伸缩性和弹性，通过使用进行计量，基于服务，在互联网技术中无处不在并共享。

术语“云原生”主要用作形容词。 例如，您可以拥有云原生架构，基础架构，应用程序或操作。

整理定义并明确目标是利用云原生的关键。普遍使用三种相互矛盾的定义：

1. 第一含义是最常见的。 基本上，将云原生解释为原生使用云平台功能。 因此，例如它可以是平台即服务，可用性区域或无服务器。 因此，如果您使用的是Amazon，那么您将使用AWS的本机功能，例如RDS，Lambda和Beanstalk。
2. 第二个含义是关注特定技术，例如容器和Kubernetes。 这由名为Cloud Native Computing Foundation（CNCF）的组织推动，该组织推广了这些技术。
3. 第三种含义是本质上具有架构意义的含义。 其中一个来源是GTP的LIFESPAR缩写。 另一个示例是12因子应用程序。 这种方法在那些非常了解架构方法的人中很流行，但绝不是该术语的最常见用法。

### 1.2 CNCF
_**2018-06-11，《CNCF Cloud Native Definition v1.0》**_

云原生技术有利于各组织在公有云、私有云和混合云等新型动态环境中，构建和运行可弹性扩展的应用。云原生的代表技术包括容器、服务网格、微服务、不可变基础设施和声明式API。

这些技术能够构建容错性好、易于管理和便于观察的松耦合系统。结合可靠的自动化手段，云原生技术使工程师能够轻松地对系统作出频繁和可预测的重大变更。

云原生计算基金会（CNCF）致力于培育和维护一个厂商中立的开源生态系统，来推广云原生技术。我们通过将最前沿的模式民主化，让这些创新为大众所用。

### 1.3 Pivotal (VMware)

云原生是一种方法，用于构建和运行充分利用云计算模型优势的应用。

云计算不再将重点放在资本投资和员工上来运行企业数据中心，而是提供无限制的按需计算能力和根据使用情况付费的功能，从而重新定义了几乎所有行业的竞争格局。

IT 开销减少意味着入行的壁垒更低，这一竞争优势使得各团队可以快速将新想法推向市场，这就是软件正在占据世界，并且初创公司正在使用云原生方法来颠覆传统行业的原因。

但是，企业需要一个用于构建和运行云原生应用和服务的平台，来自动执行并集成 DevOps、持续交付、微服务和容器等概念。

### 1.4 RedHat
#### 1.4.1 什么是云原生应用？
云原生应用是独立的小规模松散耦合服务的集合，旨在提供备受认可的业务价值，例如快速融合用户反馈以实现持续改进。简而言之，通过云原生应用开发，您可以加速构建新应用，优化现有应用并在云原生架构中集成。其目标是以企业需要的速度满足应用用户的需求。

#### 1.4.2 云原生应用中的“云”指的是什么？
如果应用是「云原生应用」，那么它专门用于跨私有云、公共云和混合云提供始终如一的开发与自动管理体验。企业采用云计算来提高应用的可扩展性与可用性。通过自助服务和按需置备资源、自动执行从开发到生产的应用生命周期，企业可以获得这些优势。

但是，要想充分利用这些优势，需要一种新的应用开发形式。

例如云原生开发，通过这种方式，可以快速构建和更新应用，同时提高质量并降低风险。具体来说，无论在公共云、私有云还是混合云，您都可以构建和运行可扩展的响应式容错应用。

#### 1.4.3 如何构建云原生应用？
首先从您企业中的人员和帮助他们开展协作的自动化流程入手。也就是说，通过 DevOps 使您的开发和运维团队协同合作，让他们朝着共同目标努力并定期进行反馈。

容器提供理想的应用部署单元和独立的执行环境，为这些实践提供支持。凭借 DevOps 和容器，您能更加轻松地以松散耦合服务的形式（如微服务）来发布和更新应用，而不是等待大型版本的发布。

云原生开发注重架构的模块性、松散耦合及其服务的独立性。每个微服务实现一种业务能力，在自己的流程中运行，并通过应用编程接口（API）或消息传递进行通信。该通信可通过服务网层进行管理。

但是，作为云原生应用的一部分，您无需始终从微服务开始以加速应用交付。许多企业仍然可以使用基于服务的实用架构来优化其传统应用。持续整合和持续部署（CI/CD）等 DevOps 工作流以及全自动部署操作为该优化提供支持。

## 2 云原生技术解决的问题
云原生架构解决应用的核心技术问题是：可移植性、可扩展性、可靠性和可维护性(易用性)。

云原生让云计算标准化、降低大规模自动化运维门槛：

* 通过「容器」技术标准化应用分发和应用交付，解耦应用与底层运行环境
* 通过「Kubernetes」标准化资源调度和资源编排，屏蔽底层架构差异
* 通过「微服务架构」标准化应用架构抽象，解耦业务与技术
* 通过「服务网格」标准化服务通信和服务治理

![](images/what-is-cloud-native-001.png)

* 为了解决单体架构应对业务的「复杂度问题」，使用微服务架构，标准化应用架构抽象、解耦业务与技术。
* 为了解决微服务间「通讯管理和异常处理问题」，使用服务治理框架 + 日志、监控、链路跟踪。
* 为了解决微服务架构下大量应用「部署问题」，使用容器，标准化应用分发与交付、解耦微服务与底层运行环境。
* 为了解决容器的「编排和调度问题」，使用 Kubernetes，标准化资源调度与编排、屏蔽底层架构差异。
* 为了解决微服务框架的「侵入性问题」，使用 Service Mesh，标准化服务通信与治理。
* 为了让 Service Mesh 有「更好的底层支撑」，将 Service Mesh 运行在 k8s 上。
* 为了解决应用「持续交付问题」，引入了 Devops。

以上是从技术角度来定义的「云原生」


## 3 云原生的优势
### 3.1 WPS 如何描述云原生优势

> 那么如此大规模的体量，WPS又是如何做到“运筹帷幄之中”的呢？
> 在今年的金山办公技术活动日中，所有的谜底逐一被揭示开来。
> 一切尽在云原生。云原生，原本是云计算发展过程中的一种新型技术体系。其应用也是“为云而生”，具有快速部署、按需伸缩和不停机交付等特点。
> 而在金山办公高级研发总监、云平台负责人黄传通看来：文档，也已经迈入云原生时代。
> 这是因为当企业在用云原生来开发和运维各种应用的过程中，诸如在线文档、在线表格、在线表单的办公应用，很自然地也会被pick在云上来运行。
> **那么办公场景下的云原生有什么优势？若是总结一句话就是：文档生于云，存于云，编辑于云、流动于云。换言之，办公云原生应用具备“唾手可得、用过即走、随时分享、方便协作”等特点**。
> 这也就是WPS即使应对“承载5.7亿活跃用户设备核心业务运营”、“超1500亿云文档数量”、“270PB云文档存储量”、“百万级QPS（每秒请求）”如此超大规模需求时，还能做到游刃有余的原因。
> 但对于金山办公来说，让文档云原生，并不是一蹴而就的事情，而是经历了13年的一步步发展及演变。
> 据了解，从2009年至2022年，WPS 云服务的架构演化历经了四个时代：
> * 单体式应用
> * 分布式架构
> * DevOps+容器化、微服务化
> * 云原生提供混合云可伸缩能力
> 整个过程，对于服务研发的“速度”和“敏捷”指标都提出了极高的要求 —— 比如必须支持大规模云服务快速更新的能力、服务必须具有高健壮性、故障自愈能力等等。

源：[《超1500亿云文档、5000万行代码，WPS是怎么管理的？》](https://c.m.163.com/news/a/HFPG2P6N0511DSSR.html)

### 3.2 阿里云如何描述云原生和云原生的优势

> 回顾过去十年，数字化转型将科技创新与 商业元素不断融合、重构，重新定义了新业态下的增长极。商业正在从大工业时代的固化范 式进化成面向创新型商业组织与新商业物种的崭新模式。随着数字化转型在中国各行业广泛深入，不管是行业巨头，还是中小微企业都不得不面对数字化变革带来的未知机遇与挑战。
>
> 数字化转型的十年，也是云计算高速发展的十年，这期间新技术不断演进、优秀开源项 目大量涌现，云原生领域进入“火箭式”发展阶段。通过树立技术标准与构建开发者生态， 开源将云计算实施逐渐标准化，大幅降低了开发者对于云平台的学习成本与接入成本。这都让开发者更加聚焦于业务本身并借助云原生技术与产品实现更多业务创新，有效提升企业增长效率，爆发出前所未有的生产力与创造力。
>
> 可以说，当云计算重构整个IT产业的同时，也赋予了企业崭新的增长机遇。正如集装箱的出现加速了贸易全球化进程，以容器为代表的云原生技术作为云计算的服务新界面加速云计算普及的同时，也在推动着整个商业世界飞速演进。上云成为企业持续发展的必然选择，全面使用开源技术、云产品构建软件服务的时代已经到。作为云时代释放技术红利的新方式， 云原生技术在通过方法论、工具集和最佳实践重塑整个软件技术栈和生命周期，云原生架构对云计算服务方式与互联网架构进行整体性升 级深刻改变着整个商业世界的IT根基。
>
> 虽然云原生概念的产生由来已久，但对于云原生的定义、云原生架构的理解却众说纷纭。 到底什么是云原生？容器就代表云原生吗？云原生时代互联网分布式架构如何发展？云原生与开源、云计算有什么关系？开发者和企业为什么一定要选择云原生架构？面对这些问题，每个人都有着不同回答。鉴于此，阿里云结合自身云原生开源、云原生技术、云原生产品、云原生架构以及企业客户上云实践经验，给出了自己的答案，并通过这本白皮书与社会分享自己的思考与总结，旨在帮助越来越多的企业顺利找到数字化转型最短路径。
>
> 未来十年，云计算将无处不在，像水电煤一样成为数字经济时代的基础设施，云原生让云计算变得标准、开放、简单高效、触手可及。如何更好地拥抱云计算、拥抱云原生架构、用技术加速创新，将成为企业数字化转型升级成功的关键。
>
> 云计算的下一站，就是云原生；IT 架构的下一站，就是云原生架构。
>
> 计算机软件技术架构进化有两大主要驱动因素，一个是底层硬件升级，另一个是顶层业务发展诉求。比如伴随着x86硬件体系的成熟，很多应用不再使用昂贵、臃肿的大中型机完成，而是选择了价格更为低廉的以 x86 为主的硬件体系，也由此诞生了包括 CORBA、EJB、RPC 在内的各类分布式架构；后由于互联网业务飞速发展，人们发现传统 IOE 架构已经不能满足海量业务规模的并发要求，于是又诞生了阿里巴巴 Dubbo & RocketMQ、Spring Cloud 这样的互联网架构体系。
>
> 云计算从工业化应用到如今，已走过十五个年头，然而大量应用使用云的方式仍停滞在传统 IDC 时代： 虚拟机代替了原来的物理机；使用文件保存应用数据，大量自带的三方技术组件，没有经过架构改造（如微服务改造）的应用上云，传统的应用打包与发布方式等等。对于如何使用这些技术，没有绝对的对与错， 只是在云的时代不能充分利用云的强大能力，不能从云技术中获得更高的可用性与可扩展能力，也不能利用云提升发布和运维的效率，是一件非常遗憾的事情。
>
> 回顾近年来商业世界的发展趋势，数字化转型的出现使得企业越来越多业务演变成数字化业务，数字化对于业务渠道、竞争格局、用户体验等诸多方面都带来更加严苛的要求，这就要求技术具备更快的迭代速度，业务推出速度从按周提升到按小时，每月上线业务量从“几十/ 月”提升到“几百/ 天”。大量数字化业务重构了企业的业务流水线，企业要求这些业务不能有不可接受的业务中断，否则会对客户体验以及营收造成毁灭性的影响。
>
> 对于企业的CIO 或者 IT 主管而言，原来企业内部 IT 建设以“烟筒”模式比较多，每个部门甚至每个应用都相对独立，如何管理与分配资源成了难题。大家都基于最底层 IDC 设施独自向上构建，都需要单独分配硬件资源，这就造成资源被大量占用且难以被共享。但是上云之后，由于云厂商提供了统一的 IaaS 能力和云服务，大幅提升了企业 IaaS 层的复用程度，CIO 或者IT 主管自然而然想到 IaaS 以上层的系统也需要被统一，使资源、产品可被不断复用，从而能够进一步降低企业运营成本。
>
> 所有这些问题都指向一个共同点，那就是云的时代需要新的技术架构，来帮助企业应用能够更好地利用云计算优势，充分释放云计算的技术红利，让业务更敏捷、成本更低的同时又可伸缩性更灵活，而这些正好就是云原生架构专注解决的技术点。

源：《阿里云云原生架构白皮书》

### 3.3 《云原生模式》如何描述为什么需要云原生？

**现代应用程序的需求**

数字体验已经不再是我们生活中的一个配角，它们在我们日常生活中的许多活动中都扮演着重要的角色。这种普遍性已经超越了我们对所使用的软件的期望：我们希望应用程序总是可用的，能够不断地升级并提供个性化的体验。在软件产品从构思到实现这一生命周期的初期，我们就必须能够满足这些期望。

#### 3.3.1 零停机时间

2015年9月20日的AWS停机，揭示了现代应用程序的一个关键需求：它必须始终是可用的。可用容忍应用程序出现短暂不可用情况的日志已经一去不复返了。世界始终是在线的。没有人希望计划外的停机出现，其影响已经达到了惊人的水平。例如，2013年《福布斯》估计，亚马逊在一次13分钟的意外停机事故中损失了近200美元。不管停机是否在计划中，都会导致收益和客户满意度的严重下降。

但是，维护系统的正常运行不仅是运维团队的问题。软件开发人员或者架构师对设计和开发一个松耦合、组件化的系统同样负有责任，应该通过部署冗余组件来应对不可避免的故障，并设置隔离机制来防止故障在整个系统中引起连锁反应。而且，还必须把软件设计成能够在不停机的情况下完成计划事件(例如，升级)。

#### 3.3.2 缩短反馈周期

同样至关重要的是频繁发布代码的能力。在激烈的竞争和不断增长的消费者期望的双重驱动下，应用程序更新已经从每月数次发展到每周数次，有时甚至一天数次。让用户感到兴奋毫无疑问是有价值的，但是持续发布新版本的最大动力是降低风险。

从你对某个功能有了想法的那一刻起，你就承担了一定程度的风险。这个主意好吗？用户能接受它吗？它能以一种更好的方式实现吗？虽然你会尽可能地去预测可能的结果，但现实往往与预期不同。获得诸如此类重要问题答案的最佳方法，是发布一个功能的早期版本并收集反馈信息。利用这些反馈信息，你可以做出调整，甚至完全改变想法。频繁的软件发布不仅缩短了反馈周期，也降低了风险。

在过去几十年占主导地位的单体软件系统，无法做到频繁地发布新版本。因为由独立团队构建和测试的各子系统之间密切相关，所以需要把它们作为一个整体进行测试后才能够进入“脆弱”的打包过程。如果在集成测试阶段的后期发现了缺陷，那么这个漫长而艰苦的过程就需要重新开始。为了实现将软件发布到生产环境的敏捷性，新的软件架构是必不可少的。

#### 3.3.3 移动端和多设备支持

2015年4月，技术趋势评测和分析公司 comScore 发布的一份报告中显示，移动设备的互联网使用率首次超过台式计算机。今天的应用程序需要支持至少两种移动设备平台(iOS和Android)和桌面系统(仍然占很大一部分使用比例)。

此外，用户越来越希望他们的应用体验随时可以从一个设备无缝切换到另一个设备上。例如，用户可能在 Apple TV 上看电影，然后去机场的车上改用移动设备继续观看。此外，移动设备的使用模式与桌面设备的使用模式有很大的不同。例如，银行必须能够满足移动设备用户频繁的应用程序刷新需求，他们可能正在不断查看每周的薪水是否到账。

正确设计应用程序对于满足这些需求至关重要。核心服务必须能够支持所有为用户提供服务的终端设备，并且系统必须能够适应不断变化的需求。

#### 3.3.4 互联设备 (物联网)

互联网不再仅仅将人类与系统连接起来，如今，数以亿计的设备通过互联网连接，使得它们能够被连接的其他实体监控甚至控制。预计到2022年，仅家庭自动化市场，即使其在所有物联网(IoT)连接设备中只占很小的一部分，也将成为一个将近530亿美元的市场。

联网的家庭拥有传感器和远程控制设备，例如，运动探测器、照相机、智能恒温器，甚至照明系统。这些设备都是非常便宜的。几年前，在 -32摄氏度的天气里，我的水管爆裂了，于是我用一个联网的恒温器和一些温度传感器搭建了一套建议的恒温系统，花费总共不到 300 美元。其他物联网设备还包括汽车、家用电器、农业设备、喷气式发动机，以及我们大多数人口袋里的超级计算机 –– 智能手机。

物联网设备从两个基本方面改变了我们的软件的特性。首先，互联网上的数据流量急剧增加。数以亿计的设备在一分钟内多次广播数据，甚至有的设备达到每秒多次。其次，为了收集和处理这些海量数据，用于计算的基础设施势必发生重大的改变。当计算资源被放在“边缘”位置，即更靠近连接设备时，它会变得更加分布式。数据量和基础架构之间的差异，需要新的软件设计和实践来解决。

#### 3.3.5 数据驱动

数量正在不断增加，数据源分布得更加广泛，而软件的交付周期正在缩短。这三个因素使得大型、集中式、共享的数据库变得无法使用。

例如，一个装有数百个传感器的喷气式发动机，它会经常与数据中心的数据库断开连接，同时由于带宽限制，无法在建立连接后立即将所有数据传输到数据中心。此外，共享数据库需要在众多应用程序之间进行大量的处理和协调，以便满足各种数据模型和交互场景的需求，这是导致无法缩短发布周期的主要问题。

这些应用程序需要的不是单一的共享数据库，而是一个由更小的、本地化数据库组成的网络，以及能够在多个数据库管理系统之间管理数据关系的软件。这些新方法催生了从软件敏捷开发管理到数据层面的各种要求。

最后，如果没有人使用新的数据，那么这些数据就没有价值。今天的应用程序必须越来越多地使用数据，通过更智能的应用程序为客户提供更高的价值。例如，地图应用程序使用来自物联网汽车和移动设备的GPS数据，以及道路和地形的数据，来提供实时交通报告和路线导航服务。过去几十年的应用程序，仅仅通过精心设计的算法加以仔细调整来适应预期的使用场景，而现在它们正在被不断变化的新应用程序所取代，甚至这些新程序可能会自动调整内部的算法和配置。

这些用户需求 –– 持续的可用性、频繁发布新版本以实现不断演进、易于伸缩和智能化，都是过去的软件设计和管理系统所无法满足的。


## 4 云原生发展史

详细内容见我的另外一篇文章 [《云原生发展史》](../../timelines/cloudnative-timeline.md)

## 5 我对于云原生的理解

* 云原生是云计算的延伸，云原生以云计算为基础，云原生是云计算的新阶段。
* 从利益相关者的角度来看，云原生涉及的利益相关者范围包括：
  * 云基础设施提供商(私有云、公有云)
  * 数字化转型的企业
  * IT技术开发者(或技术爱好者)
* 从发展趋势来看，云原生已经从关注技术，发展到关注商业价值和产业落地；圈子的发展已经从开源/技术社区、互联网企业、大型企业，发展到中小企业、传统企业等。
* 从基础设施的角度来看，云计算基础设施关注资源，云原生时代的云原生基础设施关注应用，即从「以资源为中心」演进到「以应用为中心」。
* 从技术角度来看，云原生像其他技术体系概念一样，涉及到架构、理念、组件、技术等4个方面：
  * 架构：微服务架构、12因素...
  * 理念：不可变基础设施、声明式设计、DevOps、GitOps...
  * 组件：Docker、Kubernetes...
  * 技术：容器、微服务...
* 从技术生态角度来看，云原生技术生态已经在爆发式增长。从早期的容器、微服务、DevOps等领域，扩展到几十个细分领域，包括应用定义、服务网格、可观测性、云原生数据库、消息中间件等。从CNCF的 Landscape 来看，已经有1000+的开源和商业化的项目。
* 从商业角度来看，云原生是产业数字化转型和创新的新基建和加速器，服务于数字化转型的企业/开发者。在资源利用、环境适应性、业务连续性、交付效率等方面为客户降本增效，让客户专注于自身业务的价值挖掘。
* 云原生解决的核心问题：
  * 为数字化转型的企业组织，提供管理数字化系统的复杂度的能力，让组织能够专注于自身的业务价值。这些复杂性体现在这些数字化系统应对环境变化、需求变化、业务规模增长等方面。
  * 为云基础设施提供商提供新的思路，细化产业分工，专注资源价值、能力价值：
    * 资源价值：提供高效、低成本的资源
    * 能力价值：提供生于云、长于云的软件架构、交付和运维体系
  * 并不解决这些数字化系统最终使用者的使用体验和业务能力问题，这些是数字化转型企业的业务范畴。

## 参考资料
1. [《超1500亿云文档、5000万行代码，WPS是怎么管理的？》](https://c.m.163.com/news/a/HFPG2P6N0511DSSR.html)
2. 《阿里云云原生架构白皮书》
3. 《云原生模式》
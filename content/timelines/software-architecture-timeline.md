---
title: '软件架构发展史'
linkTitle: '软件架构发展史'
type: 'docs'
weight: 104
bookFlatSection: true
bookHidden: false
date: 2023-06-27T17:06:56+08:00
---

# 软件架构发展史

## 20世纪60年代中期：软件危机
20世纪60年代中期开始爆发大规模的软件危机，软件危机的突出表现就是软件生产不仅效率低，而且质量差。究其原因，主要是因为软件开发的理论方法不够系统、技术手段相对滞后，主要的软件生产都是手工作坊式的。

## 基础研究阶段(1968-1994)
1968年和1969年：NATO会议提出软件工程
* 为了解决软件危机，北大西洋公约组织(NATO)分别于1968年和1969年连续召开两次著名的软件会议，后人称之为 NATO 会议。
* NATO 会议提出了软件工程的概念，发展了软件工程的理论和方法，形成了软件工程专业的教育、培养和训练体系，为软件产业的发展指明了方向。

1868年，**术语“软件架构”在北大西洋公约组织会议上第一次出现，但并没有得到明确定义**。

直到20世纪80年代，“架构”一词在大部分情况下被用于表示计算机系统的物理结构，偶尔被用于表示计算机指令集的特定体系。

从20世纪80年代起，为应对大型软件开发中存在的危机，对软件结构进行描述的方法开始在大型软件开发过程中广泛使用，并在实践中积累了大量经验，经研究者总结归纳，逐渐形成了以描述软件高层次结构为目的的理论体系，实质上形成了软件架构研究领域的雏形。

## 概念体系和核心技术形成阶段(1991-2000)
1991年：Winston W.Royce 与 Walker Royce 在一篇文章中**首次对"软件架构"进行了定义**。

1992年：D.E.Perry 与 A.L.Wolf 对软件架构进行了阐述，创造性地提出了著名的 **"{elements, forms, rationale} = software architecture" 公式**，使之成为后续软件架构概念发展的基础。

与此同时，大量关于软件架构的研究陆续展开并卓有成效，其中最著名的是卡内基-梅隆大学软件工程研究所(CMU/SEI)进行的研究。

1996年：CMU/SEI 的 Mary Shaw 和 David Garlan 出版了《Software Architecture：Perspectives on an Emerging Discipline》，其对软件架构概念的内涵与外延进行了详尽阐述，这对软件架构概念的形成起到了至关重要的作用。

但随着软件规模的进一步扩大和软件复杂性的不断提高，新一轮的软件危机再次出现。
1995年，Standish Group 研究机构以美国境内 8000 个软件工程项目作为调查样本进行调查，其结果显示，有84%的软件项目无法按时按需完成，超过30%的项目夭折，工程项目耗费平均超过预算189%。软件工程遇到了前所未有的困难。

通过避免软件开发中重复劳动的方式提升软件开发效率、保障软件质量，软件重用与组件化成为解决此次危机的行之有效的方案。随着组件化软件开发方式的发展，如何在设计阶段对软件系统进行抽象，获取系统蓝图以支持系统开发中的决策成为迫切而现实的问题。

从1995年起，软件架构研究领域开始进入了快速发展阶段，来自于工业界与学术界的研究成果大量出现。
* 在这一阶段中，研究关注点主要集中于对前一阶段研究成果进行整合与完善，使得软件架构作为一个技术领域日渐成熟。
* 在此阶段中，对软件架构概念的探讨越加深入，Booch、Rumbaugh 和 Jacobson 从另一个角度对软件架构的概念进行了全新的诠释，认为架构是一系列重要决策的集合。
* 此阶段还提出了第一个由软件工程研究机构提出的软件架构实践方法体系 - SAAM；企业界也提出并完善了多视角软件架构表示方法以及针对软件架构的特定设计模式。
* Siemens、Nokia、Philips、Nortel、Lockheed、Martin、IBM，以及其他一些大型软件开发组织开始关注软件架构，并联手进行了软件产品线架构的重要性调查。

1998年：Rechtin 与 Mark Maier 出版了《The Art of Systems Architecting》一书，很好地阐述了系统与软件的关系。

## 理论体系完善与发展阶段(1996至今)
随着基于组件软件架构理论的建立，与之相关的一些研究方向逐渐成为软件工程领域的研究热点，主要包括：
* 软件架构的描述与表示；
* 软件架构分析、设计与测试；
* 软件架构发现、演化与重用；
* 基于软件架构的开发方法；
* 软件架构风格等。

1998年：
* P.Bengtsson 和 J.Bosch 在 ICSR(International Conference On Software Reuse)上发表了《Scenaio-based Software Architecture Reengineering》，展开软件架构的“再工程”。
* P.Oreizy、N.Medvidovic 和 R.N.Taylor 在 ICSE 会议上发表了《Architecture-based Runtime Software Evolution》，开创了动态软件架构的研究。

## 普及应用阶段(1999至今)
1999年：召开第一届IFIP软件架构会议，成立IFIP工作组2.10与全球软件架构师协会。

2000年：IEEE 1471-2000 的 “软件密集型系统架构描述的推荐实践” 发布，**第一次定义了软件架构的形式化标准**。标志着软件架构理论体系已基本建立，并已具备普及应用的基础。发布 IEEE 1471-2000，为软件架构的普及应用制定了标准化规范，于2007和2011年修订。

2002年：SRP (~SOLID)

2003年：L.Bass、P.Clements 和 R.Kazman 出版了《Software Architecture in Practice》，引起巨大反响，书中总结了软件架构研究领域的最新成果，并介绍了如何在实践中应用这些理论成果。

2003年：领域驱动设计

2005年：MVVM 模式(Model-View-ViewModel)

2005年：端口和适配器架构即六边形架构

2006年：CQRS 与 ES (命令查询职责分离与事件溯源)

2008年：洋葱架构

2009年：微服务(Netflix)

2010年：DCI 架构(Data-Context-Interaction)

2012年：整洁架构

2014年：C4 模型

2020年，Multi-Runtime Microservices Architecture。Bilgin lbryam 发表了一篇名为 Multi-Runtime Microservices Architecture 提出了 Multi-Runtime 的理念，对基于 Sidecar 模式的各种产品形态进行了实践总结和理论升华。

## 参考资料
1. 《软件架构理论与实践》
2. [The Software Architecture Chronicles](https://herbertograca.com/2017/07/03/the-software-architecture-chronicles/)
3. [软件架构编年史(译)](https://www.jianshu.com/p/b477b2cc6cfa)
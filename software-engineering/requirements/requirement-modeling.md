# 需求建模(Requirement Modeling)

- [需求建模(Requirement Modeling)](#需求建模requirement-modeling)
  - [1 简介](#1-简介)
  - [2 需求分析](#2-需求分析)
  - [3 基于场景建模](#3-基于场景建模)
  - [4 基于类建模](#4-基于类建模)
  - [5 功能建模](#5-功能建模)
  - [6 行为建模](#6-行为建模)
  - [参考资料](#参考资料)

## 1 简介
**概念：需求建模**使用文字和图表综合的形式，以相对容易理解的方式描绘需求，更重要的是可以更直接地评审它们的正确性、完整性和一致性。

**人员**：软件工程师(有时被称作分析师)使用从各种利益相关者那里获取的需求来构建模型。

**重要性**：所有利益相关者都可以轻松评估需求模型，从而在尽可能早的时间内获得有用的反馈。然后，在重新定义模型时，它将成为软件设计的基础。

**步骤**：需求建模包含3步：
1. 基于场景建模
2. 基于类建模
3. 基于行为建模

**工作产品**：使用场景(又称为用例)描述了软件功能和用法。此外，可以使用一系列UML图来表示系统行为和其他方面。

**质量保证措施**：必须评审需求建模工作产品的正确性、完整性和一致性。

## 2 需求分析
**需求分析产生软件操作特征的规格说明，指明软件和其他系统元素的接口，规定软件必须满足的约束**。

在需求分析过程中，软件工程师(有时这个角色也被称作分析师或建模师) 可以细化在前期需求工程的起始、获取、协商任务中建立的基础需求。

**需求建模动作结果为以下一种或多种模型类型**：
* **场景模型**：出自各种系统“参与者”观点的需求。
* **面向类的模型**：表示面向对象类(属性和操作) 的模型和如何通过类的协作获得系统需求。
* **行为模型**：表示软件如何对内部或外部“事件”做出反应。
* **数据模型**：描述问题信息域的模型。
* **面向流的模型**：表示系统的功能元素并且描述当功能元素在系统中运行时怎样进行数据变换。

这些模型为软件设计者提供信息，这些信息可以被转化为结构、接口和组件级的设计。最终，在软件开发完成后，需求模型(和需求规格说明) 就为开发人员和客户提供了评估软件质量的手段。

上面这些建模方法的流行程度：
* **基于场景的建模**，这项技术在整个软件工程界**非常流行**。
* **基于流和数据建模**，在过去十年，人们已经**不常使用**了。

在整个分析建模过程中，软件工程师的**主要关注点集中在做什么而不是怎么做**。
* 发生哪些用户交互？
* 系统处理什么对象？
* 系统必须执行什么功能？
* 系统展示什么行为？
* 定义什么接口？
* 有什么约束？

**需求模型必须实现三个主要目标**：
1. 描述客户需要什么
2. 为软件设计奠定基础
3. 定义在软件完成后可以被确认的一组需求。

**分析模型在系统级描述和软件设计之间建立了桥梁**:
* 这里的系统级描述给出了整个系统或商业功能(软件、硬件、数据、人员元素)；
* 而软件设计出了软件的应用程序结构、用户接口以及组件级的结构；
* 要注意需求模型的所有元素都可以 直接跟踪到设计模型；通常难以清楚地区分设计和分析模型，有些设计总是作为分析的一部份进行，而有些分析将在设计中进行；
* 关系如下图：

<div align=center><img src="./requirement-modeling/relationship.png"></div>

## 3 基于场景建模
尽管有多种方式度量基于计算机的系统或产品的成功与否，但用户满意度仍然居于首位。如果软件工程师了解最终用户(和其他参与者) 希望如何与系统交互，那么软件团队将能够更好地正确描述需求特征并建立有意义的分析和设计模型。

**使用UML对需求进行建模首先要以用例图、活动图和序列图的形式创建场景**。

## 4 基于类建模

## 5 功能建模

## 6 行为建模

## 参考资料
1. 《软件工程 - 实践者的研究方法》
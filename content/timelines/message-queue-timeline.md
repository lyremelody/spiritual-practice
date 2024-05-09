---
title: '消息队列发展史'
linkTitle: '消息队列发展史'
type: 'docs'
weight: 109
bookFlatSection: true
bookHidden: false
date: 2023-07-31
isCJKLanguage: true
params:
  author: lyremelody
---

![](images/message-queue-histroy.jpg)

## 1983年，Teknekron
孟买26岁的工程师 Vivek Ranadiv 提出了“软件总线”的设想，同年，创建了 Teknekron 公司。

提出了一个问题：为什么没有通用的软件总线 – 一种通信系统，可以将信息从一个应用程序传递到另一个应用程序呢？

## 1985年，TIB
Teknekron 公司实现了第一个消息队列软件，叫 TIB（The Information Bus）。

高盛公司成为了 Teknekron 公司的客户，Teknekron 公司致力于解决金融交易（financial trading）方面的问题，后来就提出了发布订阅机制，并基于它开发出了第一个消息队列软件。

## 1993年，IBM（MQSeries → WebSphere → IBM MQ）
随着 TIB 受到了企业的欢迎，IBM 也看在眼里，于是在1990年在温彻斯特附近的赫斯利公园实验室成立了一个研究小组，决定研发自己的消息队列软件。

然后在1993年，IBM 推出了自家的消息队列软件 MQSeries，2002年更名为WebSphere MQ，2014年，更名为 IBM MQ。

## 1997年，Microsoft MSMQ
微软研发出了自家的消息中间件：MSMQ（Microsoft Message Queue）。

TIB 仍占据很大的市场份额，同年，Teknekron以TIBCO的形式作为一家独立公司再度出现。

## 2001年，Java Message Service(JMS)
提出的原因：
* 价格昂贵（high-priced）：巨头开发的消息中间件价格昂贵，只有大型组织机构能用得起，中小型企业无法承担高额的费用，这也限制了消息队列的应用市场；
* 商业壁垒或供应商壁垒（vender lock-in）：由于消息队列供应商采用的是不同的API，不同的协议，从而导致无法使用单一的总线来协调每种消息组件。

为了解决上面两个问题，便引入了JMS，一个与具体平台无关的API，绝大多数消息队列供应商都支持JMS。

但是JMS只是在底层具体的消息中间件之上做了一层适配，每个消息中间件并没有实现统一的规范。

## 2003年，ActiveMQ
2003年，一些开源开发者集合在一起，形成了 Apache Geronimo, 当时市场上没有开源的消息中间件，大多数消息中间件都是闭源且价格昂贵，所以小组筹划着开发出一款开源的产品，让大部分公司都能使用上，于是 ActiveMQ 便诞生了。

## 2004年，AMQP
在 2004 ~ 2006年，摩根大通开始设计统一的协议 AMQP，与思科、红帽等公司一起成立了 AMQP 工作组，通过两年多的努力，在 2006年推出了第一个版本的AMQP标准，从此，所有消息中间件产品都是基于此标准来实现的，突破了开发语言、产品等条件限制。

## 2006年，RabbitMQ
基于 AMQP 标准，RabbitMQ技术团队，开发出了第一个实现了AMQP标准的消息中间件，并将其命名为 RabbitMQ。

为什么将其称作 ”Rabbit“，因为他们觉得兔子行动速度快，繁殖起来也非常疯狂，用它来命名再合适不过了。

此时，AMQP标准也在快速迭代。

2007年，RabbitMQ 1.0 版本正式面世。

## 2011年，Kafka
一开始LinkIn采用的是 ActiveMQ 进行数据交换，但是 2010 年以后，ActiveMQ 已经无法满足业务上对数据传递的需求，因为经常会由于各种缺陷而导致消息阻塞或服务无法正常访问，为解决这个为题，LinkIn的首席架构师便开始组织团队，研发自己的消息传递系统。

所以Kafka的诞生是为了解决LinkIn的数据管道问题。

Kafka是LinkIn开发的消息中间件，最后捐给了 Apache开源基金会。

## 2012年，RocketMQ
随着阿里巴巴电商业务的发展，阿里巴巴着手开始研发自己的消息中间件。

2012年，阿里巴巴发布了自家的分布式消息中间件，RocketMQ。RocketMQ经过了 ”双十一“ 的洗礼，在高并发、高性能、高可靠方面都有出色的表现。

## 2012年，Pulsar
Apache Pulsar 诞生于 Yahoo，当初是为了解决雅虎内部各个部门间数据的协调，也就是解决多租户的问题，希望各个部门之间能够共享同一份数据，不用单独部署独立的系统的来操作数据，从而保证了各部门间数据一致性问题，同时简化了维护成本。

2012年在Yahoo内部启动，2016年9月开源，2017年6月捐赠给了 Apache并成为了一个孵化器项目，2018年9月从Apache毕业成为了顶级项目。

## 参考资料
1. [消息队列发展历史](https://aris.org.cn/archives/xiao-xi-dui-lie-fa-zhan-li-shi)
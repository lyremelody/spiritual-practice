---
title: 'Reliability 可靠性'
linkTitle: 'Reliability 可靠性'
type: 'docs'
weight: 1112
bookFlatSection: true
bookHidden: false
date: 2023-06-08T17:06:56+08:00
---

# Reliability 可靠性

## 1 软件质量模型中的「可靠性」(Reliability)
在计算机软件领域，ISO/IEC 25010 中定义的产品质量模型中，定义了八个质量属性：功能适用性(Function Suitability)、性能效率(Performance Efficiency)、兼容性(Compatibility)、可用性(Usability，其实我感觉翻译成「易用性」更容易避免歧义)、可靠性(Reliability)、安全(Security)、可维护性(Maintainability)、可移植性(Portability)。

其中「Reliability」可靠性定义为：系统、产品或组件在指定条件下、指定时间段内执行指定功能的程度。它由以下几个子特性组成：
* 成熟度(Maturity)：系统、产品或组件在正常操作下满足可靠性需求的程度；
* 可用性(Availability)：系统、产品或组件在需要使用时可操作和可访问的程度；关于可用性相关的内容，见 [《Concept-Availability》](./availability.md)
* 容错能力(Fault tolerance)：尽管存在硬件或软件故障，系统、产品或组件按预期运行的程度；关于容错性相关的内容，见 [《Concept-fault tolerance》](./fault-tolerance.md)
* 可恢复性(Recoverability)：在发生中断或故障时，产品或系统可以恢复直接受影响的数据并重新建立系统所需状态的程度。


## 2 计算机存储领域的「数据可靠性」(Data Reliability)


## 3 计算机网络领域的「可靠性」
在计算机网络中，可靠的协议(a reliable protocol) 是一种通信协议。这种协议由接受方通知发送方数据是否成功接收。可靠性(Reliability) 是保证(assurance) 的代名词，是国际电联([ITU](https://en.wikipedia.org/wiki/ITU))和ATM论坛([ATM Forum](https://en.wikipedia.org/wiki/ATM_Forum))使用的术语。

可靠的协议通常会比不可靠的协议产生更多的开销，因此，运行速度较慢且可伸缩性较低。对于单播协议，这通常不是问题，但对于可靠的多播协议，则可能成为问题。

传输控制协议（TCP）是Internet上使用的主要协议，是一种可靠的单播协议。 UDP是一种不可靠的协议，通常用于计算机游戏，流媒体或其他由于速度问题而可能会容忍某些数据丢失的场景。

通常，可靠的单播协议也是面向连接的。例如，TCP是面向连接的，虚电路ID由源IP地址和目标IP地址以及端口号组成。但是，某些不可靠的协议是面向连接的，例如异步传输模式和帧中继。此外，某些无连接协议（例如IEEE 802.11）是可靠的。

### 3.1 历史
在Donald Davies提出的包交换概念的基础上，ARPANET上的第一个通信协议是一种经由1822接口连接主机的可靠的数据包传送机制。源主机简单地以正确的包格式排列数据，插入目的主机的地址，然后通过接口将消息发送到其连接的接口消息处理器（IMP）。将消息传递到目的主机后，将确认数据传回源主机。如果网络无法传递消息，则IMP会将错误消息发送回源主机。

同时，CYCLADES和ALOHAnet的开发人员证明，有可能在不提供可靠的数据包传输的情况下构建有效的计算机网络。后来，这个研究被以太网的设计者采纳。

如果网络不能保证数据包的传递，则主机有责任通过检测和重新传输丢失的数据包来提供可靠性。随后在ARPANET上的经验表明，网络本身无法可靠地检测到所有数据包传递失败，这在任何情况下都将错误检测的责任推到了发送主机上。这导致了端到端原则的发展，端到端是Internet的基本设计原则之一。

### 3.2 属性
可靠消息传递是在不可靠的基础结构上传递消息的概念，同时能够对消息的成功传输做出某些保证。例如，如果消息已成功传递，则它最多只能传递一次，或者所有成功传递的消息都以特定顺序到达。

### 3.3 实现
可靠的传输协议能够建立在不可靠的协议之上。一个非常常见的例子是传输控制协议（TCP）。
WS-ReliableMessaging是实现可靠消息传递的一种协议，它处理SOAP消息的可靠传递。
IEEE 802.11尝试为所有流量提供可靠的服务。如果发送方在预定时间段内未收到ACK帧，则发送方将重新发送帧。

## 参考
1. [ISO 25000 STANDARDS - ISO 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010)
2. [维基百科-可靠性(计算机网络)](https://zh.wikipedia.org/wiki/%E5%8F%AF%E9%9D%A0%E6%80%A7_(%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C))
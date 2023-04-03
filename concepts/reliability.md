# 「Reliability」 可靠性

- [「Reliability」 可靠性](#reliability-可靠性)
  - [1 软件质量模型中的「可靠性」(Reliability)](#1-软件质量模型中的可靠性reliability)
  - [2 计算机存储领域的「数据可靠性」(Data Reliability)](#2-计算机存储领域的数据可靠性data-reliability)
  - [3 计算机网络领域的「可靠性」](#3-计算机网络领域的可靠性)
  - [参考](#参考)

## 1 软件质量模型中的「可靠性」(Reliability)
在计算机软件领域，ISO/IEC 25010 中定义的产品质量模型中，定义了八个质量属性：功能适用性(Function Suitability)、性能效率(Performance Efficiency)、兼容性(Compatibility)、可用性(Usability，其实我感觉翻译成「易用性」更容易避免歧义)、可靠性(Reliability)、安全(Security)、可维护性(Maintainability)、可移植性(Portability)。

其中「Reliability」可靠性定义为：系统、产品或组件在指定条件下、指定时间段内执行指定功能的程度。它由以下几个子特性组成：
* 成熟度(Maturity)：系统、产品或组件在正常操作下满足可靠性需求的程度；
* 可用性(Availability)：系统、产品或组件在需要使用时可操作和可访问的程度；关于可用性相关的内容，见 [《Concept-Availability》](./availability.md)
* 容错能力(Fault tolerance)：尽管存在硬件或软件故障，系统、产品或组件按预期运行的程度；关于容错性相关的内容，见 [《Concept-fault tolerance》](./fault-tolerance.md)
* 可恢复性(Recoverability)：在发生中断或故障时，产品或系统可以恢复直接受影响的数据并重新建立系统所需状态的程度。


## 2 计算机存储领域的「数据可靠性」(Data Reliability)

## 3 计算机网络领域的「可靠性」


## 参考
1. [ISO 25000 STANDARDS - ISO 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010)
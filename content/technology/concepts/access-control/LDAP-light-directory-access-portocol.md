---
title: 'LDAP(Lightweight Directory Access Protocol)'
linkTitle: 'LDAP(Lightweight Directory Access Protocol)'
type: 'docs'
weight: 1134
bookFlatSection: true
bookHidden: false
date: 2023-09-12
isCJKLanguage: true
params:
  author: lyremelody
---

## 1 目录服务
日常生活中使用的电话薄内记录着亲朋好友的姓名、电话与地址等数据，它就是 telephone directory(电话目录)；计算机中的文件系统(file system)内记录着文件的文件名、大小与日期等数据，它就是 file directory(文件目录)。如果这些目录内的数据能够由系统加以整理，用户就能够容易且迅速地查找到所需的数据，而 directory service(目录服务)提供的服务，就是要达到此目的。**目录服务是一个特殊的非关系型数据库，用来保存描述性的、基于属性的详细信息，支持过滤功能**。这种数据库与我们常⻅的关系型数据库(Mysql、SQL Server、Oracle等)的区别在于目录服务以树状的层次结构来存储数据，就好像 Linux/Unix 系统中的文件目录一样。此外，目录服务是一个专⻔为搜索和浏览而优化的数据库，有着优异的读性能，但写性能差，并且没有事务处理、回滚等复杂功能，不适于存储修改频繁的数据。综上所述，目录服务更适用于存储如组织架构之类的信息。

## 2 LDAP 简介
**LDAP(Light Directory Access Portocol)是基于 X.500 标准的轻量级目录访问协议**。LDAP 协议之前有一个 X.500 DAP 协议规范，该协议十分复杂，是一个重量级的协议，后来对 X.500 进行了简化，诞生了 LDAP 协议，与 X.500 相比变得较为轻量，其实 LDAP 协议依然复杂。

LDAP 约定了 Client 与 Server 之间的信息交互格式、使用的端口号、认证方式等内容。而 LDAP 协议的实现，有着众多版本，例如：
* **微软的 Active Directory** 是 LDAP 在 Windows 上的实现，AD 实现了 LDAP 所需的树形数据库、具体如何解析请求数据并到数据库查询然后返回结果等功能。
* **Red Hat Directory Servers** 是用于在 UNIX 环境中通过 Red Hat Directory Server 管理多个系统的工具。红帽目录服务器允许用户将用户详细信息存储在 LDAP 服务器中。该工具为用户提供对目录数据，组成员身份和远程访问以及通过验证过程的访问的安全且受限制的访问。
* **IBM Tivoli Directory Server** 是基于 IBM 的 LDAP 实现。基于 LDAP 框架。该工具专注于更快地开发和分发身份控制，安全性和 Web 应用程序。Tivoli Directory Server 包括不同的验证方法，例如通过数字证书，简单认证和安全层（SASL）和 CRAM-MD5 进行的验证。
* **OpenLDAP** 是可以运行在 Linux 上的 LDAP 协议的开源实现。
* 而我们平常说的 LDAP Server，一般指的是安装并配置了 Active Directory、OpenLDAP 这些程序的服务器。

## 3 LDAP 基本模型
每一个系统、协议都会有属于自己的模型，LDAP 也不例外，在了解 LDAP 的基本模型之前我们需要先了解几个 LDAP 的目录树概念:
1. 目录树：在一个目录服务系统中，整个目录信息集可以表示为一个目录信息树，树中的每个节点是 一个条目。
2. 条目：每个条目就是一条记录，每个条目有自己的唯一可区别的名称(DN)。
3. 对象类：objectClass，与某个实体类型对应的一组属性，对象类是可以继承的，这样父类的必须属性也会被继承下来。
4. 属性：描述条目的某个方面的信息，一个属性由一个属性类型和一个或多个属性值组成，属性有必须属性和非必须属性。

LDAP 目录以树状的层次结构来存储数据，最顶层即根部称作「基准DN」，形如 ```dc=lyremelody,dc=cn``` 或者 ```ou=lyremelody.cn```，前一种方式更为灵活也是 Windows AD 中使用的方式。在根目录的下面有很多的文件和目录，为了把这些大量的数据从逻辑上分开，LDAP 像其它的目录服务协议一样使用 ```OU(Organization Unit)```，可以用来表示公司内部机构，如部⻔等，也可以用来表示设备、人员等。同时 OU 还可以有子 OU，用来表示更为细致的分类。LDAP 中每一条记录都有一个唯一的区别于其它记录的名字 ```DN(Distinguished Name)```，其处在「叶子」位置的部分称作 RDN；如 ```dn:cn=tom,ou=animals,dc=lyremelody,dc=cn``` 中 tom 即为 RDN；RDN 在一个 OU 中必须是唯一的。

因为 LDAP 数据是「树」状的，而且这棵树是可以无限延伸的，假设你要树上的一条记录，如何寻找它的位置呢？当然首先要说明是哪一棵树(dc)，然后是从树根到那个苹果所经过的所有「分叉」(ou)，最后就是这个苹果的名字(cn)。知道了树(dc=lyremelody,dc=cn)，分叉 (ou=IT,ou=Worker,ou=Pentester)，苹果(cn=abc)，就可以找到我们想要的苹果了：
```
dn:cn=abc,ou=IT,ou=Worker,ou=Pentester,dc=lyremelody,dc=cn
```

LDAP 的功能模型中定义了一系列利用 LDAP 协议的操作。它包含了三个部分:
* **查询操作(Interrogation Operations)**：容许查询目录和取得数据。它包含 Search Operating 和 Compare Operation。
* **更新操作(Update Operations)**：容许添加(ADD)、删除(Delete)、重命名(Rename)和改变目录(Modify)
* **认证和管理操作(Authentication And Control Operations)**：容许客户端在目录中识别自己，并且能够控制一个 Session 的性质。

## 4 LDAP 和 AD 的关系
Active Directory 是微软基于 LDAP 协议的一套解决方案(LDAP 服务器 + 应用)， 而 LDAP 是与 AD 交互的协议之一。

Active Directory 解决了细粒度的权限控制「谁」以 「什么权限」访问「什么」。AD 在 LDAP v3 规范之上还有自定义扩展，例如，帐户锁定，密码到期等。

## 参考资料
1. [守护沃土数字平台的“闸门”：OneAccess统一身份与访问管理](https://e.huawei.com/cn/blogs/industries/insights/2020/one-access-roma)
2.  [Types of Authentication Protocols](https://www.geeksforgeeks.org/types-of-authentication-protocols/)
3.  [LDAP 协议相关, Geekby's Blog](https://www.geekby.site/2020/12/ldap-%E5%8D%8F%E8%AE%AE/)
4.  [Authing - 概念](https://docs.authing.cn/v2/concepts/)
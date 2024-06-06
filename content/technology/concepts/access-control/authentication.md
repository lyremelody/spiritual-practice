---
title: 'Authentication 身份验证/认证'
linkTitle: 'Authentication 身份验证/认证'
type: 'docs'
weight: 1131
bookFlatSection: true
bookHidden: false
date: 2023-12-14
isCJKLanguage: true
params:
  author: lyremelody
---

## 1 什么是认证(Authentication)以及认证的目的？
**一个人的身份必需在身份验证/认证过程中被验证。身份验证/认证通常涉及一个包含两个步骤的过程**：
1. 输入公共信息(用户名、雇员号、账号或部门ID)
2. 输入私有信息(静态密码、一次性密码、PIN或数字签名)

输入公共信息是身份标识步骤，而输入私有信息则是两步骤过程中的身份验证步骤。

**身份标识和身份验证/认证所使用的每一项技术都有其优缺点，因此需要在特殊的环境中正确地对其进行评估，以便采用正确的策略。**

身份验证就是要证明“主体是谁”。

## 2 认证有哪些方法？
用于身份验证/认证的3种因素：
1. **某人知道的内容(根据知识进行身份验证/认证)**，可以是密码、PIN、母亲的娘家姓氏或密码锁。通过某人知道的内容进行身份验证实现起来往往是最经济的。这种方法的不利方面就是其他人也可能获得相关知识并能够对系统或设施进行未授权访问。
2. **某人所拥有的物品(根据所有权进行身份验证/认证)**，可以是钥匙、门卡、访问卡或证件。这种方法常用于访问设施，不过也可用于访问敏感区域或身份验证系统。该方法的确定是这些物品容易丢失或被盗，从而导致未授权访问。
3. **某人的身份(根据特征进行身份验证/认证)**，这种方法并不基于某人是火星人或者低能儿，而是基于物理特征。基于独特的物理特征对一个人的身份进行验证称为生物测定学。

**强身份验证**包含上面3种身份验证方法中的两种。也成为**双因素身份验证**。强身份验证有时也叫做多重身份验证，即使用两个或两个以上的方法进行验证。也可以使用**三因素身份验证**，即同时使用所有的验证方法。

## 3 认证有哪些协议和标准？
认证协议是一种计算机通信协议或密码协议，专门设计用于在两个实体之间传输身份验证数据。它允许接收实体通过声明认证所需的信息类型和语法来认证连接实体(例如，连接到服务器的客户端)以及向连接实体(服务器到客户端)认证自己。它是计算机网络中安全通信所需的最重要的保护层。

**认证协议主要用于在用户、业务系统、身份认证服务之间传递用户信息，告诉业务系统“此用户是谁”**。

主流的认证协议和标准有：
* JWT (JSON Web Tokens)
* OIDC (OpenID Connect)
* CAS (Central Authentication Service)
* LDAP (Lightweight Directory Access Protocol)
* Kerberos
* SAML (Security Assertion Markup Language)
* RADIUS (Remote Authentication Dial-In User Service)
* Session/Cookie
* ...

### 2.1 JWT(JSON Web Tokens)
详细见: [JWT(JSON Web Tokens)](./JWT-json-web-tokens.md)

### 2.2 OIDC(Open ID Connect)
详细见: [OIDC(Open ID Connect)](./OIDC-open-id-connect.md)

### 2.4 CAS(Central Authentication Service)
### 2.5 LDAP(Lightweight Directory Access Protocol)
详细见: [LDAP(Lightweight Directory Access Protocol)](./LDAP-light-directory-access-portocol.md)

### 2.6 Kerberos
### 2.7 SAML (Security Assertion Markup Language)
### 2.8 RADIUS (Remote Authentication Dial-In User Service)
## 2.3 什么是认证源？
认证源指的是用户在登录当前系统时，由第三方提供认证服务，系统信任第三方的认证结果。例如使用微信登录某APP。就是将微信作为认证源。

## 2.4 联邦认证
在互联网早期，你的各类账号信息分散在不同的站点和应用，这存在以下问题：
1. 每次访问一个新的站点都要注册一个新的用户名和密码账号。
2. 这个账户就仅仅被存储在这个站点。
3. 你无法在不同的站点下保持登录，用户的信息在不同的站点间也无法互通。

联邦认证通过标准协议将不同的身份提供商联合起来对用户进行认证。联邦是一种身份提供商之间的信任关系，建立联邦关系的身份提供商之间可以通过标准协议互相拉取用户信息。

### 2.4.1 为什么需要联邦认证？
联邦认证是一种分布式的身份认证，当用户在身份提供商登录时，用户可以选择到当前身份提供商信任的联邦身份提供商登录。用户可以通过联邦认证登录一个新的系统，而不必每次在新的系统中注册账号。例如现在许多网站有自己的账密注册登录方式，也有微信扫码直接登录的方式，其中的微信就是这个网站的身份联邦，用户不必填写信息注册账号，直接使用微信就可以登录。

使用联邦认证有以下好处：
1. 用户不必每次都要创建一个全新的账号。
2. 接入联邦认证后用户可以在不同的组织和站点中畅游。
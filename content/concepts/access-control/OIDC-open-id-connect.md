---
title: 'OIDC(Open ID Connect)'
linkTitle: 'OIDC(Open ID Connect)'
type: 'docs'
weight: 1133
bookFlatSection: true
bookHidden: false
date: 2023-09-12
---

# OIDC(Open ID Connect)

在 OIDC 协议中，有三种 Token：
* id_token
* access_token
* refresh_token

## 1 ID Token
OIDC(OpenID Connect)协议对OAuth 2.0协议最主要的一个扩展就是 ID Token 数据结构。

ID Token 相当于用户的身份凭证，开发者的前端访问后端接口时可以携带 ID Token，开发者服务器可以校验用户的 ID Token 以确定用户身份，验证通过后返回相关资源。

ID Token 本质上是一个 JWT Token，包含了该用户身份信息相关的 key/value 键值对，例如：
```
{
   "iss": "https://server.example.com",
   "sub": "24400320", // subject 的缩写，为用户 ID
   "aud": "s6BhdRkqt3",
   "nonce": "n-0S6_WzA2Mj",
   "exp": 1311281970,
   "iat": 1311280970,
   "auth_time": 1311280969,
   "acr": "urn:mace:incommon:iap:silver"
}
```

ID Token 本质上是一个 JWT Token 意味着：
* 用户的身份信息直接被编码进了 id_token，你不需要额外请求其他的资源来获取用户信息；
* id_token 可以验证其没有被篡改过

## 2 Access Token
Access Token 用于基于 Token 的认证模式，允许应用访问一个资源 API。用户认证授权成功后，认证授权服务会签发 Access Token 给应用。应用需要携带 Access Token 访问资源 API，资源服务 API 会通过拦截器查验 Access Token 中的 scope 字段是否包含特定的权限项目，从而决定是否返回资源。

如果你的用户通过社交账号登录，例如微信登录，微信作为身份提供商会颁发自己的 Access Token，你的应用可以利用 Access Token 调用微信相关的 API。这些 Access Token 是由社交账号服务方控制的，格式也是任意的。

**Opaque Access Token**

Opaque Access Token 是一串随机字符串，从中不能获取到任何信息，你需要将它发送到服务器进行解析。只能通过将 Token 发到服务器的方式来验证 Opaque Access Token。

**JWT Access Token**

JWT 全称为 JSON Web Token，遵循 JWT 标准。JWT 中包含了主体、受众、权限、颁发时间、过期时间、用户信息字段等内容且具备签名，不可篡改。因此无需发送到服务器，可以本地验证。

**Access Token示例**
```
eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IjF6aXlIVG15M184MDRDOU1jUENHVERmYWJCNThBNENlZG9Wa3VweXdVeU0ifQ.eyJqdGkiOiIzWUJ5eWZ2TDB4b01QNXdwTXVsZ0wiLCJzdWIiOiI2MDE5NDI5NjgwMWRjN2JjMmExYjI3MzUiLCJpYXQiOjE2MTI0NDQ4NzEsImV4cCI6MTYxMzY1NDQ3MSwic2NvcGUiOiJvcGVuaWQgZW1haWwgbWVzc2FnZSIsImlzcyI6Imh0dHBzOi8vc3RlYW0tdGFsay5hdXRoaW5nLmNuL29pZGMiLCJhdWQiOiI2MDE5M2M2MTBmOTExN2U3Y2IwNDkxNTkifQ.cYyZ6buwAjp7DzrYQEhvz5rvUBhkv_s8xzuv2JHgzYx0jbqqsWrA_-gufLTFGmNkZkZwPnF6ktjvPHFT-1iJfWGRruOOMV9QKPhk0S5L2eedtbKJU6XIEkl3F9KbOFwYM53v3E7_VC8RBj5IKqEY0qd4mW36C9VbS695wZlvMYnmXhIopYsd5c83i39fLBF8vEBZE1Rq6tqTQTbHAasR2eUz1LnOqxNp2NNkV2dzlcNIksSDbEGjTNkWceeTWBRtFMi_o9EWaHExdm5574jQ-ei5zE4L7x-zfp9iAe8neuAgTsqXOa6RJswhyn53cW4DwWg_g26lHJZXQvv_RHZRlQ
```

解析后的内容：

```
{
  "jti": "3YByyfvL0xoMP5wpMulgL",
  "sub": "60194296801dc7bc2a1b2735", // subject 的缩写，为用户 ID
  "iat": 1612444871,
  "exp": 1613654471,
  "scope": "openid email message",
  "iss": "https://steam-talk.authing.cn/oidc",
  "aud": "60193c610f9117e7cb049159"
}
```

## 3 Refresh Token
AccessToken和IDToken是JSON Web Token，有效时间通常较短。通常用户在获取资源的时候需要携带AccessToken，当AccessToken过期后，用户需要获取一个新的AccessToken。

Refresh Token用于获取新的AccessToken。这样可以缩短AccessToken的过期时间保证安全，同时又不会因为频繁过期重新要求用户登录。

用户在初次认证时，Refresh Token会和AccessToken、IDToken一起返回。你的应用必须安全地存储Refresh Token，它的重要性和密码是一样的，因为Refresh Token能够一直让用户保持登录。

以下是Token端点返回的Refresh Token：
```
{
  "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InIxTGtiQm8zOTI1UmIyWkZGckt5VTNNVmV4OVQyODE3S3gwdmJpNmlfS2MifQ.eyJqdGkiOiJ4R01uczd5cmNFckxiakNRVW9US1MiLCJzdWIiOiI1YzlmNzVjN2NjZjg3YjA1YTkyMWU5YjAiLCJpc3MiOiJodHRwczovL2F1dGhpbmcuY24iLCJpYXQiOjE1NTQ1Mzc4NjksImV4cCI6MTU1NDU0MTQ2OSwic2NvcGUiOiJvcGVuaWQgcHJvZmlsZSBvZmZsaW5lX2FjY2VzcyBwaG9uZSBlbWFpbCIsImF1ZCI6IjVjYTc2NWUzOTMxOTRkNTg5MWRiMTkyNyJ9.wX05OAgYuXeYM7zCxhrkvTO_taqxrCTG_L2ImDmQjMml6E3GXjYA9EFK0NfWquUI2mdSMAqohX-ndffN0fa5cChdcMJEm3XS9tt6-_zzhoOojK-q9MHF7huZg4O1587xhSofxs-KS7BeYxEHKn_10tAkjEIo9QtYUE7zD7JXwGUsvfMMjOqEVW6KuY3ZOmIq_ncKlB4jvbdrduxy1pbky_kvzHWlE9El_N5qveQXyuvNZVMSIEpw8_y5iSxPxKfrVwGY7hBaF40Oph-d2PO7AzKvxEVMamzLvMGBMaRAP_WttBPAUSqTU5uMXwMafryhGdIcQVsDPcGNgMX6E1jzLA",
  "expires_in": 3600,
  "id_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InIxTGtiQm8zOTI1UmIyWkZGckt5VTNNVmV4OVQyODE3S3gwdmJpNmlfS2MifQ.eyJzdWIiOiI1YzlmNzVjN2NjZjg3YjA1YTkyMWU5YjAiLCJub25jZSI6IjIyMTIxIiwiYXRfaGFzaCI6Ik5kbW9iZVBZOEFFaWQ2T216MzIyOXciLCJzaWQiOiI1ODM2NzllNC1lYWM5LTRjNDEtOGQxMS1jZWFkMmE5OWQzZWIiLCJhdWQiOiI1Y2E3NjVlMzkzMTk0ZDU4OTFkYjE5MjciLCJleHAiOjE1NTQ1NDE0NjksImlhdCI6MTU1NDUzNzg2OSwiaXNzIjoiaHR0cHM6Ly9hdXRoaW5nLmNuIn0.IQi5FRHO756e_eAmdAs3OnFMU7QuP-XtrbwCZC1gJntevYJTltEg1CLkG7eVhdi_g5MJV1c0pNZ_xHmwS0R-E4lAXcc1QveYKptnMroKpBWs5mXwoOiqbrjKEmLMaPgRzCOdLiSdoZuQNw_z-gVhFiMNxI055TyFJdXTNtExt1O3KmwqanPNUi6XyW43bUl29v_kAvKgiOB28f3I0fB4EsiZjxp1uxHQBaDeBMSPaRVWQJcIjAJ9JLgkaDt1j7HZ2a1daWZ4HPzifDuDfi6_Ob1ZL40tWEC7xdxHlCEWJ4pUIsDjvScdQsez9aV_xMwumw3X4tgUIxFOCNVEvr73Fg",
  "refresh_token": "WPsGJbvpBjqXz6IJIr1UHKyrdVF",
  "scope": "openid profile offline_access phone email",
  "token_type": "Bearer"
}
```

应用携带Refresh Token向Token端点发起请求时，认证授权服务每次都会返回相同的Refresh Token和新的AccessToken、IDToken，直到Refresh Token过期。

## 4 Access Token vs ID Token
与身份相关的Token有两种：Access Token和ID Token。

**关于形式**：
* Access Token 的格式可以是 JWT也可以是一个随机字符串。
* ID Token的格式为JWT

**关于访问鉴权**：
* 应当携带 Access Token 访问受保护的 API 接口，API 接口应该检验 Access Token 中的 scope 权限项目决定是否返回资源。例如，有一个应用使用了谷歌登录，然后同步用户的日历信息，谷歌会返回 Access Token 给应用。当应用希望读写用户的日历数据时，应用需要携带返回的 Access Token 访问谷歌的 日历 API。
* 不推荐使用ID Token来进行API的访问鉴权。

**关于认证**：
* 绝对不要使用 Access Token 做认证。Access Token 本身不能标识用户是否已经认证。Access Token 中只包含了用户 id，在 sub 字段。在你开发的应用中，应该将 Access Token 视为一个随机字符串，不要试图从中解析信息。注意Access Token不包含除id之外的任何用户信息。包含scope权限项目，用于调用受保护的 API接口。所以Access Token用于调用接口，而不是用作用户认证。
* **ID Token仅适用于认证场景**。例如，有一个应用使用了谷歌登录，然后同步用户的日历信息，谷歌会返回ID Token给这个应用，ID Token中包含用户的基本信息(用户名、头像等)。应用可以解析ID Token然后利用其中的信息，展示用户名和头像。**在使用 ID Token 之前应该先验证合法性**。每个ID Token的受众(aud 参数)是发起认证授权请求的应用的ID (或编程访问账号的AK)。

## 参考资料
1.  [Authing - 概念](https://docs.authing.cn/v2/concepts/)
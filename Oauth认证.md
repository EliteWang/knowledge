## Oauth1.0 VS Oauth2.0
oauth1.0的每个token都有一个加密，2.0不需要，oauth2.0要求使用https协议。

## oauth的概念
OAUTH是一种开放协议，能为桌面程序或bs程序提供一种简单的标准方式去访问需要用户授权的API服务，并且任何第三方都可以使用oauth认证服务

## 为什么会出现oauth，它解决什么样的问题？
随着大量开放平台的出现，建立在开放平台之上的各种第三方应用也大量冒出，出于对安全性和统一标准的要求，出现了oahth协议。比如，开发一个新浪微博的第三方的应用，需要访问新浪微博提供的API，但是使用这些API需要授权验证，怎么授权验证，这时就用到了oauth，这个过程第三方开发者是拿不到用户信息的，这里只是授权可以干某事。

## oauth2.0的授权过程：

	1，用户到授权服务器，请求授权，返回授权码（AuthorizationCode）
	2，客户端由授权码到授权服务器换取访问令牌（Access Token）
	3，用访问令牌去访问得到的授权的资源。

## oauth1.0的授权过程：

	1，客户端到授权服务器请求一个授权令牌
	2，引导用户到授权服务器请求授权
	3，用访问令牌到授权服务器换取访问令牌
	4，用访问令牌去访问得到的授权资源。
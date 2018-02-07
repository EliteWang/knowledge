# Browser对象
## window
### window.location.hash
	获取url中#号以后（包括#号）的内容


### window.onhashchange
	html5新增事件
	事件在当前页面URL中的hash值发生改变时触发  
	事件在当前URL的锚部分（以#号开始的部分）发生改变时触发
	这两种说法，
### location.hash
	window.location是一个只读属性，返回一个Location对象，包含文档当前地址的相关信息。


## 浏览器渲染的过程

1，浏览器解析三个东西

	1，html/SVG/Xhtml，解析后产生一个dom tree。
	2，CSS，解析CSS规则，会产生CSS规则树。
	3，Javascript，主要通过dom api 和css api来操作dom tree和css tree。

2，解析完成后，浏览器通过dom tree和css rule tree构造 rendering tree

3，调用操作系统native gui的api绘制。

这三个步骤并不是按部就班的执行的，而是交替并发执行的。

repaint：样式的变化，会触发repaint操作

reflow：元件的大小变化，触发reflow操作


# http
## http url中的#号
[#的意义](http://www.ruanyifeng.com/blog/2011/03/url_hash.html)  

*	#代表网页中的一个位置，其右边的字符就是该位置的标识符
*	#是指导浏览器动作的，对服务器端完全无用
*	改变#后面的部分，浏览器只会滚动到相应的位置，不会重新加载网页
*	window.location.hash读取#的值
*	onhashchange事件，html5新增事件，当#值发生变化时，会触发改事件
*	#可以理解为占位符


## http get/post 请求参数长度误解

	http Get请求的数据大小长度并没有限制。http协议规范没有对url长度进行限制。这个限制是特定的浏览器及服务器对它的限制。

	post请求数据也是没有大小限制，http协议也没有进行大小限制，起限制作用的是服务器的处理程序的处理能力。如：在tomcat下可以取消post大小限制（tomcat默认2m）
	在connector里面加上maxPostSize=0代表无限制。
	

## http请求头

	1 POST /inner/index.html HTTP/1.1
	2 Host: localhost:8080
	3 Connection: keep-alive
	4 Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
	5 User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 
	(KHTML, like Gecko) Chrome/38.0.2125.122 Safari/537.36 SE 2.X MetaSr 1.0
	6 Accept-Encoding: gzip,deflate,sdch
	7 Accept-Language: zh-CN,zh;q=0.8
	
	8 name=ligen&age=21

2：请求方法-uri-协议（版本），/inner/index.html请求的资源，一般是相对于根路径，所以以“/”开头  
2-7：请求头  
8：请求实体


## http响应格式

	1 HTTP/1.1 200 OK
	2 server:tomcat
	3 Content-Type:text/html
	4 Content-Length:100
	
	<html>
	......
	</html>

1：指定了协议和版本，状态码，响应部分与请求




# https

## 对称加密

	双发加密和解密用的是同一个密钥

## 非对称加密（RSA）
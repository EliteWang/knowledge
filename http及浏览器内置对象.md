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



# http
## http url中的#号
[#的意义](http://www.ruanyifeng.com/blog/2011/03/url_hash.html)  

*	#代表网页中的一个位置，其右边的字符就是该位置的标识符
*	#是指导浏览器动作的，对服务器端完全无用
*	改变#后面的部分，浏览器只会滚动到相应的位置，不会重新加载网页
*	window.location.hash读取#的值
*	onhashchange事件，html5新增事件，当#值发生变化时，会触发改事件
*	#可以理解为占位符

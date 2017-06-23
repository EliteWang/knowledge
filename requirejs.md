


## requirejs
[requirejs](http://www.ruanyifeng.com/blog/2012/11/require_js.html)  
解决的问题:  

	1，解决模块之间的依赖关系。
	2，实现js的异步加载，避免网页失去响应。

使用的方法：
	
	<script src="js/require.js" defer async="true" data-main="js/main.js"></script>

defer和async:这两个都说明该文件需要异步加载，但是IE只支持defer。	
data-main:网页程序的主模块，整个网页的入口代码。

定义的三个变量：  
	
	define，require，requirejs
		1.define用来定义一个模块  
		2.require===requirejs，用来加载所定义的模块，并执行加载完后的回调函数。


## 异步、同步
XmlHttpRequest支持异步和同步，出于性能，异步优于同步


### requirejs和require
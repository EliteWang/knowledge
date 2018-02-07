## javaee

### servlet容器
### web.xml中的mime-mapping的作用
Web应用程序包含一些不常用的文件，元素将mime类型映射到扩展名, 用于规定下载格式。

### servlet
##### 生命周期

##### 核心类与接口
``ServletContext``

``ServlerConfig``

``ServletRequest``  
1,request.getParameter()、request.getInputStream()和request.getReader()


``ServletResponse``

##### Form表单处理
1,一个属性enctype，有两种属性值

	enctype＝application/x-www-form-urlencoded 或multipart/form-data



##### Listener（监听器）

##### Filter（过滤器）

##### Interceptor（拦截器）

	依赖的技术是java中的动态代理

	1，业务组件：被代理或被拦截的对象
	2，代理处理器：实现了InvocationHandler的一个对象
	3，代理对象：Proxy对象
	4，拦截器：普通的javabean，在调用业务方法之前或之后，会自动拦截并执行自己的一些方法
	5，客户端：执行业务处理的入口

##### Get和Post请求

##### session 

##### cookie
 
### jsp
##### 内置对象

##### 指令

##### 自定义标签 

### 文件上传下载
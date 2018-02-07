RESTFUL:
	
	软件研究主要关注软件设计的分类、设计方法的演化。
	网络研究主要关注系统之间的通信行为的细节、如何改进特定通信机制的表现。

REST：Representational State Transfer

	Representational:表现层，指的是"资源"的表现层，“资源”是一种信息实体，有很多种表现形式。

	State Transfer：状态转化。http协议，是一个无状态的协议，意味着，所有的状态都保存在服务端
	。如果客户端要操作服务端，必须通过某种手段，让服务器发生“状态转化”，而这种转化是建立在表现层之上的，所以就是“表现层的状态转化”。


什么是RESTFul架构：
	
	1，每一个URI代表一种资源
	2，客户端和服务器之间，传递这种资源的某种表现层。
	3，客户端通过四个HTTP动词（GET，PUT，DELETE，POST），对服务端资源进行操作，实现
		“表现层状态转化”。

对RESTful的误解：
	1，URI中包含动词
	2，URI中包含版本号，不同版本号应该对应同一种资源。

路径（Endpoint）:

	路径又称"终点"（endpoint），表示API的具体网址。
	在RESTful架构中，每个网址代表一种资源（resource），所以网址中不能有动词，只能有名词，
	而且所用的名词往往与数据库的表格名对应。一般来说，数据库中的表都是同种记录的"集
	合"（collection），所以API中的名词也应该使用复数。

http动词：

	GET（SELECT）：从服务器取出资源（一项或多项）。
	POST（CREATE）：在服务器新建一个资源。
	PUT（UPDATE）：在服务器更新资源（客户端提供改变后的完整资源）。
	PATCH（UPDATE）：在服务器更新资源（客户端提供改变的属性）。
	DELETE（DELETE）：从服务器删除资源。

状态码：

	200 OK - [GET]：服务器成功返回用户请求的数据，该操作是幂等的（Idempotent）。
	201 CREATED - [POST/PUT/PATCH]：用户新建或修改数据成功。
	202 Accepted - [*]：表示一个请求已经进入后台排队（异步任务）
	204 NO CONTENT - [DELETE]：用户删除数据成功。
	400 INVALID REQUEST - [POST/PUT/PATCH]：用户发出的请求有错误，服务器没有进行
											新建或修改数据的操作，该操作是幂等的。
	401 Unauthorized - [*]：表示用户没有权限（令牌、用户名、密码错误）。
	403 Forbidden - [*] 表示用户得到授权（与401错误相对），但是访问是被禁止的。
	404 NOT FOUND - [*]：用户发出的请求针对的是不存在的记录，服务器没有进行操作，
						该操作是幂等的。N次变换和1次变换的结果相同，是一个数据概念。
	406 Not Acceptable - [GET]：用户请求的格式不可得（比如用户请求JSON格式，
								但是只有XML格式）。
	410 Gone -[GET]：用户请求的资源被永久删除，且不会再得到的。
	422 Unprocesable entity - [POST/PUT/PATCH] 当创建一个对象时，发生一个验证错误。
	500 INTERNAL SERVER ERROR - [*]：服务器发生错误，用户将无法判断发出的请求是否成功。

幂等性：

	get、put、delete请求方式都是幂等性的，幂等性的意思是指，请求一次和请求多次的结果是一样的。

Restful API设计：


	Hypermedia，即返回结果中提供链接。
## zookeeper
### zookeeper是什么？

	zookeeper is a service for coordinating processes of distributed applications

### zookeeper有哪些应用场景？
	
	zookeeper is a centralized service for maintaining configuration information,
	naming,providing distributed synchronization and providing group service.

	configuration information(配置管理):
	naming(名字服务):
	distributed synchronization(分布式锁）:
	group service(集群管理):

### 什么是分布式协调服务？  

	可以想象一下十字路口，交通协管员，指挥交通，就是协调服务。
	
	那分布式系统为啥需要协调服务哩？
	在并发环境中，为了避免多个线程同时操作一个共享数据，造成数据损坏，就必须依赖锁这样的协调机制。

### zookeeper的原理是啥？

### zookeeper三种安装方式
	
	单机、伪分布、分布

### zookeeper的节点类型

	1，PERSISTENT（持久化目录节点，客户端与zookeeper断开后，节点依旧存在）
	2，PERSISTENT_SEQUENTIAL（持久化顺序编号目录节点）
	3，EPHEMERAL（瞬时目录节点，客户端与zookeeper断开后，节点不存在）
		利用这一特性可以监控集群中出故障的机器
	4，EPHEMERAL_SEQUENTIAL（临时顺序编号目录节点)


### zookeeper通知机制原理

	客户端向服务端注册一个Watcher，并添加到客户端WatcherManager中，服务端触发Watcher事件，服务端向客户端发送通知，客户端线程从WatcherManager中取出Watcher对象，执行回调逻辑。


### zookeeper启动
	
	zkServer.sh start

### zookeeper 客户端连接
	
	zkCli.sh -server ip:port


### 与zookeeper相类似的技术有哪些？


### 这些技术的优缺点是啥？
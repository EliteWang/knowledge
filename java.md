# java
[java](http://www.importnew.com/23549.html#comment-542805)

## 六大原则

	* 单一职责:高内聚，低耦合
	* 开闭原则:扩展开放，修改关闭
	* 里氏替换
	* 依赖倒置
	* 接口隔离
	* 迪米特 

## CopyOnWriteArrayList



## 共享变量

	在多个线程之间能够被共享的变量

## 锁
两种主要特性：

	1，互斥性：一次只允许一个线程持有某个特定的锁
	2，可见性


#java中的锁

## 内置锁

### volatile



轻量级的synchronize，主要用来修饰变量，保证共享变量的“可见性”，可见性的意思是：当一个线程修改一个共享变量时，另外一个线程可以读到修改的值



### synchronized



## 由java.util.concurrent.locks.Lock派生出来的锁
# aop

	软件工程有一个基本的原则：关注点分离（Concern Separation），
	就是把不同的问题交给不同的部分去解决，每部分专注于自己解决的问题。其实就是一种“分治”或者“分类”的思想，

	人解决复杂问题的能力是有限的，为了控制复杂性，解决问题时都需要对问题进行拆解，
	拆解的同时建立各部分之间的关系，各个击破。

## 什么是aop？

	aop其实就是一种关注点分离的技术。
	

## 为什么会出现了aop？

	开发中代码主要就是实现某种业务逻辑或业务功能，
	但是往往在实现业务逻辑的过程中，会先做一些额外的东西，
	比如事务，日志，缓存等通用化的功能，往往不能专注于业务逻辑，而且每个通用化功能还要和业务功能混合在一起。
	为了将业务功能的关注点和通用功能的关注的功能分离开，就出现了AOP技术。

	这些通用化功能的代码实现，就是切面（Aspect）。

	业务代码和切面代码分开后，责任就明确了，开发者就能各自专注解决问题了，设计更加高内聚低耦合！

	代码分开之后，如何才能保证功能的完整性？

	那肯定是将两部分的代码，合并在一起，专业术语叫“织入”。
	
## 织入（Weave）

	织入的三种方式：
		
		1，编译时织入：顾名思义，在编译时期，将切面代码织入进来，生成完整功能的字节码。
						这就需要特殊的java编译器，AspectJ。
		2，类加载时织入：在java字节码加载时，把切面字节码融合进来。
		3，运行时织入：在运行时，通过动态代理的方式，调用切面代码增强业务功能。


## AOP的使用场景

* what
		
	指切面

* where
* when

	

	


## 什么是hash
	hash（散列），是将任意长度的数据映射到有限长度的域上。大白话，将一串数据m进行杂糅，输出另一段固定长度的数据h。
* 抗碰撞能力
* 抗篡改能力，在用到用hash进行管理的数据结构中，如hashmap，hash值（key）存在的目的是加速键值对的查找。hash出来的key，只要保证value均匀的放在不同的桶中就行了。
* 

## hash表
[hash表算法](http://www.cnblogs.com/dolphin0520/archive/2012/09/28/2700000.html)  
[hash表结构](http://www.cnblogs.com/jiewei915/archive/2010/08/09/1796042.html)
	

## hashcode()
*	[相关文章](http://www.importnew.com/18851.html)
*	包含容器类型的程序设计语言，都会涉及到hashcode。  
*	作用
	> 为了配合基于散列的集合一起运行正常，散列集合HashMap、HashSet、HashTable。  
	> 这些集合中不允许有重复的数据，是怎么判断数据是否重复的？  
	> 

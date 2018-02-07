# mysql 
## exists与not exists
	exists用于检查子查询是否至少会返回一行数据
	not exists与exists相反


## case when then else end

## 索引

什么是索引 

	索引是帮助mysql高效获取数据的数据结构，可以得出索引的本质：索引是数据结构。
	
	每种查找算法都只能应用于特定的数据结构之上，数据库中的数据结构又不满足于这些算法的数据结构
	怎么处理？

	在数据之外，数据库系统还维护着满足特定查找算法的数据结构，这些数据结构以某种方式引用数据 

索引原理

	通过不断缩小想要数据的范围筛选出结果，类似的例子，词典、书的目录

索引的存储分类

	> BTree 
	> Hash
	> R-Tree
	> Full-text

添加索引

	1，alter table add index index_name(column_list)

	2,create index index_name on table(column_list)
	
建索引几大原则：


[mysql十大错误](http://database.51cto.com/art/201707/546206.htm?edm)

## 查看mysql中的变量

1，show variables like '%max_connection%'; 查看mysql的最大连接数

2，show variables like '%innodb_thread_concurrency%';查看innodb的并发处理数量，0代表无限制


## 忘记数据库密码的问题：

解决办法：
1，启动mysql时,可以不用输密码进入

	/usr/local/mysql/bin/mysqld_safe --defaults-file=/etc/my.cnf --skip-grant-tables &

2， 进入数据库后，执行，设置用户密码：
	
	update mysql.user set password=password('root123') where user='root'; 

## truncate delete
1，truncate会清空自增的初始值，自增属性值会从1开始记录，delete不会。

	注意：尽量不要使用truncate清空表


## 表名大小写参数

	lower_case_table_names = 0


## emoji表情入库出错
1，解决思路

	针对表情插入的问题，一定是字符集的问题

2，解决办法
	
	vim /etc/my.cnf 
	[mysqld] 
	init-connect='SET NAMES utf8mb4' 
	character-set-server=utf8mb4 

	注：utf8mb4是utf8的超集


## mysql中的日期比较
	
	如果有字符串，一定是要把字符串转为日期再比较

	如果用了日期函数，那么作用在这个日期列上的索引就会失效不起作用，这时就得用上between and这两个关键字。




## 表设计

除了一些表中通用的字段之外，还需要思考什么来完善这个设计？业务量？查询？
什么才算是好的设计？可以应对业务的变化？
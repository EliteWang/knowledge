## jvm 参数  

* 查看jvm参数

		1，java -XX:+PrintFlagsInitial 显示默认jvm参数配置
		2，java -XX:+PrintFlagsFinal 显示jvm设置后的配置
		3，jinfo [option] pid 
		4，java -XX:+PrintCommandLineFlags 显示的是jvm初始化完毕后，所有跟默认值不同的参数及他们的值
		5，java -XX:+PrintGC
		6，java -XX:+PrintGCDetails

* 堆

		整个堆的大小 = 年轻代（Eden和两个Survivor） + 年老代 + 持久代
			（sun官方推荐年轻代的大小应设置为整个堆大小的3/8）
		-XX:NewRatio=4:设置年轻代与年老代的比值，意思是年轻代与年老代所占比值是1:4，年轻代占整个堆的1/5
		-XX:SurvivorRatio=4:设置年轻代中Eden和两个Survivor区的大小比值，意思是两个Survivor区和一个Eden区的比值为2:4
		-XX:MaxPermSize=16m:设置持久代的大小为16m
		-XX:MaxTenuringThreshold=0,设置垃圾最大年龄，如果设为0，则年轻代对象不经过Survivor区，直接进入年老代

* jvm

		-Xmx3550m:设置Jvm最大可用内存，默认为物理内存的1/4
		-Xms3550m：设置Jvm初始内存，可以和最大内存一样，避免垃圾回收之后，jvm重新分配内存,默认为物理内存的1/64
		-Xmn2g：设置年轻代大小为2g ，最好让-Xmn值约等于-Xmx的1/3[2]
		-Xss128k:设置每个线程的堆栈大小

* 非堆

		-XX:PermSize:设置非堆内存的初始值,默认为物理内存的1/64

* 常见jvm配置

		堆设置 
		-Xms:初始堆大小 
		-Xmx:最大堆大小 
		-XX:NewSize=n:设置年轻代大小 
		-XX:NewRatio=n:设置年轻代和年老代的比值.如:为3,表示年轻代与年老代比值为1:3,年轻代占整个年轻代年老代和的1/4 
		-XX:SurvivorRatio=n:年轻代中Eden区与两个Survivor区的比值.注意Survivor区有两个.如:3,
							表示Eden:Survivor=3:2,一个Survivor区占整个年轻代的1/5 
		-XX:MaxPermSize=n:设置持久代大小收集器设置 
		-XX:+UseSerialGC:设置串行收集器 
		-XX:+UseParallelGC:设置并行收集器 
		-XX:+UseParalledlOldGC:设置并行年老代收集器 
		-XX:+UseConcMarkSweepGC:设置并发收集器垃圾回收统计信息 
		-XX:+PrintGC 
		-XX:+PrintGCDetails 
		-XX:+PrintGCTimeStamps 
		-Xloggc:filename并行收集器设置 
		-XX:ParallelGCThreads=n:设置并行收集器收集时使用的CPU数.并行收集线程数. 
		-XX:MaxGCPauseMillis=n:设置并行收集最大暂停时间 
		-XX:GCTimeRatio=n:设置垃圾回收时间占程序运行时间的百分比.公式为1/(1+n)并发收集器设置 
		-XX:+CMSIncrementalMode:设置为增量模式.适用于单CPU情况. 
		-XX:ParallelGCThreads=n:设置并发收集器年轻代收集方式为并行收集时,使用的CPU数.并行收集线程数.
	

		 
	
## 查看正在运行的jvm参数

	jcmd，是jdk7开始引入的命令行工具


查看jvm进程的PID：
	
	jcmd -l

查看jvm运行的参数：

	jcmd PID VM.flags

## permanent generation

	The permanent generation is used to hold reflective data of the VM itself such as class 
	objects and method objects. These reflective objects are allocated directly into the
	permanent generation, and it is sized independently from the other generations.

	it holds meta-data describing user classess Examples of such meta-data are objects
	describing classes and methods and they are stored in the Permanent Generation.  

## 监控垃圾回收的几种方式

	1，jstat
	
		jstat -<options> <PID> <second> <times>
		第三个参数是毫秒，second毫秒出现times次


	2，jconsole
	


## java.lang.OutOfMemoryError: GC overhead limit exceeded

这个是jdk1.6,1.7默认启动的时候，启用了该特性。这个的意思是，将要抛出内存溢出异常，这个是jvm的一个推断，如果垃圾回收耗费了较长的时间（98%），但是回收了较少的内存（2%），jvm就会抛出该异常

垃圾回收器



## java.lang.StackOverflowError





## jvm工具

### jstat

	1，查看类的加载及卸载
	2，查看新生代、老生代、持久代的容量及使用情况
	3，查看新生代、老生代、持久代的垃圾收集情况，包括垃圾收集次数及垃圾回收所占用的时间
	4，查看新生代中eden和survivor区中的容量及分配情况


### jmap

	打印出某个java进程的，所有对象的情况。可以输出所有内存中对象的工具

	64位机上使用需要使用如下方式：
	jmap -J-d64 -heap pid


### jinfo

	输出并修改运行时的java options


### jhat

	分析java堆的对象，包括对象的数量，大小等等



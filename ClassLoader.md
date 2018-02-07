动态代理--->ClassLoader--->ClassPath

```ClassLoader的类加载机制？```

双亲委托机制，每个classLoader的实例都有一个父类加载器的引用，Bootstrap ClassLoader除外，当一个ClassLoader要加载某个class的时候，会把这个任务委托给他的父类加载器，这个过程是由上到下依次检查的，首先由最顶层的类加载器Bootstrap ClassLoader视图加载，如果没有加载到，则把任务委托给Extension ClassLoader，如果也没加载到，则委托给App ClassLoader，如果还没加载到，则返回给委托的发起者，由它到指定的文件系统或网络等url加载该类。如果都没有加载到这个类时，会抛出ClassNotFoundException,加载到这个类时，将会生成一个类的定义，并将它加载到内存当中，最后返回这个类在内存中的Class实例对象。

```为什么使用双亲委托机制来加载？```

可以避免重复加载的问题，父ClassLoader已经加载过，子ClassLoader无需加载.

``` ClassLoader在搜索类的时候，是如何判断两个class是否相同呢？ ```

不仅要判断两个类名是否相同，而且还要判断这两个类是不是同一个类加载器加载的。

```classpath:```

	The class path is the path that the Java runtime environment 
	searches for classes and other resource files. 
	就是用来指定.java文件编译后生成的.class文件目录的。

```System.getSecurityManager()安全管理器```

	用来控制执行权限，默认安全管理器是没有安装的，
	需要在运行时添加参数：-Djava.security.manager，这时安全管理器就被装上了。
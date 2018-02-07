# linux命令
## free、/proc目录下面查看linux的内存情况
	
	free
	cat /proc/cupinfo
	cat /proc/meminfo
		
## 查看linux版本

	cat /proc/version、cat /etc/issue

## 查看磁盘空间
	
	df -m
	
## 查看当前文件夹大小

	du -sh

## 查看所有用户列表

	cat /etc/passwd

## 查看用户组
	
	cat /etc/group

## 远程拷贝文件夹

	scp -r /opt root@192.168.12.1:/opt

## 重命名

	mv a.txt a.txt.bak

## 本地拷贝文件夹

	cp -r source dest

## 查看防火墙

	service iptables status

	启动
	service iptables start

## 查找
	
	find / -name 查找的目录或名字
	whereis 	


## 更新服务器时间

	date -s yyMMdd：设置年月日
	date -s HH:mm:ss ：设置当前时间

	ntpdate -u 210.72.145.44 :网络时间同步命令

	中国国家授时中心：210.72.145.44
	NTP服务器(上海) ：ntp.api.bz

## 解压

	**tar**
		-x 解压
		-c 压缩
		-t 查看内容
	x、c、t是独立的命令 tar后面的呃参数中只能有一个

	-z：有gzip属性的
	-j：有bz2属性的
	-Z：有compress属性的
	-v：显示所有过程
 
	-f：使用档案名字，切记，这个参数是最后一个参数，后面只能接档案名。

	*.tar：使用tar -xvf解压
	*.gz：使用gzip -d或gunzip 解压
	*.tar.gz和*.tgz：使用tar -xzf解压
	*.bz2：使用 bzip2 -d 或 bunzip2 解压
	*.tar.bz2 : 使用 tar -xjf解压
	*.Z：使用uncompress解压
	*.tar.Z：使用tar -xZf解压
	*.rar：使用unrar e解压
	*.zip：使用unzip 解压
	
	


## 压缩

	tar -cvf jpg.tar *.jpg //将目录里所有jpg文件打包成tar.jpg 

	tar -czf jpg.tar.gz *.jpg   //将目录里所有jpg文件打包成jpg.tar后，并且将其用gzip压缩，生成一个gzip压缩过的包，命名为jpg.tar.gz

	tar -cjf jpg.tar.bz2 *.jpg //将目录里所有jpg文件打包成jpg.tar后，并且将其用bzip2压缩，生成一个bzip2压缩过的包，命名为jpg.tar.bz2

	tar -cZf jpg.tar.Z *.jpg   //将目录里所有jpg文件打包成jpg.tar后，并且将其用compress压缩，生成一个umcompress压缩过的包，命名为jpg.tar.Z

	rar a jpg.rar *.jpg //rar格式的压缩，需要先下载rar for linux

	zip jpg.zip *.jpg //zip格式的压缩，需要先下载zip for linux



## 安装


	rpm：软件包管理命令工具
	options：
		-a：查询所有套件；
		-i<套件档>或--install<套件档>：安装指定的套件档；
		-v：显示指令执行过程；
		-h或--hash：套件安装时列出标记；
	
		

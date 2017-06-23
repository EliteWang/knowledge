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



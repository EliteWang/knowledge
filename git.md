#git
## 创建git仓库
	
	git init

## 往git仓库中添加文件

	git add

	将目录下面所有文件添加到仓库中：git add .

## 提交文件
	
	git commit -m "";

## 对比文件

	git diff

## 查看历史

	git log

## 工作区，缓存区


## 添加到githup中

	初始化git仓库，并将需要的文件添加到仓库中之后，
	本地的仓库需要和githup仓库建立连接:
	git remote add origin https://github.com/EliteWang/knowledge.git
	可以从远程仓库先更新一下：
	git pull origin master
	提交本地文件到githup：
	git push -u origin master


## git 远程仓库

	添加远程仓库：
		git remote add [shortname] [url]
	查看远程仓库
		git remote -v[verbose详细的意思]
	从远程仓库抓取数据
		git fetch [remote-shortname]
	
	

	


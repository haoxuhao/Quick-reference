安装：

	yum install screen

创建一个screen：

	screen -S dataprocess 

进入：

	screen -ls
	screen -r dataprocess

强行进入：

	screen -r -D dataprocess

结束一个screen：
	
	ctrl+d
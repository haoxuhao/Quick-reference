### vnc简介
	虚拟桌面服务（Virtual Network Computing）

### vnc服务搭建
暂略

### vnc使用命令
	vncserver -kill :1 #杀死一个桌面
	vncserver #初始启动设置密码，密码小于8位
	vncserver :2 #指定启动一桌面
	vim ~/.vnc/xstartup #修改桌面软件
	vncconfig & #解决复制粘贴问题
	vim /usr/bin/vncserver #修改配置信息，分辨率，端口等
	vncpasswd #设置密码

### 常见错误与解决方案


1. vncviewer 使用的时候如果点击连接后卡了很久然后显示超时的情况是由于防火墙的关系。
> iptables -A INPUT -p tcp --dport 30001 -j ACCEPT


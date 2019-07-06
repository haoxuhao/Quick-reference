### 启动
svnserve -d -r /home/data/svn/ #一定要是项目的目录
### 关闭
ps -ef|grep svnserve && kill
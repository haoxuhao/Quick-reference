# Install
```shell
apt-get install openssh-server
/etc/init.d/ssh status  #confirm ssh status
```

# root login
```shell
vim /etc/ssh/sshd_config
PermitRootLogin yes #找到并去掉该行的注释即可
# :wq 
```

# 免密码登录
```
# 1 create public key on your own mechine
ssh-keygen -t rsa  #一路回车即可

# 2 上传
scp id_rsa.pub username@ip:/home/username

# 3 登录到远程服务器
ssh username@ip

#4 添加到.ssh/authorized_keys，没有会自动创建一个文件
cat id_rsa.pub >>.ssh/authorized_keys
```

# 登录到指定端口
```
ssh 到指定端口  ssh -p xx user@ip      xx 为 端口号    user为用户名   ip为要登陆的ip
```

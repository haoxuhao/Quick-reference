# Some shell skills
### awk 分割字符串
awk -F, '{print $1,$2,$4}' 

### 循环执行指令
`for i in {1..10}; do echo "Hello, World $i"; done`

### 将文本文件里的文件路径对应的文件复制到另一个目录中去
`cat <list file> | xargs -i cp {} <dst dir>` 

### 提交后台运行的指令
nohup command & 
显示当前username的所有进程
ps -u username

### GPU 驱动相关
nvidia-smi
watch -n 1 nvidia-smi
sudo nvidia-smi -pm 1


### 文件存储有关命令
//查看文件的大小
du -h
df -h

### 重定向
cat file > newfile //cat 将file中的内容输出的标准输出，> 将标准输出重定向到了newfile中， >>追加, >覆盖

\>log 1>&2 //1，2都定向到log文件中


### others
ln -s <src_file> <link_file>

wget --user=xxx --password=xxx http://xxx.xxx.xxx.xxx/cdh3/script/ntp-.sh //带用户名及密码的下载

git config --global http.sslVerify false//在Ubuntu下使用git clone等出错很可能都是这个的问题

sudo vim ~/.bashrc //编辑本用户的目录

source ~/.bashrc //使用户目录生效

解决windows文件换行符‘\r\n’的问题
vi M.txt
:set fileformat=unix
:wq

移动当前文件下的所有.jpg文件到指定目录
sudo find . -name "*.jpg" -exec mv {} <dst_dir>



## 简介
tmux 的设计哲学与vim类似，也有命令模式和非命令模式．
基本的结构是:

- 服务
	- sessions
		- windows
			-  panels

服务一般是创建会话的时候就自动创建好了，一个服务包含多个会话，一个会话可以放置多个窗口，一个窗口可以进行分屏产生多个的panel．
## 速查链接
<a href="http://louiszhai.github.io/2017/09/30/tmux/#%E6%96%B0%E5%BB%BA%E4%BC%9A%E8%AF%9D" target="_blank">link</a>

## 常用命令
``` shell
# 新增
$ tmux
# OR
$ tmux new -s <your_session_name>
$ tmux new -s train -d #后台创建，可以在会话里面创建多个后台session
# session 列表
$ tmux ls
# 重新連線 session
$ tmux a -t 0
# OR
$ tmux a -t <session_name>
# 刪除 session
$ tmux kill-session -t 0
# OR
$ tmux kill-session -t <session_name>
# OR
$ tmux kill-session -a # 全部
# 刪除 tmux server
$ tmux kill-server
# 重新命名 session
$ tmux rename-session -t 0 <new_session_name>
```
## 快捷键操作
以下所有快捷键均是在命令模式下使用的，根据配置文件的命令模式进入键不同，每个人有所差异，某人为Ctrl+b，我的为Ctrl+j
### 会话相关
- 切换会话: `s #上下选择并enter即可`

### 窗口相关
- 创建窗口：`c`
- 切换指定窗口：`数字键`
- 前一个窗口：`p`
- 后一个窗口：`n`
- 窗口命名：`,`

### panel 管理
- 竖分屏：`h`
- 横分屏：`v`
- 屏之间切换: `o #也可以直接鼠标控制，需要配置鼠标功能`
- panel全屏：`z #再按恢复`
 
## 配置

### 鼠标支持与复制粘贴
- `set-option -g mouse on`
- 按住shift进入了原terminal模式，可以右键复制或者粘贴

### 配置文件 ~/.tmux.conf

```shell
set-option -g prefix C-j

# Mouse
# 
set-option -g -q mouse on

# Easy split pane commands
#
bind h split-window -h
bind v split-window -v
unbind '"'
unbind %

# Status bar --------------------{{{ 
set -g status-bg black
set -g status-fg white
set-option -g status-justify centre
set-option -g status-left '#[fg=cyan][#{session_name}]'
set-option -g status-left-length 5
set-option -g status-right '#[fg=white,bg=default]%H:%M #[default] #[fg=blue]%Y-%m-%d%a'

# panel --------------------{{{ 
set-option -g pane-border-fg colour27
set-option -g pane-active-border-fg colour9
set-option -g display-panes-active-colour blue
set-option -g display-panes-colour brightred
# }}}
```

### 重新加载配置文件
在tmux 会话中使用`tmux source-file ~/.tmux.conf` 激活配置
重启的tmux会自动加载配置

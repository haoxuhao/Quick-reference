# Some useful tmux command

#### 重新加载配置文件
tmux source-file ~/.tmux.conf

#### 鼠标支持与复制粘贴
> set-option -g mouse on

shift+ctr c copy
shift+ctr v past


#### ~/.tmux.conf

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
set-option -g status-left-length 25
set-option -g status-right '#[fg=white,bg=default]%H:%M #[default] #[fg=blue]%Y-%m-%d%a'

# panel --------------------{{{ 
set-option -g pane-border-fg colour27
set-option -g pane-active-border-fg colour9
set-option -g display-panes-active-colour blue
set-option -g display-panes-colour brightred
# }}}
```

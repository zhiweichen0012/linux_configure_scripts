# Linux Configure Scripts

A script to configure a new machine. 

## 📋 Table of content
  1. [Oh My Zsh](#1)
  2. [Tmux](#2)

> Updating ~

## ⭐ Oh My Zsh <a name="1"></a> 

> Install zsh
```bash
$ sudo apt install zsh
$ chsh -s $(which zsh)
```
> Install oh-my-zsh
```bash
$ sudo apt install git
$ sh -c "$(wget -O- https://install.ohmyz.sh/)"

# Refer to https://github.com/ohmyzsh/ohmyzsh
```
> Install myys_v2 theme
```bash
$ git clone https://github.com/zhiweichen0012/myys.zsh-theme.git
$ cd myys.zsh-theme & cp myys_v2.zsh-theme ~/.oh-my-zsh/themes/
$ vim ~/.zshrc 
# Set ZSH_THEME to myys_v2, i.e., ZSH_THEME="myys_v2"
$ source ~/.zshrc

# Refer to https://github.com/zhiweichen0012/myys.zsh-theme
```
> Install powerlevel10k theme (optional)
```bash
$ git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
# For China
$ git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

$ vim ~/.zshrc 
# Set ZSH_THEME to powerlevel10k, i.e., ZSH_THEME="powerlevel10k/powerlevel10k"
$ source ~/.zshrc

# Refer to https://github.com/romkatv/powerlevel10k
```

> Install plugins

- zsh-autosuggestions
```bash
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# For China
$ git clone https://github.moeyy.xyz/https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Add the plugin
$ vim ~/.zshrc
plugins=( [plugins...] zsh-autosuggestions)
$ source ~/.zshrc

# Refer to https://github.com/zsh-users/zsh-autosuggestions
```

- zsh-syntax-highlighting
```bash
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# For China
$ git clone https://github.moeyy.xyz/https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Add the plugin
$ vim ~/.zshrc
plugins=( [plugins...] zsh-syntax-highlighting)
$ source ~/.zshrc

# Refer to https://github.com/zsh-users/zsh-syntax-highlighting
```


## ⭐ Tmux <a name="2"></a> 

```bash
$ sudo apt install tmux
```

```bash
$ cd
$ git clone https://github.com/gpakosz/.tmux.git
$ ln -s -f .tmux/.tmux.conf
$ cp .tmux/.tmux.conf.local .

# Refoer to https://github.com/gpakosz/.tmux
```

```
# vim .tmux.conf.local

# CHANGE
tmux_conf_copy_to_os_clipboard=true

set -g mouse on

set -gu prefix2
unbind C-s
unbind C-b
set -g prefix C-s
bind C-s send-prefix

# ADD
bind-key c new-window -c "#{pane_current_path}"
bind-key \\ split-window -h -c "#{pane_current_path}"
bind-key - split-window -c "#{pane_current_path}"
```

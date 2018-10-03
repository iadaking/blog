设置默认shell为iterm2

To activate the syntax highlighting, add the following at the end of your .zshrc:
  source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

If you receive "highlighters directory not found" error message,
you may need to add the following to your .zshenv:
  export ZSH_HIGHLIGHT_HIGHLIGHTERS_DIR=/usr/local/share/zsh-syntax-highlighting/highlighters

```bash
open -a Go2Shell --args config
```



允许任何来源的选项打开 https://www.jianshu.com/p/66782848286c

# 安装破解istat时添加了修改了 hosts

切换到root 用户并执行了如下命令 sudo echo "updates.bjango.com 127.0.0.1" >>/private/etc/hosts


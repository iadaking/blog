# WSL 中 autojump 出现 autojump_chpwd:4: nice(5) failed: operation not permitted 的解决方案

在 `~/.zshrc` 中添加

```shell
unsetopt BG_NICE
```


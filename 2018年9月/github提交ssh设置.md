https://segmentfault.com/a/119000000264562

## 修改`.git`文件夹下`config`中的`url`。

修改前

```shell
    [remote "origin"]
    url = https://github.com/xxx.git
    fetch = +refs/heads/*:refs/remotes/origin/*

```

修改后

```shell
    [remote "origin"]
    url = git@github.com:xxx.git
    fetch = +refs/heads/*:refs/remotes/origin/*

```


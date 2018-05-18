## 安装 shadowsocks



安装 you-get



## 安装 proxychain-ng





## 安装 youtube-dl

Ubuntu 系统直接安装

## 下载最佳 MP4 格式

youtube-dl --proxy “socks5://127.0.0.1:1080” -f 'bestvideo[ext=mp4]+bestaudio[ext=m4a]/best[ext=mp4]/best'



## centos7 安装youtube-dl 

```shell
sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl
```

安装 ffmpeg



下载一个列表

```shell
# 下载一个列表的例子：
youtube-dl -i -f '137+140' --merge-output-format mp4 'https://www.youtube.com/playlist?list=PLvyIyKZVcfAlvx3HoSuxg8a4MOYLd7ki5'
```



## bypy Linux下上传文件到百度网盘

上传当前文件夹下的文件到百度网盘 我的应用数据/bypy 文件夹下，并删除上传成功了的文件；相当于移动操作，移动当前文件夹下的文件到百度网盘中。

`bypy -v -f --move upload` 

在百度网盘中新建一个文件夹

`bypy mkdir leetcode101-150`


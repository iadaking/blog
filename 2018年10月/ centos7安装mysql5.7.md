# Centos 7 安装 MySQL

```
# 下载
$ wget 'https://dev.mysql.com/get/mysql57-community-release-el7-11.noarch.rpm' 
# 设置源？
$ sudo rpm -Uvh mysql57-community-release-el7-11.noarch.rpm 
# 查看源
$ yum repolist all | grep mysql
# 安装最新版命令
$ sudo yum install mysql-community-server
# 安装成功后重启mysql服务
$ sudo service mysqld restart
# 安装完成后查看临时密码
$ sudo grep 'temporary password' /var/log/mysqld.log

```

https://blog.csdn.net/kuluzs/article/details/51924374

# 外网访问mysql设置

https://www.cnblogs.com/starof/p/4680083.html

http://www.cnblogs.com/live41/archive/2013/04/02/2995178.html

**1.修改配置文件**
sudo vi /etc/my.cnf
把bind-address参数的值改成你的内/外网IP或0.0.0.0,或者直接注释掉这行.


**2.登录数据库**
mysql -u root -p

输入密码
mysql> use mysql;


**3.查询host**
mysql> select user,host from user;


**4.创建host**
如果没有"%"这个host值,就执行下面这两句:
mysql> update user set host='%' where user='root';
mysql> flush privileges;


**5.授权用户**
任意主机以用户root和密码mypwd连接到mysql服务器
mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'mypwd' WITH GRANT OPTION;
mysql> flush privileges;

IP为192.168.1.102的主机以用户myuser和密码mypwd连接到mysql服务器
mysql> GRANT ALL PRIVILEGES ON *.* TO 'myuser'@'192.168.1.102' IDENTIFIED BY 'mypwd' WITH GRANT OPTION; 
mysql> flush privileges;

PS：以上为授权方法，以下为改表方法：

mysql> use mysql;
mysql> update user set host='%' where user='root';
mysql> flush privileges;

# mac telnet 命令安装

https://www.huangzz.xyz/mac-telnet-an-zhuang.html

其实 telnet 的源码包并不叫 telnet ，而是叫 [inetutils](http://ftp.gnu.org/gnu/inetutils/) 。之前使用 Linux 时， telnet 都是自带的，所以没太注意。

在 `brew search inetutils` 后，发现存在这个包，遂使用 `brew install inetutils` 进行下载安装

# centos7 ping通telnet不通

https://blog.csdn.net/love5117/article/details/43817463

原来从centos7开始系统就已经启用了firewalld，决定暂时完全屏蔽掉firewalld

systemctl stop firewalld.service

systemctl disable firewalld.service
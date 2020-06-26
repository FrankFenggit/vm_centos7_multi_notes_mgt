# 常用命令

[TOC]

## docker

### tomcat

```shell
docker run --name tomcat-8090 -p 8090:8080 
-v /vagrant/tomcattest:/usr/local/tomcat/webapps/tomcat-test 
-d tomcat

docker run --name tomcat-8091 -p 8091:8080 -d tomcat
```

### httpd

```shell
docker run --name httpd8070 -p 8070:80 
-v $PWD/www/:/usr/local/apache2/htdocs/ 
-v $PWD/conf/httpd.conf:/usr/local/apache2/conf/httpd.conf 
-v $PWD/logs/:/usr/local/apache2/logs/ 
-d httpd 
```

### mysql

```shell
docker run -p 3306:3306 --name mysql5.7-3306 \
-v /vagrant/mysql/conf:/etc/mysql \
-v /vagrant/mysql/logs:/var/log/mysql \
-v /vagrant/mysql/data:/var/lib/mysql \
-e MYSQL_ROOT_PASSWORD=123456 \
-d mysql:5.7
```



## 开启coredump（centos7为例）

```bash
#一种方法是：ulimit -c unlimited
#但是这种方法是暂时的，你每打开一次终端都要输一次
ulimit -c unlimited

#另一种方法是：修改//etc/security/limits.conf  修改 soft core 
vi /etc/security/limits.conf
#*              soft    core            unlimited
#root           soft    core            unlimited
#之后保存。*代表所有用例，对root用例专门设置，以确保对root用例生效。

# format the name of core file.   
# %% – 符号%
# %p – 进程号
# %u – 进程用户id
# %g – 进程用户组id
# %s – 生成core文件时收到的信号
# %t – 生成core文件的时间戳(seconds since 0:00h, 1 Jan 1970)
# %h – 主机名
# %e – 程序文件名
echo -e "core-%e-%s-%u-%g-%p-%t" > /proc/sys/kernel/core_pattern

# for centos7 system(update 2017.2.3 21:44)
echo -e "core-%e-%s-%u-%g-%p-%t" > /etc/sysctl.conf

# suffix of the core file name
echo -e "1" > /proc/sys/kernel/core_uses_pid
```


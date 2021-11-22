## HDFS开源文件系统学习
HDFS是由java语言开发的，应用也很广泛。[官方中文文档](http://hadoop.apache.org/docs/r1.0.4/cn/hdfs_user_guide.html)

1. 开源主流分布式文件系统简单介绍[参考地址](https://blog.csdn.net/u011436427/article/details/98198935)

2. centos7 配置单机 HDFS[参考地址](https://blog.csdn.net/BlaineLi/article/details/103135082)

## centos7 中删除openjdk包，安装jdk
1. rpm -qa | grep java     //查看安装的java包
2. 删除安装的jdk包
````
rpm -e --nodeps java-1.8.0-openjdk-headless-1.8.0.252.b09-2.el7_8.x86_64
pm -e --nodeps java-1.8.0-openjdk-1.8.0.252.b09-2.el7_8.x86_64
````

### HFDS启动报错： ERROR: but there is no YARN_RESOURCEMANAGER_USER defined. Aborting operation.
[处理参考地址](https://www.cnblogs.com/liuys635/p/11069313.html)

### 启动Hadoop时候datanode没有启动的原因及解决方案
[参考地址](https://www.cnblogs.com/ya-qiang/p/9494986.html)

### 查询了半天启动不了NameNode服务，各种修改，运行下面一个命令就可以了，干。。。


注意：
我直接用  $HADOOP_HOME/sbin/start-dfs.sh没有启动所有是因为没有弄公私钥。所以本地不能ssh，处理可以看官方文档：描述如下
````
If you cannot ssh to localhost without a passphrase, execute the following commands:

  $ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
  $ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
  $ chmod 0600 ~/.ssh/authorized_keys
````

https://blog.csdn.net/nenguou04/article/details/88770031

[Unit]
Description=nginx - high performance web server
Documentation=http://nginx.org/en/docs/
After=network.target remote-fs.target nss-lookup.target
 
[Service]
Type=forking
PIDFile=/your nginx pid file path/nginx.pid
ExecStartPre=/usr/local/nginx/sbin/nginx -t -c /usr/local/nginx/conf/nginx.conf
ExecStart=/usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf
ExecReload=/bin/kill -s HUP $MAINPID
ExecStop=/bin/kill -s QUIT $MAINPID
PrivateTmp=true
 
[Install]
WantedBy=multi-user.target


## javaweb开发常用linux操作是的一些常用指令
[linux命令大全参考地址](https://ipcmen.com/category/shell-command)

#### 一、查看日志详情
tail -f /usr/local/apache-tomcat-8.0.30/logs/catalina.out -n 300

#### 二、查看某段时间(2017-12-27 09:25到2017-12-27 09:26)的日志文件
sed -n "/2017-12-27 09:25/,/2017-12-27 09:26/p"  /usr/local/apache-tomcat-8.0.30/logs/catalina.out

#### 三、筛选日志文件：cat 文件路径 | grep “删选条件”
cat  /usr/local/apache-tomcat-8.0.30/logs/catalina.out | grep "筛选字段"
cat -n /usr/local/apache-tomcat-8.0.30/logs/catalina.out | grep "Exception" | grep "2018-01"|more

#### 四、windows 查看文件：find
find “赛选字段” 文件路径，如：find "2017-12-18 16:53" emm.txt

#### 五、linux允许远程连接设置：支持root用户允许远程连接mysql数据库
grant all privileges on *.* to 'root'@'%' identified by '123456' with grant option;
flush privileges;
受了权限还是不能连上可能是linux防火墙没有关

### CentOS7防火墙开启端口命令：
- firewall-cmd --permanent --add-port=3032/tcp
- firewall-cmd --reload

### centos7或关闭防火强服务
systemctl stop firewalld.service
systemctl start firewalld.service

### 注意磁盘的使用率，使用90%以上，就容易造成系统问题

### grep命令的or，and，not操作的例子
[参考地址](https://www.cnblogs.com/chaichuan/p/4172070.html)

### CentOS 7.x设置自定义开机启动,添加自定义系统服务
配置[参考地址](http://www.sevenfal.com/2016/08/04/784.html)
- 简单说明
~~~~
[Unit]:服务的说明
Description:描述服务
After:描述服务类别
 
[Service]服务运行参数的设置
Type=forking      是后台运行的形式
ExecStart        为服务的具体运行命令
ExecReload       为服务的重启命令
ExecStop        为服务的停止命令
PrivateTmp=True     表示给服务分配独立的临时空间
注意：启动、重启、停止命令全部要求使用绝对路径
 
[Install]        服务安装的相关设置，可设置为多用户
WantedBy=multi-user.target 
~~~~


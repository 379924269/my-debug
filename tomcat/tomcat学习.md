## tomcat相关学习
### tomcat做成服务
#### linux  
[参考地址](https://blog.csdn.net/qq_30641447/article/details/103940081)
- 1、 root用户配置全局环境变量，
vi /etc/profile
追加以下内容
````
export JAVA_HOME=/usr/jdk1.7.0_72
export PATH=$JAVA_HOME/bin:$PATH
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
````
生效：source /etc/profile

- 2、在/usr/lib/systemd/system/目录下新建文件tomcat7.service（这里可以自定义），内容如下：  
`**内容中的路径以实际为参考**`
````
[Unit]
Description=Tomcat7
After=syslog.target network.target remote-fs.target nss-lookup.target
   
[Service]
Type=forking
Environment='JAVA_HOME=/usr/jdk1.7.0_72'
Environment='CATALINA_PID=/usr/apache-tomcat-7.0.70/bin/tomcat.pid'
Environment='CATALINA_HOME=/usr/apache-tomcat-7.0.70/'
Environment='CATALINA_BASE=/usr/apache-tomcat-7.0.70/'
Environment='CATALINA_OPTS=-Xms512M -Xmx1024M -server -XX:+UseParallelGC'
 
WorkingDirectory=/usr/apache-tomcat-7.0.70/
 
ExecStart=/usr/apache-tomcat-7.0.70/bin/startup.sh
ExecReload=/bin/kill -s HUP $MAINPID
ExecStop=/bin/kill -s QUIT $MAINPID
PrivateTmp=true
   
[Install]
WantedBy=multi-user.target
````
- 3、设置为开启机启动：systemctl enable tomcat7

- 4、启停服务  
A,启动服务：systemctl start tomcat7  
B,停止服务：systemctl stop tomcat7  
C,重启服务：systemctl restart tomcat7  

[参考地址](https://blog.csdn.net/gc666888/article/details/123510992)  
- 打开cmd命令窗口，进入tomcat的bin文件夹，执行命令service.bat install安装tomcat服务

#### windows  
以管理员方式打开cmd->cd到tomcat的bin目录下,执行 service.bat install

### windows下启停服务
net start 服务名称  
net stop 服务名称
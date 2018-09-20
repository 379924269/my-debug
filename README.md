# my-debug
我经常遇到的一些问题

## 1、通过maven创建普通的jar项目，没有引入jar包和主函数
- 可以通过加载maven配置来完成，参考地址：https://blog.csdn.net/xiao__gui/article/details/47341385， 我选的第二种
- 第一种要生成一个lib和一个jar包，这样重复上传的的话可以少传代码，下次更新就只传一个jar就可以了（如果不更新jar包）



## 2、maven引入自己的jar, 操作如下	
```
1、
<dependency>
      <groupId>iTextAsina</groupId>
      <artifactId>com.lowageie.text.pdf.fonts</artifactId>
      <version>1.0</version>
      <scope>system</scope>
      //下面就是自己的路径
      <systemPath>E:/ideaGitProject/commonUtil/export-xls-doc-pdf/src/main/resource/iTextAsian.jar</systemPath>
</dependency>

2、可以将jar打包到本地库，然后引入jar，参考地址：https://blog.csdn.net/JinbaoSite/article/details/79427544
```
## 3、文件上传，参考地址：https://www.cnblogs.com/ghq120/p/8312944.html
- servlet直接是文件流
- struts2直接封装file对象，直接用
- springmvc 直接用MultipartFile

## 4、ireport4.6启动不了，一起懂就闪退。
- 原来是jdk没路径配置好.修改：ireport根目录/etc/ireport.conf 中jdk配置就可以了
- 参考地址https://blog.csdn.net/dragonpeng2008/article/details/51943711

## 5、生成日志路径问题：
- log.dir = ../logs/项目名称/logs/日志名称，会生成到tomcat下面的logs里面
- log.dir = logs/日志名称,会生成到tomcat/bin下面
- log.dir = /log/日志名称,会生成到项目跟目录下面

## 6、jar包记录日志问题
- 引入依赖包，maven引入slf4j-log4j12，其他依赖都有了
- src/resources 包中加入log4j.properties

## 7、 springboot 开启调试模式，
- 1、打开Run/Debug Configurations,
- 2、选择Spring Boot 下要进行debug调试的服务,
- 3、在VM options:的填写框中写入"-Xms512m -Xmx512m -Xmn164m -XX:MaxPermSize=250m -XX:ReservedCodeCacheSize=64m -Dserver.port=8080 -ea",
- 4、port是该服务的端口号;Working directory选择$MODULE_DIR$。
- 5、然后debug运行微服务主程序入后即@springbootapplication注释的类就可以了

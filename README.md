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

<dependency>
	  <groupId>com.ckfinder</groupId>
	  <artifactId>apache-ant-zip</artifactId>
	  <version>2.3</version>
	  <scope>system</scope>
	  <systemPath>${project.basedir}/src/main/webapp/WEB-INF/lib/apache-ant-zip-2.3.jar</systemPath>				
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

还有一个简单的命令：
- 1、打开Run/Debug Configurations
- 2、添加一个maven命令：spring-boot:run -Ddebug 然后运行命令就可以了


## 8、springboot devtools 的使用
- 1、“File” -> “Settings” -> “Build,Execution,Deplyment” -> “Compiler”，选中打勾 “Build project automatically” 。

- 2、组合键：“Shift+Ctrl+Alt+/” ，选择 “Registry” ，选中打勾 “compiler.automake.allow.when.app.running” 。

## 9、springboot 跨域问题，修改参看地址：
https://blog.csdn.net/qq_24393965/article/details/80689299

## 10、写代码的时候注意：
类和方法的名称是否“一眼就看明白了”、“不写注释也看得懂”。
方法中的代码是否“一眼就看明白了”， 代码行数不应该过多。
写方法的时候注意兼容性，

## 11、maven不配置下面代码，变异的时候可能有点问，注意：
````
 <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-compiler-plugin</artifactId>
      <version>3.3</version>
      <configuration>
           <source>1.8</source>
           <target>1.8</target>
      </configuration>
 </plugin>
````

## 12、创建项目后目录 mark directory as 问题：
参考地址：https://ask.csdn.net/questions/706375 下面的回答
注意：源码一定要放到main.java目录下面，别少了【java目录】

## 13、多项目打包，问题：打的jar包含了库文件，如果分模块项目体积就变大了，处理参考地址：
````
https://blog.csdn.net/lizhongfu2013/article/details/7965697
````

## 14、springboot jar改为war包参考地址：
````
https://www.jianshu.com/p/6451e6aa99a0
````

## 15、解决SpringBoot jar包太大的问题，参考地址：
````
https://www.cnblogs.com/ygjlch/p/7767639.html
````

## 16、list<object>转list<map<string, object>>, 利用了java8的功能 
````
list<Position>.stream().map(this::toMap).collect(Collectors.toList());

 private Map<String, Object> toMap(Position position) {
        Map<String, Object> map = new HashMap<>();
        map.put("id", position.getId());
        map.put("userId", position.getUserId());
        map.put("username", position.getUsername());
        map.put("latitude", position.getLatitude());
        map.put("longitude", position.getLongitude());
        map.put("createTime", new SimpleDateFormat("yyyy-MM-dd HH:mm:ss").format(new Date(position.getCreateTime())));
        return map;
    }
````

## 17、git项目传到github上的操作步骤
````
1、git上创建一个新的项目，名称和自己的一样，
2、修改本地项目的远程git地址为刚刚在git上创建的新项目。
3、本地项目提交。
````

## 在war包里面还有一个lib-provided在里面，使包变得大了一些，参考处理地址：
````
https://www.cnblogs.com/andysd/p/10105801.html
相当可以直接用xx.war.original这个包。把.original去掉就可以了
````

## bibernate验证规则参考地址
https://www.cnblogs.com/wjh123/p/8745473.html
# my-debug
我经常遇到的一些问题

## 1、通过maven创建普通的jar项目，没有引入jar包和主函数
- 可以通过加载maven配置来完成，参考地址：https://blog.csdn.net/xiao__gui/article/details/47341385， 我选的第二种
- 第一种要生成一个lib和一个jar包，这样重复上传的的话可以少传代码，下次更新就只传一个jar就可以了（如果不更新jar包）



## 2、maven引入自己的jar, 操作如下	
```
<dependency>
      <groupId>iTextAsina</groupId>
      <artifactId>com.lowageie.text.pdf.fonts</artifactId>
      <version>1.0</version>
      <scope>system</scope>
      //下面就是自己的路径
      <systemPath>E:/ideaGitProject/commonUtil/export-xls-doc-pdf/src/main/resource/iTextAsian.jar</systemPath>
</dependency>
```
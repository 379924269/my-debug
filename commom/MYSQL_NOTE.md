##MYSQL 的一些注意事项
####1、数据库中的`登录`字段一定要设置唯一。

####2、数据库`条件查询`字段`忽略大小写`

####3、数据库外键问题：比如删不掉表，报外键问题。处理
````
1、SELECT  @@FOREIGN_KEY_CHECKS 查看外键启用没有
2、set foreign_key_checks = 0   关闭外键功能
3、set foreign_key_checks = 1   启用外键功能
````

####4、导入数据库
````
1、方法一
mysql -uxxx -pxxx create databaseName
mysql -uxxx -pxxx databaseName < databaseName.sql
2、方法2
mysql -uxxx -pxxx  //进入数据库
create database dbName  // 创建库
use dbname               //选中该库
source backupFile        //导入备份文件
````

####5、备份数据库
mysqldump -uxxx -p databaseName > backupFile
enter password: xxx

####6、mysql中模糊查询要处理的特殊字符，记得转义
1、' 点
2、% 百分号
3、下划线

####6、 group_contact函数默认长度为1024子字节

## sql优化

###1、in 当in的数据达到上万条后明显有点慢，我用EXISTS替换了
[参考地址](https://blog.csdn.net/fukaiit/article/details/83515439)

### 2、FIND_IN_SET  跟在where后面就慢了。
部门数据不到1000条就用了4、5秒
慢：    SELECT o.id FROM `organization` o WHERE FIND_IN_SET(o.id, getChildList(1));
优化后：SELECT o.id FROM `organization` o, (SELECT getChildList(1) cids) t WHERE FIND_IN_SET(o.id,cids);

[参考地址](https://blog.csdn.net/wokelv/article/details/78915502)
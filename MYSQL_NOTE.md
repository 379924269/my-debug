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
## 我优化过的sql语句

###in 当in的数据达到上万条后明显有点慢，我用exit替换了
参考地址：https://blog.csdn.net/fukaiit/article/details/83515439

### FIND_IN_SET  跟在where后面就慢了。
部门数据不到1000条就用了4、5秒
慢：    SELECT o.id FROM `organization` o WHERE FIND_IN_SET(o.id, getChildList(1));
优化后：SELECT o.id FROM `organization` o, (SELECT getChildList(1) cids) t WHERE FIND_IN_SET(o.id,cids);

参考地址：https://blog.csdn.net/wokelv/article/details/78915502
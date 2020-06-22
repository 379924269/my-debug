## WEB日志学习
Java项目构建基础：统一结果，统一异常，统一日志（好文推荐）[参考地址](https://mp.weixin.qq.com/s?__biz=MzUxNjk0ODIwMg==&mid=2247486092&idx=1&sn=ceecd437dceb881c1f6dacf91c31bf32&chksm=f99ee309cee96a1f1b07a92f27728eae11457990efc751d2324505e5fc885e52252de945741d&scene=126&sessionid=1592785720&key=4329f85beb0ed04a90b20fe0315da2a0d5f0ddc52805a78168cb5a0f725e104fcee4846c547b88e88a18ff300298e7347de3c0e4cae6f73e2da98487729b88de9ccd85f26d03f55b12e491e4f3f4a41b&ascene=1&uin=MjU1OTg0MzU4Mw%3D%3D&devicetype=Windows+10&version=62080079&lang=zh_CN&exportkey=Awe1NHn2CqFs5OUeaINY81Y%3D&pass_ticket=R1%2FtldE97aw3pnchU%2B6WkAsM2HrArLb3lALHyRASmDCxHOsBkjp%2BUomKdIv9pHu%2B)

### 1、springboot中lockback配置
- 参考文件，当前文件夹下logback.xml、logback.properties
- 然后配置依赖：
````
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-logging</artifactId>
</dependency>
````
- 注意：一般只修改logback.properties配置就可以了
## java中常用的工具库
[apache commons](http://commons.apache.org/) 是我经常访问的工具库
- 我常用的库
### IO库，功能描述：[demo参考地址](http://commons.apache.org/proper/commons-io/description.html)
        - 实用程序类 -具有执行常规任务的静态方法
        - 输入 -有用的输入流和阅读器实现
        - 输出 -有用的输出流和Writer实现
        - 过滤器 -文件过滤器的各种实现
        - 比较器 - 文件java.util.Comparator的各种实现
        - 文件监视器 -用于监视文件系统事件的组件
        
### lang库，功能描述,[demo可以参考源码中的util即可]()：
        - Lang为java.lang API提供了许多帮助程序实用程序，特别是字符串操作方法，基本数值方法，对象反射，并发，创建和序列化以及系统属性。此外，它还包含对java.util.Date的基本增强，以及一系列专用于构建方法的实用程序，例如hashCode，toString和equals。
     
### Collections库，功能描述：
    - Bag接口，用于每个对象具有多个副本的集合
    - BidiMap接口用于maps，该maps也可以从值到键以及键到值进行查找
    - MapIterator界面可提供简单快速的maps迭代
    - 变换修饰器，以在将每个对象添加到集合时更改每个对象
    - 使多个集合看起来像一个的复合集合
    - 添加有序图和保留订单元素的集合，包括基于LRU的图
    - 参考图，允许在紧密控制下对键和/或值进行垃圾回收
    - 许多比较器实现
    - 许多迭代器实现
    - 从数组和枚举到集合的适配器类
    - 用于测试或创建集合的典型集合论属性（例如并集，交集和闭包）的实用程序
        
### codec库，功能描述：
        - 常规编码/解码算法（例如，语音，base64，URL）。编解码器由一组实用程序和一个用于对文本和二进制数据进行编码和解码的简单框架组成。
### Validator库，功能描述,[demo参考地址](http://commons.apache.org/proper/commons-validator/apidocs/org/apache/commons/validator/routines/package-summary.html#package_description)
        2. 日期和时间验证器
            2.1 概述
            2.2 验证日期值
            2.3 格式化
            2.4 时区
            2.5 比较日期和时间
        3. 数值验证器
            3.1 概述
            3.2 验证数值
            3.3 格式化
            3.4 比较数字
            3.5 货币验证
            3.6 验证百分比
        4. 其他验证人
             4.1 概述
             4.2 正则表达式验证
             4.3 校验位验证/计算
             4.4 通用代码验证
             4.5 ISBN验证
             4.6 IP地址验证
             4.7 电子邮件地址验证
             4.8 URL验证
             4.9 域名验证
       
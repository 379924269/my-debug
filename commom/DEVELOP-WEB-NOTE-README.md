## Javaweb后端开发注意事项
#### 一、防止sql注入
    处理：少用sql字符串拼接，如果要用过滤特殊字符

#### 二、防止远程xxs脚本攻击
    处理：添加一个请求过滤器，对所有请求的参数进行过滤。
    可参考地址：https://blog.csdn.net/fangleijiang/article/details/73696866

#### 三、接口安全
    处理：添加接口访问权限，有权限才可以访问接口

#### 四、文件上传漏洞
    处理：限制文件上传大小与类型

#### 五、返回错误信息字段统一
    处理：封装返回参数， 返回最好和前段和手机端端商量好

#### 六、记得写测试代码，一键测试
    处理：记得写测试，别老是每次都去手动测试

#### 七、历史数据库保存
    处理：首先把基础数据库保存好，数据库字段发生变化记得保存新表，并注明原因，然后保存到git

#### 八、注意事物回归，分层清晰，定义好业务异常
    处理：
    controller：控制层，接收参数，验证参数
    Service：业务层，处理业务逻辑，注意事物回滚问题
    Dao：持久层，对数据库的curd操作

#### 九、记录操作日志
    处理：通过aop同意记录日志，有助于维护，发现异常访问

#### 十、做一个ip黑名单
    如果发现某个ip正在攻击服务器，可以禁止该ip

#### 十一、数据库备份
    为了安全需要做数据库备份，自动恢复还是手动回复。

#### 十二、注意web退出session要失效
    调用Session.invalidate()

#### 十三、敏感信息记得加密
    如前段传输密码要传密文、保存密码要保存密文

#### 十四、模糊查询字段要处理的特殊字符（sql查询下划线和%都是查询所有）

    //处理特殊字符"_"和"%"
    public static String dealSpecialCharacter(String specialCharacters) {
            if (isEmpty(specialCharacters)) {
                return specialCharacters;
            } else {
                if (searchParam.contains("%") || searchParam.contains("_")) {
                    return searchParam.replace("%", "\\%").replace("_", "\\_");
                }
                return searchParam;
            }
    }
    
#### 十五、404和500的处理
不处理会泄露服务器信息

#### 十六、登录次数限制，防止暴力破解

#### 十七、sql中文排序问题
如果编码是GBK就没问题，如果是utf-8就会有问题，需要处理一下

### 十八、 如何设计一个安全的对外接口
[参考地址：](https://mp.weixin.qq.com/s?__biz=MzAxNjk4ODE4OQ==&mid=2247488713&idx=3&sn=ff5991d4881929bd6a147a7051e05a35&chksm=9bed35bbac9abcadfc1f1359ec66e98c29931fb89570ab10636c96ee6bd7a1b6a4e68be36ef5&scene=126&sessionid=1588207136&key=5134b9fdf48fcb986221218adb49aea48295b3e2ecffed11414047ef90725be67460b94ad89a4956b45efbc557a28ce1fd5cb6654ebe07e02e571d7e6e4217ea3e04ca4c87027cd29044beae1ec8c44d&ascene=1&uin=MjU1OTg0MzU4Mw%3D%3D&devicetype=Windows+10&version=62080079&lang=zh_CN&exportkey=A9aQVc3rRVvxY45eRjk9pmk%3D&pass_ticket=3avGRUpDV6Dn%2Bc4UHiRxoPBEzROgPF6n6JGDGam%2BrsEShz%2BZvkcEzVv4uWLj4eMB)




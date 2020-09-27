## RabbitMQ学习
我参考的书籍：《RabbitMQ实战指南》， 本书在我的百度网盘上有， 也可以在`脚本之家`[下载](https://www.jb51.net/books/648894.html).
学习要点：exchange、routingkey、queue，要熟练运用需要详细了解他们的接口参数。

### 1、后台启动rabbitmq
- 到rabbitmq的sbin下运行rabbitmq-server -detached（如果配置了环境变量，可以直接输入命令）
- [本地访问地址](http://localhost:15672)

## rabbit中的一些名词
- playload 消息体 
- label 标签
- envelope 英 [ˈenvələʊp]  信封
- delivery 英 [dɪˈlɪvəri]  传递、交付
- broker 英 [ˈbrəʊkə(r)]  n. 经纪人 v. 安排、协商 消息队列服务器实体
- consume 消耗
- Blocking Queue 阻塞队列里
- round-robin 英 [ˌraʊnd ˈrɒbɪn] 轮询
- exchange 交换器
- routkey 路由键
- bingding 绑定
- direct 英 [dəˈrekt] 直接的
- channel 信道
- internal 英 [ɪnˈtɜːnl] 内部的;里面的;体内的;(机构)内部的
- passive adj. 消极的;被动的;(动词形式)被动语态的 n. 动词被动形式;被动语态
- transient 英 [ˈtrænziənt] adj. 短暂的;转瞬即逝的;倏忽;暂住的;过往的;临时的 n. 暂住某地的人;过往旅客;临时工
- durable 英 [ˈdjʊərəbl] adj. 耐用的;持久的 n. 耐用品;耐久品
- mandatory 英 [ˈmændətəri]   adj. 强制的;法定的;义务的
- immediate 英 [ɪˈmiːdiət]  adj. 立即的;立刻的;目前的;当前的;迫切的;接近的;附近的;紧接的
- TTL (time to live) 过期时间
- RPC (remote procedure call) 远程过程调用
- DLX (dead letter exchange) 死信交换器
- multiple 英 [ˈmʌltɪpl]  adj. 数量多的;多种多样的 n.倍数
- federation 英 [ˌfedəˈreɪʃn]  n. 联邦;(俱乐部、工会等的)联合会;同盟;联盟
- shovel 英 [ˈʃʌvl] n.铲;铁铲;(推土机、挖土机等的)铲
- proxy 英 [ˈprɒksi]  n.代理权;代表权;代理人;受托人;代表;(测算用的)代替物，指标

## exchange 交换器
- 1、[交换器类型介绍参考地址](https://blog.csdn.net/u013938578/article/details/81606884)
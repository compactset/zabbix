Zabbix的问题整理
======

整理在用Zabbix和读代码过程中的一些问题。

问题汇总
--------


2. zabbix的Last 20 issues里面怎么没有ack

3. zabbix api是什么？

  [Zabbix 1.8 api](http://www.zabbix.com/documentation/1.8/api)

  [Zabbix 2.0 api](http://www.zabbix.com/documentation/2.0/api)

  [Zabbix的perl json-rpc api客户端](https://github.com/SFR-ZABBIX/Zabbix-API)

  [Zabbix 2.0手册上的api](https://www.zabbix.com/documentation/2.0/manual/appendix/api/api)


4. zabbix如何自动注册？

  [官方手册上的自动注册说明](https://www.zabbix.com/documentation/2.0/manual/discovery/auto_registration)

  [官方wiki的自动注册说明，action可以新建设备、设备组、关联模板](https://www.zabbix.com/wiki/howto/config/autoregister)

5. zabbix proxy如何分布式，流程是什么？

  Zabbix Proxy能够代替Zabbix Server进行性能及可用性数据采集. Proxy是Zabbix部署的可选组件。 如果想分担单一Zabbix Server负载，推荐使用proxy.

  [官方文档: 高可用性集群搭建](https://www.zabbix.org/wiki/Docs/howto/high_availability)
  
  [官方文档：分布式监控](https://www.zabbix.com/documentation/doku.php?id=1.8/manual/distributed_monitoring)

  [翻译的中文文档：分布式监控Node](https://zabbix-manual-in-chinese.readthedocs.org/en/latest/distributed_monitoring/nodes/index.html)
  
  [多节点分布式配置](http://hi.baidu.com/jiaozhenqing/item/f7ae08f5cfe183ce531c2697)

  [论坛讨论1](http://comments.gmane.org/gmane.network.zabbix.user/729)

  [论坛讨论2](https://www.zabbix.com/forum/showthread.php?t=4104)

  [论坛讨论3](http://blog.zabbix.com/multiple-servers-for-active-agent-sure/858/)



6. zabbix的agent、sender、proxy、Java Gateway的发送json格式是什么?

  [Zabbix的协议](https://www.zabbix.org/wiki/Docs/protocols)

  [server和agent的通信json格式](https://www.zabbix.com/documentation/2.0/manual/appendix/items/activepassive)

7. 数据库里hosts、items、hots_templates表之间是什么关系？
   

8. Zabbix server如何知道模板的内容，并去采集相应数据？
  

9. 如何绕过php的frontend，调用Zabbix的json rpc？
   
  [1.8版本的api入门](https://www.zabbix.com/documentation/1.8/api/getting_started)

  [教程1](http://blog.zabbix.com/getting-started-with-zabbix-api/1381/)

  [教程2](http://doc.bonfire-project.eu/R2/monitoring/monitoring_zabbix_API.html)

  [教程3](http://webcache.googleusercontent.com/search?q=cache:pp8ZvALsGwwJ:paperplane.ruhoh.com/zabbix/zabbix-api%E7%AE%80%E4%BB%8B%E5%8F%8A%E4%BD%BF%E7%94%A8/+zabbix+json+api+curl&cd=5&hl=zh-CN&ct=clnk&gl=cn&client=firefox-a)

10. json rpc auth id的会话是否会过期？

	```
		Todo...
	```

11. zabbix是什么开源协议，第三方公司开发的插件有源代码么？
   
    ```
		协议为GPL
	```

    > zabbix的第三方客户端，主要是手机客户端，还有类库
	http://www.zabbix.com/third_party_tools.php
	上面列的zabbix第三方客户端，有一个realopinsight的dashboard很不错，可以学习下。它也是开源的
	http://realopinsight.com/en/
	realopinsight的特点
	http://realopinsight.com/en/index.php?page=monitoring-concepts-and-technology
	realopinsight的源码和二进制包，支持fedora
	http://realopinsight.com/en/index.php?page=download-lastrel
	[mikoomi公司开发了些针对NoSql的agent](http://code.google.com/p/mikoomi/)
	（目前包括MongoDB、Amazon EC2、Hadoop、HBase）
  

12. zabbix的界面用什么库画曲线图的？
    
    ```
		Todo...
	```

13. 如何修改Zabbix的数据项的默认监控频率？

    ```
		Todo...
	```

14. zabbix的appliance如何用?和turnkeylinux提供的100多种appliance有何区别？

    ```
		Todo...
	```

15. snmp agent在哪里运行？是不是必须在zabbix server上跑？这样会不会影响性能？性能如何？

    ```
		在Poller线程里跑的吧。不必须在Zabbix Server上跑。可以让Proxy跑，分担Server的负载。
	```

16. zabbix支持日志采集，但是syslog支持么？如何配置？
    
    [zabbix论坛里有人写了个syslog receiver转zabbix json的程序](https://www.zabbix.com/forum/showthread.php?t=19180)

    [相关的代码](http://www.alixen.org/svn/zbxlog/tags/r0.1/README)

17. 如何进行performance tuning?

    首先Zabbix的Release Notes定位用于**中小型企业级网管**。

    [官方高可用性文档](https://www.zabbix.org/wiki/Docs/howto/high_availability)

    [Postgres表分区提高性能1](https://www.zabbix.org/wiki/Docs/howto/zabbix2_postgresql_partitioning)、
    [Postgres表分区提高性能2](https://www.zabbix.org/wiki/Docs/howto/zabbix2_postgresql_autopartitioning)、
    [Postgres表分区提高性能3](https://www.zabbix.org/wiki/Docs/howto/postgresql_partitioning_by_range)

    [Zabbix创始人Alexei Vladishev写的性能调优ppt](http://www.zabbix.com/img/zabconf2011/presentations/Alexei_Vladishev_-_Zabbix_Performance_Tuning.pdf)
    

18. Zabbix有在线Demo么？

    [Zabbix的在线demo1: takealook/takealook](https://zabbixdemo.coreit.fr)

19. Zabbix有手机客户端么？
    
    >zabbix还有手机版，用php写的，只能用浏览器访问，不是native app。
    >只有最基本的hostgroup、hosts和图表曲线功能。
    >http://www.mozbx.net/
	有[demo](http://www.mozbx.net/demo.html)。
	
    zabbix手机客户端源代码
    ```
		wget https://github.com/mattiasgeniar/MoZBX/zipball/master
	```
  



    
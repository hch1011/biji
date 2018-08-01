 





#知识点





## 直连服务提供者，指定调用，本地调用

方法0： (推荐) JVM中添加启动参数

`java -Dcom.alibaba.xxx.XxxService=dubbo://localhost:20890` 

如果服务比较多，可以使用文件映射。如下面方法



方法1： (推荐)当${user.home}下添加属性文件

文件名:**dubbo-resolve.properties**

内容：

com.xxx.xxx.XxxService=dubbo://localhost:20890



方法2： 消费者.xml添加属性url，多个分号分隔
<dubbo:reference url="**dubbo://localhost:20880;dubbo://localhost:20881**" .../>



方法3： 使用唯一版本号
方法2.1 ：单个服务使用版本号
<dubbo:service interface="xxx" ref="xxx" retries="0" version="0.0.0"/>
<dubbo:reference interface="xxx" id="xxx" check="false" retries="0" timeout="60000" version="0.0.0"/>

方法2.2： 或者统一配置版本号
<dubbo:provider timeout="10000" threadpool="fixed" threads="100" accepts="1000" version="0.0.0"/>
<dubbo:consumer version="0.0.0" />







## jmeter测试dubbo接口 



## telnet

telnet登录dubbo：

​	>telnet 172.17.0.13 60003

查看提供的服务

​	>ls

ls com.cxxx.xxxxdubbo 

ls com.test.DemoService 

ls com.test.DemoService queryDemoPageList insertDemolist 



调用方法 

​	invoke 





 

# 问题

 

 

# 参考

<http://dubbo.io/>

<https://github.com/dangdangdotcom>

https://www.cnblogs.com/yougewe/p/6673845.html

java调试技能之dubbo调试 ---telnet



<https://blog.csdn.net/lzwglory/article/details/69289395>

Dubbo性能优化

<https://www.zhihu.com/question/39560697/answer/104096311>

阿里巴巴为什么主推HSF?比Dubbo有哪些优势? EDAS

RPC最重要的事性能，运维

<http://www.iigrowing.cn/dubbo_chao_shi_ji_zhi_dao_zhi_de_xue_beng_lian_jie.html>

超时机制导致的雪崩连接an_jie.html

<http://blog.csdn.net/akfly/article/category/6600674>

akfly学习笔记  14

 
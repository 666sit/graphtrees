# graphtrees
# 最新版集成到OneOaaS Monitor中，下载地址http://www.oneoaas.com/download   
###功能
```
一、集中展示所有分组设备
二、集中展示一个分组图像
三、集中展示一个设备图像
四、展示设备下的Application
五、展示每个Application下的图像
六、展示每个Application下的日志
七、对原生无图的监控项进行绘图
注意问题:
    在组和主机级别，默认只显示系统配置的graph
    点击application后，会显示3种数据：
    1. 系统默认有graph的；
    2. 系统默认无graph的；
    3. 日志类的
```


```
Function:
Zabbix graph tree  
Display all monitor things in one page.
1.All group graph 
2.One Application graph 
3.One group graph
4.One host graph
5.All Application one host
6.All Application log text 
7.draw graph if no exist graph in host if item type is Numeric 
Note:
   click group and host,display graph in host graph
   click Application,dispaly 3 types:
   1.default graph
   2.Draw graph for not exist graph(item type is Numeric)
   4.item tpye is Character\Log\Text
```
## zabbix web version  >=3.0.0  
### 安装   
###### 注意：如果你用过3.0.1的patch，需要重新下载zabbix的源码包，请用第一种方法安装  

#How to Install:
1.if you have not installed zabbix web
```
#说明，本项目支持3.0.4以上的ZabbixWEB版本
wget http://sourceforge.net/projects/zabbix/files/ZABBIX%20Latest%20Stable/3.0.4/zabbix-3.0.4.tar.gz
tar xf zabbix-3.0.4.tar.gz
cd frontends/php
wget https://raw.githubusercontent.com/OneOaaS/graphtrees/master/graphtree3.0.4.patch
#yum install -y patch
patch  -Np0 <graphtree3.0.4.patch
chown -R ${WEB_USER} oneoaas
cd ../
mv php /usr/share/zabbix (Web root should be /usr/share/zabbix)
#注意此处的权限，必须和nginx或者apache的用户一致，如用的是apache，则此处为chown -R apache:apache oneoaas/
```

2.If you have already installed zabbix web RPM repo  #从未使用过3.0.1的patch
```
#说明，本项目支持3.0.4以上的ZabbixWEB版本
cd /usr/share/zabbix
wget https://raw.githubusercontent.com/OneOaaS/graphtrees/master/graphtree3.0.4.patch
yum install -y patch
patch  -Np0 <graphtree3.0.4.patch
chown -R ${WEB_USER} oneoaas
#注意此处的权限，必须和nginx或者apache的用户一致，如用的是apache，则此处为chown -R apache:apache oneoaas/
```

3.Apache Issue		 +
```		
#vim /etc/httpd/conf.d/zabbix.conf		
Alias /oneoaas /usr/share/zabbix/oneoaas		
Alias /zabbix /user/share/zabbix		
```

#screenshot
http://t.cn/RqAeAxT 
http://t.cn/RcwoOGf 
项目捐款
==================================
如果你觉得本项目促进了您的生产力,欢迎对作者打赏,以资支持【让作者有更多动力去开发下个版本】  
打赏金额任意(注意:不接受大于500的高额赞赏)  

![image](https://github.com/OneOaaS/graphtrees/blob/master/image/wx.jpg) ![image](https://github.com/OneOaaS/graphtrees/blob/master/image/zfb.jpg)


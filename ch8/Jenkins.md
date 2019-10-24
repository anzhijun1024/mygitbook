# 2、tomcat中安装Jenkins


## 第一步：去官网下载jenkins的war包
[Jenkins官网](https://jenkins.io/zh/download/)：https://jenkins.io/zh/download/
官网下载jenkins war包大小约75M
![](/assets/jenkins下载.jpg)

## 第二步：上传war包到阿里云
**注意：**
把jenkins.war包移动到tomcat的webapps目录下自动解压，生成jenkins目录，直接访问，不用重启tomcat如果要删除Jenkins，直接删jenkins.war包，jenkins目录也会同时被删除
![](/assets/上传jenkins的war包.jpg)


## 第三步：直接访问jenkins安装jenkins
[地址](http://120.77.85.227:8080/jenkins/)：http://120.77.85.227:8080/jenkins/
![](/assets/jenkins报错.jpg)

报错如下：
AWT is not properly configured on this server. Perhaps you need to run your container with "-Djava.awt.headless=true"? See also: https://jenkins.io/redirect/troubleshooting/java.awt.headless


[解决方案如下：](https://www.cnblogs.com/sophia-985935365/p/10820245.html)https://www.cnblogs.com/sophia-985935365/p/10820245.html

解决方案：
1）在startup.sh文件增加一句：export CATALINA_OPTS="-Djava.awt.headless=true"

2）重启tomcat即可，刷新http://IP:8080/jenkins/
```
![](/assets/jenkins问题解决.jpg)

在次刷新依然报错
[在次百度解决方案如下：](https://blog.csdn.net/ssrc0604hx/article/details/52057716)https://blog.csdn.net/ssrc0604hx/article/details/52057716

根据上面的提示，发现是少了libxrender，于是执行命令
sudo apt-get install libxrender-dev
再次执行命令：apt-get install libxtst-dev
继续重启tomcat。
刷新页面，可以看到正常启动了

再次重启tomcat后问题解决
![](/assets/jenkins疑难问题解决.jpg)


## 第四步：在线安装jenkins并配置

**1、根据提示找到密码并输入**

![](/assets/复制初始密码jenkins.jpg)

**2、使用推荐安装插件**

![](/assets/jenkins推荐安装插件.jpg)

**3、jenkins安装中（这个过程很漫长）**

![](/assets/jenkins插件安装中.jpg)

**4、很明显很可能会出现初始启动安装推荐插件全部失败的情况**

![](/assets/jenkins安装插件全部失败.jpg)
**[解决方案：](https://www.cnblogs.com/sxdcgaq8080/p/10489326.html)**https://www.cnblogs.com/sxdcgaq8080/p/10489326.html

具体解决方案请参考看上方解决地址
这里的解决方案采用的是：去jenkins官网下载每周更新版（效果有很大改善）
![](/assets/jenkins每周更新版.jpg)
![](/assets/jenkins每周更新版有改善.jpg)
![](/assets/创建管理员用户.jpg)

![](/assets/示例配置.jpg)
**重启过程有点漫长**
![](/assets/重启过程有点漫长.jpg)



























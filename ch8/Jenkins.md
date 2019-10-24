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







































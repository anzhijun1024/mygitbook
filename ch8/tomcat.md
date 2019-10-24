[](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)# 1、阿里云部署tomcat


###　tomcat介绍

tomcat是干什么的？
**Tomcat是一个应用服务器。**
比如，假设我们浏览sina网的网页，而sina网的所有网页是配置在一个Tomcat服务器上的，那么，如果没有这个Tomcat来提供服务器端的服务的话，那你就打不开sina网的任何网页了。
**Tomcat是应用（java）服务器**，它只是一个servlet容器，是Apache的扩展，处理动态网页部分。

### 注意：
因为tomcat是用java开发的所以部署tomcat需要java环境支持所以第一步先安装好jdk环境，安装好后在解压配置tomcat


### 第一步 下载 java 环境需要的jdk

[1、去官网下载 jdk](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
地址：https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

![](/assets/java.png)

**2、下载的时候需要登录，登录成功后可以下载 下载可能比较久**
账号：2696671285@qq.com
密码：Oracle123
![](/assets/下载.jpg)

PS：开了vpn下载超快，没vpn慢慢下也能下载就是时间比较久
![](/assets/vpn.jpg)

**
3、下载成功后使用xftp工具把jdk上传到你自己的阿里云**

上传jdk到阿里云的software的azb目录下

![](/assets/上传java.jpg)

**4、解压jdk并配置好java的环境并验证**

解压jdk   命令： tar -zxvf jdk的文件名
![](/assets/java解压完成.jpg)


解压完成后 移动文件并重命名
将解压后的文件名移动后重命名为jdk8   命令：mv 旧文件名  新文件名

![](/assets/移动jdk.png)

**配置jdk的环境变量（重点内容） **

```
在根目录sudo vim etc/profile 在最后一行添加变量如下后退出保存
# java8 环境配置
export JAVA_HOME=/software/jdk8
export CLASSPATH=$JAVA_HOME/lib/
export PATH=$PATH:$JAVA_HOME/bin
export PATH JAVA_HOME CLASSPATH
```

查看java的路径并配置环境变量
![](/assets/配置java环境.jpg)
刚才配置写错了
![](/assets/java8.jpg)

配置好环境变量后需要保存退出使配置文件生效
使配置文件生效 在etc下运行文件生效命令 source profile(建议先执行sudo -s 命令)
![](/assets/java配置成功.jpg)



### 第二步：阿里云安装tomcat

**1、下载tomcat **
[官网地址](https://tomcat.apache.org/download-90.cgi)：https://tomcat.apache.org/download-90.cgi
![](/assets/tomcat下载.jpg)


**2、下载成功后 把tomcat上传到你自己的阿里云（直接拖就可以） 我这里上传到azb目录下**
![](/assets/tomcat上传.jpg)


**3、解压tomcat9并配置环境变量**

解压并重命名
![](/assets/解压并移动tomcat9.jpg)

配置tomcat9的环境变量
进去tomcat9的bin文件夹，通过编辑setclasspath.sh来配置jdk

```
# sudo vi setclasspath.sh
export JAVA_HOME=/software/jdk8
export JRE_HOME=/software/jdk8/jre
```
![](/assets/tomcat9环境配置.jpg)

**4、阿里云启动tomcat**
启动tomcat前确保阿里云的8080端口是否开放，没开放则开放（阿里云安全组）

![](/assets/8080端口.jpg)

启动tomcat 运行/software/tomcat9/bin 下的./startup.sh文件


# ./startup.sh
![](/assets/运行tomcat9.jpg)

到这一步之后就可以通过浏览器来访问了，输入http://云服务器的ip:8080
这里是：[我的阿里云的tomcat：](http://120.77.85.227:8080/)http://120.77.85.227:8080/

![](/assets/阿里云成功运行tomcat9.jpg)


################## 本节教程完毕#############



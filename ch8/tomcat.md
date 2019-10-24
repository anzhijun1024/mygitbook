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
开了vpn下载超快
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












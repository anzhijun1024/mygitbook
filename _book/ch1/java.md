
**在阿里云环境下安装java并配置环境大体分为以下4步：**
**1.官网下载jdk并上传到阿里云**
**2. 解压文件并重命名 并配置环境变量**
	用tar zxvf  跟上压缩包名称 解压
**3.并配置环境变量**
	jdk解压后更改环境变量：vim /etc/profile
	添加如下内容：JAVA_HOME根据实际目录来
	export JAVA_HOME=jdk的路径
	export CLASSPATH=$JAVA_HOME/lib/
	export PATH=$PATH:$JAVA_HOME/bin
	export PATH JAVA_HOME CLASSPATH
**4.启配置文件source /etc/profile  输入命令java -version 验证是否安装成功**

---------------------------------------------开始了----------------------------------------------------------
**第一步 下载 java 环境需要的jdk**

下载jdk的地址(官网)：https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628192627371.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1JlY29yZGluZ19zdHVkeQ==,size_16,color_FFFFFF,t_70)
	点击下载下载工具 idm 很快  下载可能需要登录分享账号密码如下
	账号：2696671285@qq.com
	密码：Oracle123
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628192924541.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1JlY29yZGluZ19zdHVkeQ==,size_16,color_FFFFFF,t_70)
下载好的jdk并使用xftp上传到我的阿里云/usr/local/software目录下

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628193202223.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1JlY29yZGluZ19zdHVkeQ==,size_16,color_FFFFFF,t_70)
**第二步 解压jdk并配置java环境变量**

	解压jdk   命令： tar -zxvf jdk的文件名
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628193508453.png)
	将解压后的文件名 重命名为jdk8   命令：mv 旧文件名  新文件名
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628193813960.png)

**第三步 配置jdk的环境变量** 
在根目录sudo vim etc/profile  在最后一行添加变量如下后退出保存
```
export JAVA_HOME=jdk的路径（/usr/local/software）
export CLASSPATH=$JAVA_HOME/lib/
export PATH=$PATH:$JAVA_HOME/bin
export PATH JAVA_HOME CLASSPATH
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628194656378.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1JlY29yZGluZ19zdHVkeQ==,size_16,color_FFFFFF,t_70)
**第四步 配置文件生效并验证jdk是否安装成功**

使配置文件生效  在etc下运行文件生效命令 source profile(建议先执行sudo -s 命令)![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628194943401.png)
查看 Java环境是否安装成功  运行命令 Java -vesion
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190628195024392.png)

---当你发现自己的才华撑csdc不起野心时，就请安静下来学习吧。---
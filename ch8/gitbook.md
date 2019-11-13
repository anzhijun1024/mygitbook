# 3、使用Jenkins自动化部署gitbook

## 所用到的技术有：git+github+gitbook+Jenkins+tomcat+node+阿里云



**gitbook在jenkins的持续集成部署思路：**
在本地使用gitbook编辑好电子书后，使用gitbook自带的上传工具上传到github指定的项目下，使用jenkins自动拉取gitbub项目到自己的阿里云服务器，并自动部署，外网即可访问。
**效果图如下：**

![](/assets/部署成功.jpg)

###　第一步：阿里云安装git

在Ubuntu 16.04上安装Git

步骤1：首先，通过运行以下命令确保您的系统和apt包列表完全更新：

apt-get update -y
apt-get upgrade -y


步骤2：**输入apt install git 命令安装git** 
使用以下命令来检查已安装的git版本：git --version  版本2.7.4 安装成功
![](/assets/git安装.jpg)


### 第二步：安装node
gitbook 核心是 node.js
[node.js linux 下载安装请参考csdn](https://blog.csdn.net/qq_31708763/article/details/82690129)：https://blog.csdn.net/qq_31708763/article/details/82690129
![](/assets/node.jpg)

如遇到npm软链不成功，建议去官网下载最新node方可解决

### 第三步：安装gitbook

gitbook Ubuntu下，在安装好nodejs后直接使用如下命令安装,依据自己安装的目录可能有权限问题，自行加上

npm install -g gitbook-cli
设置软链
sudo ln -s /software/node/bin/gitbook /usr/local/bin/gitbook
然后查看gitbook版本，检查是否安装成功。
gitbook -V #查看gitbook版本

![](/assets/gitbook01jpg.jpg)

![](/assets/gitbook02.jpg)





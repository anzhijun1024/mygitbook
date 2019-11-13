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

步骤1：运行命令
    npm install -g gitbook-cli
    
步骤2：设置软链 
    sudo ln -s /software/node/bin/gitbook /usr/local/bin/gitbook
    
步骤3：然后查看gitbook版本，检查是否安装成功
     gitbook -V 
 
 具体流程如下图
![](/assets/gitbook01jpg.jpg)

![](/assets/gitbook02.jpg)




### 第四步：安装gitbook及配置git密钥

步骤1：linux生成密钥
ssh-keygen -t rsa -C "1010666711@qq.com"
![](/assets/git在linux环境中生成密钥.jpg)

步骤2：在/root/.ssh 查看密钥
![](/assets/查看密钥.jpg)

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCmbfkAO/jEZ1C41WTaAGoIhU9Vuu+Hu4288lntYTUU7UfnxeRbwDa27MHNuEqcSYAxtvJQN2xvoL2n1vqUP6JcxfKRty/Mn/QABreuI8BxgdlqLxYyQ4Ww3XiIV8CQQ+YTuTKz9IX7lMA4BPsbNmx5uBs7TIXllBhntiCbO46LG0R4oBtBBUqqhCJdrLwunW79X/6ppv48hZnRiOwY4oq1wrx8twaLrB5tHZo7E8rogC4P/zxlYxfxrizUdjkwSFv9iNhxmK3LqRbrPuxg5cMvaeJtCjSVSYLIT0sKsRfKz2DJBggQ5Cv6+/m18Vjw5oWVg84PFfVgL6vT9gEs96sH 1010666711@qq.com

步骤3：git的密钥配置在github上
![](/assets/github密钥配置.jpg)


步骤4：验证git密钥配置是否生效
运行命令：ssh -T git@github.com
提示：Hi xxx! You've successfully authenticated, but GitHub does not provide shell  access.即为成功
![](/assets/验证git密钥.jpg)












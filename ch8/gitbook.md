# 3、使用Jenkins自动化部署gitbook

## 所用到的技术有：git+github+gitbook+Jenkins+tomcat+node+阿里云



**gitbook在jenkins的持续集成部署思路：**
在本地使用gitbook编辑好电子书后，使用gitbook自带的上传工具上传到github指定的项目下，使用jenkins自动拉取gitbub项目到自己的阿里云服务器，并自动部署，外网即可访问。
**效果图如下：**

![](/assets/部署成功.jpg)

###　第一步：阿里云安装git

# 1、windows本地搭建HttpRunnerManager接口自动化测试平台

### windows本地搭建需要提前准备的资料如下：
1、本地已安装mysql数据库，推荐mysql5.7+ 有客户端管理工具
2、python环境及pycharm已安装完毕且运行正常
3、HttpRunnerManager源码已下载完成
4、erlang安装包下载完毕
5、Rabbitmq包下载完毕


### 现在开始搭建本地接口自动化测试平台

### 第一步：在本地新建数据库

**1、使用的工具是：Navicat Premium 12 编码：utf-8 名称：httprunnermanag**er
![](/assets/新建数据库.jpg)
![](/assets/数据库新建成功.jpg)

### 第二步：下载项目源码
[源码github地址：](https://github.com/HttpRunner/HttpRunnerManager)https://github.com/HttpRunner/HttpRunnerManager

该项目自2018年9月起已停止维护使用python开发
**1、下载源码**
![](/assets/项目下载.jpg)

**2、解压源码并重命名至于D盘根目录**
![](/assets/下载解压完成.jpg)

### 第三步：安装erlang、Rabbitmq 准备环境

**1、下载erlang并配置环境**

Erlang 是一种通用的面向并发的编程语言，它由瑞典电信设备制造商爱立信所辖的 CS-Lab 开发，目的是创造一种可以应对大规模并发活动的编程语言和运行环境。

[下载地址：](http://www.erlang.org/downloads)http://www.erlang.org/downloads

**1、下载erlang**
![](/assets/下载erlang.jpg)

**2、[安装erlang](https://blog.csdn.net/g6256613/article/details/80191402)**
[安装教程：](https://blog.csdn.net/g6256613/article/details/80191402)https://blog.csdn.net/g6256613/article/details/80191402
![](/assets/配置erlang.jpg)

**3、配置erlang环境查看结果**
配置系统变量
![](/assets/配置成功.jpg)

**4、下载RabbitMQ并配置运行成功**
RabbitMQ 是一个由 Erlang 语言开发的 AMQP(高级消息队列协议)的开源实现。它支持多个消息传递协议。RabbitMQ 可以部署在分布式和联合配置中，以满足高规模、高可用性的需求，另外安装 rabbitmq 需要先安装erlang 。

[下载地址：](https://www.rabbitmq.com/download.html)https://www.rabbitmq.com/download.html

**下载RabbitMQ**
![](/assets/下载rabbitMQ.jpg)

**安装RabbitMQ**

遇到问题服务启动成功却无法访问
解决办法：完全卸载 rabbitMQ 包括注册表

[卸载教程：](https://blog.csdn.net/anbang713/article/details/82872880)https://blog.csdn.net/anbang713/article/details/82872880
[安装教程参考](https://www.cnblogs.com/saryli/p/9729591.html)：https://www.cnblogs.com/saryli/p/9729591.html
![](/assets/MQ命令.jpg)
![](/assets/rabbitmq成功.jpg)


### 第四步：使用pycharm导入项目 配置环境 安装环境依赖包

**1、导入开源项目**
![](/assets/数据库迁移成功.jpg)


**2、数据库配置**
打开 HttpRunnerManager 项目的 setting.py 文件，进行如下配置
![](/assets/数据库配置.jpg)
![](/assets/work配置.jpg)



**3、安装依赖库文件**
打开 cmd 命令窗口，切换到 HttpRunnerManager 目录，然后执行下面命令，自动安装需要的依赖库文件。 pip install -r requirements.txt 我这里一个一个装的 用命令装一直报错 例如：pip install locust

![](/assets/依赖包问题.jpg)




**4、执行数据库迁移操作**
python manage.py makemigrations ApiManager #生成数据迁移脚本
python manage.py migrate #应用到 db 生成数据表
创建超级用户，用户后台管理数据库，并按提示输入相应用户名，密码，邮箱。
python manage.py createsuperuser

**生成迁移脚本**
![](/assets/生成迁移脚本.jpg)

**迁移数据库成功**

**查看数据库是否成功**
![](/assets/数据库表迁移成功.jpg)
###　第五步：启动服务　

在项目根目录下面输入下面命令启动服务　python manage.py runserver
服务启动成功之后，打开如下地址，可以进入到不同的页面。
因主页没有配置需要进入注册页

注册页: http://127.0.0.1:8000/api/register/
登录: http://127.0.0.1:8000/api/login/
后台数据库管理：http://127.0.0.1:8000/admin/

**运行主程序**

![](/assets/运行主程序.jpg)

[注册页](http://127.0.0.1:8000/api/register/): http://127.0.0.1:8000/api/register/
![](/assets/注册页进行注册.jpg)

登录: http://127.0.0.1:8000/api/login/
![](/assets/用户登录.jpg)

登录成功页
![](/assets/主页.jpg)

## 本地搭建 HTTPRUNNERMANAGER 接口自动化测试平台成功 教程结束 2019年10月25日

还遗留一些小问题 页面样式，百度API问题之后慢解决

我遇到问题汇总：
1、rabbitMQ 装了半天
2、依赖包问题装了好久 










# 2、阿里云搭建接口自动化测试平台

## 环境配置

### 1、安装httprunner
使用 pip 命令进行安装
pip install httprunner
安装后校验是否安装成功，可以使用如下命令进行校验
hrun -V
2.3.2
har2case -V
0.3.1
![](/assets/httprun.jpg)

### 2、安装数据库




### 3、安装erlang
Erlang 是一种通用的面向并发的编程语言，它由瑞典电信设备制造商爱立信所辖的 CS-Lab 开发，目的是创造一种
可以应对大规模并发活动的编程语言和运行环境。
下载地址：http://www.erlang.org/downloads
下载erlang


下载完成后上传阿里云
#### 3.1 执行安装命令
dpkg -i esl-erlang_21.0-1_ubuntu_artful_amd64.deb
它会说，我缺少很多相关的依赖。
![](/assets/需要安装依赖.jpg)

#### 3.2 解决依赖问题
这个时候你需要执行：
apt-get -f install
然后会让你同意输入一个y。 
大概需要五分钟去执行。
![](/assets/解决依赖.jpg)

#### 3.3 再次执行安装命令
![](/assets/再次执行安装命令.jpg)
安装成功
![](/assets/erlang安装成功.jpg)

#### 3.4 验证erlang是否安装成功
erl    # 查看relang语言版本，成功执行则说明relang安装成功
![](/assets/验证erl.jpg)



### 4、安装RabbitMq
.由于rabbitMq需要erlang语言的支持，在安装rabbitMq之前需要安装erlang

#### 4.1 添加公钥

命令：wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -
![](/assets/添加公钥.jpg)


#### 4.2 更新软件包

命令：apt-get update

#### 4.3 安装 RabbitMQ
安装成功自动启动
命令：apt-get install rabbitmq-server  
![
](/assets/安装MQ.jpg)

#### 4.4 查看 RabbitMq状态
systemctl status rabbitmq-server   #Active: active (running) 说明处于运行状态
service rabbitmq-server status 用service指令也可以查看，同systemctl指令
![](/assets/MQ状态.jpg)


#### 4.5 启动、停止、重启
service rabbitmq-server start    # 启动
service rabbitmq-server stop     # 停止
service rabbitmq-server restart  # 重启 


#### 4.6 启用 web端可视化操作界面，我们还需要配置Management Plugin插件
rabbitmq-plugins enable rabbitmq_management   # 启用插件
service rabbitmq-server restart    # 重启




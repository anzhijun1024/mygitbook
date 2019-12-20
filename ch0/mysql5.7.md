# ubuntu16.04安装mysql 5.7 并实现远程连接
### 本文主要介绍在Ubuntu16.04安装MySQL，并用Window的Navicat连接到Ubuntu的MySQ



1、更新Ubuntu的apt
    sudo apt update
    
2、安装mysql
    sudo apt install mysql-server
    
3、安装过程中会提示我们设置MySQL root用户的密码，输入密码后，按tab键选中OK，回车确认
![](/assets/MYSQL.jpg)

4、确认密码，再输入与上一步相同的密码，按tab键选中OK，回车确认
![](/assets/再测确认.jpg)

5、安装完成后，MySQL服务讲自动被启动，可以用如下命令查查看mysql正在运行
    sudo netstat -tap | grep mysql
有类似如下输出为安装并启动成功 
![](/assets/musql运行.jpg)
 如执行命令后无任何输出，请检查是否安装好、确认mysql是否启动                           
     （mysql的启动命令为 service mysql start）
     
 6、用navicat连接mysql:
 ![](/assets/那白天.jpg)

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
 
 会有如下报2003错误
 ![](/assets/2003.jpg)
 
 接下来解决报错

修改mysqld.cnf文件，注释掉bind-address=127.0.0.1一行，注释方法：在行首添加 # 号
    udo nano /etc/mysql/mysql.conf.d/mysqld.cnf
    
找到bind-address  = 127.0.0.1一行，如下 
![](/assets/address.jpg)

重启Ubuntu MySQL服务
    sudo service mysql restart
    
输入MySQL密码，进入到mysql命令行，按如下步骤进行设置
    mysql> use mysql;
    Reading table information for completion of table and column names
    You can turn off this feature to get a quicker startup with -A
     
    Database changed
    mysql> select 'host' from user where user='root';
    +------+
    | host |
    +------+
    | host |
    +------+
    1 row in set (0.00 sec)
    mysql> update user set host = '%' where user ='root';
    Query OK, 1 row affected (0.00 sec)
    Rows matched: 1  Changed: 1  Warnings: 0
    mysql> flush privileges;
    Query OK, 0 rows affected (0.00 sec)
    mysql> select 'host'   from user where user='root';
    +------+
    | host |
    +------+
    | host |
    +------+
    1 row in set (0.00 sec)
    mysql>
    mysql> quit;
    Bye


再次点击Navicat的连接测试，提示连接成功

![](/assets/连接数据库成功.jpg)


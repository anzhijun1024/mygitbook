# ubuntu16.04安装python3.7

### 1.下载、安装、校验、Python 3.7.0
#### 1.1下载python3.7.0
wget http://www.python.org/ftp/python/3.7.0/Python-3.7.0.tgz

#### 1.2 解压python3.7.0
tar -xvzf Python-3.7.0.tgz

#### 1.3 安装python3.7.0
cd Python-3.7.0
./configure --with-ssl
make
sudo make install

#### 1.4 校验python3.7.0是否安装成功
输入Python3 ：出现：即成功
 ![](/assets/校验.jpg)

### 2.安装Python编译外部模块文件使用的Python-dev:

命令：sudo apt-get install python-dev

### 3.安装包管理PIP

sudo apt-get install python-pip

升级PIP
sudo pip3 install --upgrade pip
![](/assets/升级pip.jpg)

### 4、查看已经安装的python版本和pip版本

查看pip版本
![](/assets/pip列表.jpg)

查看python3.7版本
![](/assets/python3版本.jpg)

### 5、如何实现把python3.7设置成全局变量
#### 5.1 删除/usr/bin/python原来的软链  
进入/usr/bin/目录下执行如下命令
rm python 即可  查看是否删除 ll

#### 5.2 设置新软链
命令：ln -s /software/python3.7.0/python /usr/bin/python

![](/assets/新软链.jpg)



# ubuntu16.04安装jmeter


### 第一步 解压jmeter
    命令：tar -zxvf apache-jmeter-5.1
    
    
#### 第二步 重命名
    mv apache-jmeter-5.1 ../jmeter5.1 
    
   
### 第三步 配置环境 

    # jmeter环境配置
    export JMETER_HOME=/software/jmeter5.1
    export CLASSPATH=$JMETER_HOME/lib/ext/ApacheJMeter_core.jar:$JMETER_HOME/lib/jorphan.jar:$CLASSPATH
    export PATH=$JMETER_HOME/bin:$PATH:$HOME/bin
    
![](/assets/jmeter.jpg)

### 第四步 查看版本
    java -version
![](/assets/java -version.jpg)
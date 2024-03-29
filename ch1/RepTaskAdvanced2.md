# **HTTP 功能**

**HTTP** 协议（HyperText Transfer Protocol，超文本传输协议）是用于从服务器传输超文本到本地浏览器的传输协议。它可以使浏览器更加高效，使网络传输减少。它不仅保证计算机正确**快速地传输超文本文档**，还确定**传输**文档中的哪一部分，以及哪部分内容首先显示(如**文本先于图形**)等。

# **HTTP 特点**

•  **无连接**：无**连接的含义是限制每次连接只处理一个请求**。服务器处理完客户的请求，并收到客户的应答后，即断开连接。**采用这种方式可以节省传输时间**。

• ** 媒体独立**：这意味着，只要客户端和服务器知道如何处理的数据内容，任何类型的数据都可以通过 HTTP发送。客户端以及服务器指定使用适合的 **MIME-type **来传输。 详见：[MIME 参考手册](https://www.w3school.com.cn/media/media_mimeref.asp)

•  **无状态**：HTTP 协议是无状态协议。**无状态是指协议对于事务处理没有记忆能力**。如果服务器不需要先前信息，那么它的应答就比较快。但是缺少状态意味着如果后续处理需要前面的信息，则它必须**重传**，这样可能导致每次连接传送的数据量增大，此时**可以设置缓存**。

![](/assets/MME.jpg)


# **HTTP 与 HTTPS**

现在在浏览很多网站时，通过浏览器地址栏可以看到有的网站是 https 开头（https://www.baidu.com/ ）, 但是有的是 http 开头（如：http://www.weather.com.cn ）这两种有什么区别呢？难道加了 s 就是复数吗？HTTPS 的全称是 Hyper Text Transfer Protocol over Secure Socket Layer，是以安全为目标的 HTTP 通道，**简单讲是 https是HTTP 的安全版，即 HTTP 下加入 SSL 层（Secure Sockets Layer 安全套接层），简称为 HTTPS。**
**S 其实是 Security 单词的首字母。**


**HTTPS 的安全基础是 SSL，因此通过它传输的内容都是经过 SSL 加密的，它的主要作用可以分为两种：**

**1.** 是建立一个**信息安全通道**，来**保证数据传输的安全**。
**2.** **确认网站的真实性**，凡是使用了 https 的网站，都可以通过点击浏览器地址栏的**锁头标志**来查看网站认证之后的真实信息，也可以通过** CA **机构颁发的安全签章来查询。

现在越来越多的网站和 APP 都已经向 HTTPS 方向发展。例如：谷歌从 2017 年 1 月推出的 Chrome 56 开始，对未进行 HTTPS 加密的网址链接亮出风险提示，即在地址栏的显著位置提醒用户“此网页不安全”。

![](/assets/私密链接.jpg)
![](/assets/百度证书.jpg)

# **HTTP 与 TCP/IP 的区别**

**TCP/IP 协议是传输层协议**，主要解决数据如何在网络中传输，而 HTTP 是应用层协议，主要解决如何包装数据。关于 TCP/IP 和 HTTP 协议的关系，网络有一段比较容易理解的介绍：“我们在传输数据时，可以只使用（传输层）TCP/IP 协议，但是那样的话，如果没有应用层，便无法识别数据内容，如果**想要使传输的数据有意义，则必须使用到应用层协议**，应用层协议有很多，比如 HTTP、FTP、TELNET 等，也可以自己定义应用层协议。**WEB 使用 HTTP协议作应用层协议，以封装 HTTP 文本信息，然后使用 TCP/IP 做传输层协议将它发到网络上。”**























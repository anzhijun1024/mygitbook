# 1-7 HTTP请求头与请求URL 

# **Request Headers**

请求头，用来说明服务器要使用的附加信息，比较重要的信息有 Cookie、Referer、User-Agent 等，下面将一些常用的头信息说明如下：

•  Accept ，请求报头域，用于指定客户端可接受哪些类型的信息。
•  Accept-Language ，指定客户端可接受的语言类型。
•  Accept-Encoding ，指定客户端可接受的内容编码。

•  Host ，用于指定请求资源的主机 IP 和端口号，其内容为请求 URL 的原始服务器或网关的位置。从 HTTP1.1 版本开始，Request 必须包含此内容。

•  **Cookie **，也常用复数形式 Cookies，是网站为了辨别用户进行Session 跟踪而储存在用户本地的数据。Cookies 的主要功能就是维持当前访问会话。

•  **Referer  **此内容用来标识这个请求是从哪个页面发过来的，服务器可以拿到这一信息并做相应的处理，如做来源统计、做防盗链处理等。

•  **User-Agent **，简称 UA，它是一个特殊字符串头，使得服务器能够识别客户使用的操作系统及版本、浏览器及版本等信息。在做爬虫时加上此信息可以伪装为浏览器，如果不加很可能会被识别出为爬虫。

•  Content-Type ，即 Internet Media Type，互联网媒体类型，也叫做 MIME 类型，在 HTTP 协议消息头中，使用它来表示具体请求中的媒体类型信息。例如  application/x-www-form-urlencoded 表示表单数据，  text/html 代表 HTML 格式， image/gif 代表 GIF 图片， application/json 代表 Json 类型，
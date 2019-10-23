# **Response**

Response，即响应，由服务端返回给客户端。Response 可以划分为三部分:
•  Response Status Code
•  Response Headers
•  Response Body

# **Response Status Code**

响应状态码，此状态码表示了服务器的响应状态，如 200 则代表服务器正常响应， 404 则代表页面未找到， 500 则代表服务器内部发生错误。常用响应状态码如下

状态码  说明  详情
200  成功  服务器已成功处理了请求。
201  已创建  请求成功并且服务器创建了新的资源。
301  永久移动  请求的网页已永久移动到新位置，即永久重定向。
302  临时移动  请求的网页暂时跳转到其他页面，即暂时重定向。
400  错误请求  服务器无法解析该请求。
401  未授权  请求没有进行身份验证或验证未通过。
403  禁止访问  服务器拒绝此请求。
404  未找到  服务器找不到请求的网页。
500  服务器内部错误  服务器遇到错误，无法完成请求。
501  未实现  服务器不具备完成请求的功能。
502  错误网关  服务器作为网关或代理，从上游服务器收到无效响应。

扩展资料：[HTTP 响应码](http://tool.oschina.net/commons?type=5)

![](/assets/状态码.jpg)

# **Response Headers**
响应头，其中包含了服务器对请求的应答信息，如 Content-Type、Server、Set-Cookie 等，下面将一些常用的头信息说明如下：

•  Date ，标识 Response 产生的时间。
•  Last-Modified ，指定资源的最后修改时间。
•  Content-Encoding ，指定 Response 内容的编码。
•  Server ，包含了服务器的信息，名称，版本号等。
•  Content-Type ，文档类型，指定了返回的数据类型是什么，如 text/html 则代表返回 HTML 文档，application/x-javascript 则代表返回 JavaScript 文件，image/jpeg 则代表返回了图片。
•  Set-Cookie ，设置 Cookie，Response Headers 中的 Set-Cookie 即告诉浏览器需要将此内容放在
Cookies 中，下次请求携带 Cookies 内容。
•  Expires ，指定 Response 的过期时间，使用它可以控制代理服务器或浏览器将内容更新到缓存中，如果再次访问时，直接从缓存中加载，降低服务器负载，缩短加载时间。


# **Response Body**

即响应体，响应的正文数据都是在响应体中，如请求一个网页，它的响应体就是网页的 HTML 代码，请求一张图片，它的响应体就是图片的二进制数据。一般在接口的响应内容大多都是 Json 数据内容.


# 参考资料

•  https://baike.baidu.com/item/http/243074?fr=aladdin#2
•  https://germey.gitbooks.io/python3webspider/content/2.1-HTTP 基本原理.html
•  https://www.cnblogs.com/duanxz/p/5127561.html



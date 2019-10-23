# **Request Body**

即请求体，一般用于 POST 请求中，主要定义向服务器提交的数据类型，而对于 GET 请求 Request Body 则为空。

比如在登录之前我们填写了用户名和密码信息，提交时就这些内容就会以  Form Data 的形式提交给服务器，此时注意  Request Headers 中指定了 Content-Type 为  application/x-www-form-urlencoded ，只有设置  Content-Type 为  application/x-www-form-urlencoded 才会以  Form Data 形式提交，另外我们也可以将Content-Type 设置为  application/json 来提交  Json 数据，或者设置multipart/form-data 来上传文件。

常用 Content-Type 和 POST 提交数据方式的关系：

Content-Type  提交数据方式
application/x-www-form-urlencoded  Form 表单提交
multipart/form-data  表单文件上传提交
pplication/json  序列化 Json 数据提交
text/xml  XML 数据提交


## application/x-www-form-urlencoded 与 multipart/form-data 区别

•  在没有 type=file 时候，用默认的  application/x-www-form-urlencoded 就行。
•  在有  type=file 时候，要用 multipart/form-data 编码方式。浏览器会把表单以控件为单位分割，并且为每个部分加上 Content-Dispositon(form-data 或 file) 、 Content-Type (默认 text/plain)、 name (控件 name)等信息，并加上分割符(boundary)。
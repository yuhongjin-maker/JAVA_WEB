# HTTP-请求数据格式

## HTTP-请求数据格式

1. 请求行：请求数据的第一行。其中GET表示请求方式， /表示请求资源路径，HTTP/1.1表示协议版本
2. 请求头：第二行开始，格式为key：value形式
3. 请求体：POST请求的最后一部分，存放请求参数

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

### 常见的HTTP请求头：

* Host：表示请求的主机名
* User-Agent：浏览器版本，例如Chrome浏览器的标识类似Mozilla/5.0...
* Chrome/79,IE浏览器的标识类似Mozila/5.0(Windows NT...)like Gecko
* Accept:表示浏览器能接受的资源类型，如text/\*,image/\*或者/\*/\*表示所有
* Accept-Language:表示浏览器偏好的语言，服务器可以据此返回不同语言的网页
* Accept-Encoding:表示浏览器可以支持的压缩类型，例如gzip,deflate等

### Get请求和POST请求区别

1. Get请求参数在请求行中，没有请求体。POST请求请求参数在请求体中
2. Get请求请求参数大小有限制，POST没有

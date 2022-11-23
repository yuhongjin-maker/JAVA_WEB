# HTTP-响应数据格式

## 响应数据分为3部分

1. 响应行：响应数据的第一行。其中HTTP/1.1表示协议版本，200表示响应状态码，OK表示状态码描述
2. 响应头：第二行开始，格式为key:value形式
3. 响应体：最后一部分。存放响应数据

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

### 常见的HTTP响应头

* Content-Type：表示该响应内容的类型，例如text/html,image/jpeg
* Content-Length: 表示该响应内容的长度（字节数）
* Content-Encoding:表示该响应压缩算法，例如：gzip
* Cache-Control:指示客户端应如何缓存，例如max-age=300 表示可以最多缓存300秒


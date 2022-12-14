# Requet获取请求数据

## 获取请求数据

### 请求行

```
Get/request-demo/req1?username=zhangsan HTTP/1.1
```

* String getMethod(): 获取请求方式：GET
* String getContextPath():获取虚拟目录(项目访问路径)：/request-demo
* StringBuffer getRequestURL():获取URL(统一资源定位符)：https://localhost:8080/request-demo/req1
* String getRequestURL(): 获取URL（统一资源定位符）：/request-demo/req1
* String getQueryString():获取请求参数(GET方式)：username=zhangsan\&password=123

### 请求头

```
User-Agent:Mozilla/5.0 Chrome/91.0.4472.106
```

* String getHeader(String name):根据请求头名称，获取值

### 请求体

```
username=superbaby&password=123
```

* ServletputStream getInputStream(): 获取字节输入流
* BufferReader getReader(): 获取字符输入流

## 通过通用方式获取请求参数

#### 请求参数获取方式

#### GET方式

```
String getQueryString()
```

#### POST方式

```
BufferReader getReader()
```

<figure><img src="../.gitbook/assets/image (1) (1) (4).png" alt=""><figcaption></figcaption></figure>

## 请求参数中文乱码处理

请求参数如果存在中文数据，则会乱码

#### 解决方法

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

<pre><code>// URL编码
String encode = URLEncoder.encode(username,"utf-8");

//URL解码,因为Tomcat不能直接设置为utf-8没有给外部接口
String decode = URLDecoder.decode(encode,"ISO-8859-1");
//以上URL编码实现

//转换成字节数据
<strong>byte[] = decode.getBytes("ISO-8859-1");
</strong>
//将字节数组转为字符串
String s = new String(bytes,"utf-8");
</code></pre>

#### Tomcat 8.0后已将GET请求乱码问题解决，设置默认的解码方式为UTF-8

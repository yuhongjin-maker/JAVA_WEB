# Request\&Response介绍

<figure><img src="../.gitbook/assets/image (1) (5).png" alt=""><figcaption></figcaption></figure>

```
// Example Code
//使用request 对象，获取请求数据
String name =request.getParameter("name");

//使用response 对象，设置响应数据
response.setHeader("content-type","text/html;charset=utf-8")
response.getWriter().writer(name+"helloworld");
```

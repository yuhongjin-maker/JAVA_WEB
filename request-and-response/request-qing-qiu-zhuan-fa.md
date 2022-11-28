# Request请求转发

## 请求转发

* 请求转发(forward):一种在服务器内部的资源跳转方式

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## 实现方式

```
req.getRequestDispatcher("资源B路径").forward(req,resp);
```

## 请求转发资源间共享数据：使用Request对象

* void setAttribute(String name, Object o): 存储数据到request域中
* Object getAttribute(String name):根据key,获取值
* void removeAttribute(String name):根据key，删除改键值对

## 请求转发特点

* 浏览器地址路径不发生变化
* 只能转发到当前服务器的内部资源
* 一次请求，可以在转发的资源间使用request共享数据

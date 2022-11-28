# Response完成重定向

## Response完成重定向

* 重定向(Redirect):一种资源跳转方式

<figure><img src="../.gitbook/assets/image (1) (10).png" alt=""><figcaption></figcaption></figure>

## 实现方式

```
resp.setStatus(302);
resp.setHeader("location","资源B的路径");
//简化方式
resp.sendRedirect("资源B的路径")
```

## 重定向特点

* 浏览器地址栏路径发生变化
* 可以重定向到任意位置的资源（服务器内部、外部均可）
* 两次请求，不能在多个资源使用request共享数据

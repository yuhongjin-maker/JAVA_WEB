# 路径问题

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

```
// 动态获取虚拟目录的方式
String contextPath = request.getContextPath();

response.sendRedirect(contextPat+"/resp2");
```

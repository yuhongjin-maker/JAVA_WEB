# Response响应字符数据

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

1. 该流不需要关闭，随着响应结束，response对象销毁，由服务器关闭
2. 中文数据乱码：原因通过Response获取的字符输出流默认编码:ISO-8859-1

```
resp.setContentType("text/html;charset=utf-8")
```

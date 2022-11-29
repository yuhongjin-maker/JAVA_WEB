# EL表达式

* Expression Language表达式语言，用于简化JSP页面内的Java代码
* 主要功能：获取数据
* 语法：${expression}

```
// 获取域中存储的key为brands的数据
${brands}
```

### JavaWeb中的四大域对象

1. page:当前页面有效
2. request:当前请求有效
3. session:当前会话有效
4. application:当前应用有效

![](<../.gitbook/assets/image (7).png>)

#### el表达式获取数据，会依次从这4个域中寻找，直到找到为止

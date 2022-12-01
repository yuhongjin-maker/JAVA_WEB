# Session

服务端会话跟踪技术：将数据保存到服务端

Java EE提供HttpSession接口，来实现一次会话的多次请求间数据共享功能

## 基本使用

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-30 at 12.47.02 AM.png" alt=""><figcaption></figcaption></figure>

## Session原理

* Session是基于Cookie实现的

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

## Session使用细节

### Session钝化、活化

* 服务器重启后，Session中的数据是否还在
* 钝化：在服务器正常关闭后，Tomcat会自动将Session数据写入硬盘的文件中
* 活化：再次启动服务器后，从文件中加载数据到Session中

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

### Session销毁

* 默认情况下，无操作，30分钟自动销毁

```
//在web.xml配置
<session-config>
    <session-timeout>30</session-timeout>
</session-config>
```

* 调用Session对象的incalidate()方法

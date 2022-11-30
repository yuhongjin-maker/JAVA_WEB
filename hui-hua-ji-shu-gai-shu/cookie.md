# Cookie

#### Cookie：客户端会话技术，将数据保存到客户端，以后每次请求都携带Cookie数据进行访问

## Cookie基本使用

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-30 at 12.13.27 AM.png" alt=""><figcaption></figcaption></figure>

## Cookie原理

Cookie的实现是基于HTTP协议的

* 响应头：set-cookie
* 请求头：cookie

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-30 at 12.21.42 AM.png" alt=""><figcaption></figcaption></figure>

## Cookie使用细节

### Cookie存活时间

* 默认情况下，cookie存储在浏览器内存中，当浏览器关闭，内存释放，则Cookie被销毁
* setMaxAge(int second)：设置Cookie存活时间

1. 正数：将Cookie写入浏览器所在电脑的硬盘，持久化存储。到时间自动删除
2. 负数：默认值，Cookie在当前浏览器内存中，当浏览器关闭，则Cookie被销毁
3. 零：删除对应Cookie


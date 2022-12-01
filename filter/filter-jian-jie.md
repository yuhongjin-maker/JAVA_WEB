# Filter简介

* 概念：Filter表示过滤器，是JavaWeb三大组件(Servlet、Filter、Listener)之一
* 过滤器可以把对资源的请求拦截下来，从而实现一些特殊的功能
* 过滤器一般完成一些通用的操作，比如：权限控制、统一编码处理、敏感字符处理等等..

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

## Filter快速入门

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

## Filter执行流程

#### 执行放行前逻辑 --> 放行 --> 访问资源 --> 执行放行后逻辑

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>


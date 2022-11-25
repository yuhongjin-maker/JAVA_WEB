# Servlet

* Servlet是Java提供的一门动态web资源开发技术
* Servlet是JavaEE规范之一，其实就是一个接口，将来我们需要定义Servlet类实现Servlet接口，并由web服务器运行Servlet

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

## Servlet快速入门

<figure><img src="../.gitbook/assets/image (2) (2).png" alt=""><figcaption></figcaption></figure>

## Servlet执行流程

#### Servlet由web服务器创建，Servlet方法由web服务器调用

#### 因为我们自定义的Servlet，必须实现Servlet接口并复写其方法，而Servlet接口中service方法

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

## Servlet生命周期

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

## Servlet方法

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Servlet体系结构

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### HttpServlet使用步骤

1. 继承HttpServlet
2. 重写doGet和doPost方法

### HttpServlet原理

获取请求方式，并根据不同的请求方式，调用不同的doXxx方法

## Servlet urlPattern配置

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

### urlPattern配置规则

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

#### 当一个路径同时满足精确匹配和目录匹配时，精确匹配的优先级要高于目录匹配

#### / 和 /\* 的区别：

* 当我们项目中的Servlet配置了"/",会覆盖掉tomcat中的DefaultServlet，当其它的url-pattern都匹配不上时都会走这个Servlet
* 当我们的项目中配置了"/\*",意味着匹配任意访问路径

#### 优先级：

精确路径>目录路径>扩展名路径>/\*>/

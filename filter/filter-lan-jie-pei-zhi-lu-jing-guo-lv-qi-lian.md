# Filter拦截配置路径&过滤器链

## Filter拦截路径配置

* Filter可以根据需求，配置不同的拦截资源路径

<figure><img src="../.gitbook/assets/image (1) (10).png" alt=""><figcaption></figcaption></figure>

## 过滤器链

* 一个Web应用，可以配置多个过滤器，这多个过滤器称为过滤器链
* 注解配置的Filter,优先级按照过滤器类名字（字符串）的自然排序

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

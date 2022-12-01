# Vue常用指令和生命周期

* 指令：HTML标签上带有v-前缀的特殊属性，不同指令具有不同意义。例如:v-if,v-for

## 常用指令

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## 生命周期

#### 生命周期的八个阶段：每触发一个生命周期事件，会自动执行一个生命周期方法

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### mounted:挂载完成，Vue初始化成功，HTML页面渲染成功

* 发送异步请求，加载数据

```
// Example Code
new Vue({
    el:"#app",
    mounted(){
        alert("vue挂载完毕，发送异步请求");
    }
);
```

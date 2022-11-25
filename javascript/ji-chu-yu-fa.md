# 基础语法

## 书写语法

1. 区分大小写
2. 每行结尾的分号可有可无
3. 注释

* 单行注释：//
* 多行注释：/\* 注释内容 \*/

&#x20;4\. 大括号表示代码块

```
if (count == 3){
    alert(count);
}
```

## 输出语句

* 使用window.alert()写入警告框
* 使用document.write()写入HTML输出
* 使用console.log()写入浏览器控制台

```
window.alert("hello JS~"); //弹出警告框
document.write("hello JS~"); //写入HTML
console.log("hello JS~");//写入控制台
```

## 变量

<figure><img src="../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

## 数据类型

<figure><img src="../.gitbook/assets/image (2) (3).png" alt=""><figcaption></figcaption></figure>

## 运算符

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

### ==：

1. 判断类型是否一样，如果不一样，则进行类型转换
2. 再去比较其值

### ===：

1. 判断类型是否一样，如果不一样，直接返回false
2. 再去比较其值

## 类型转换

### 其他类型转为number

* string：按照字符串的字面值，转为数字。如果字面值不是数字，则转为NaN,一般使用parseInt
* boolean: true 转为1，false转为0

### 其他类型转为boolean

* number:0和NaN转为false,其他数字转为true
* string:空字符串转为false，其他字符串转为true
* null:false
* undefined:false

## 流程控制语句

* if
* switch
* for
* while
* do....while

#### 与JAVA类似&#x20;

## 函数

<figure><img src="../.gitbook/assets/image (9) (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1) (5).png" alt=""><figcaption></figcaption></figure>

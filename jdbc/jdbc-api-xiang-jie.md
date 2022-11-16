# JDBC API详解

## DriverManager（驱动管理类）作用

1. 注册驱动
2. 获取数据库连接

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

## Connection

* Connection（数据库连接对象）作用：

1. 获取执行SQL的对象
2. 管理事务

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

## Statement

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

## ResultSet

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

## PreparedStatement

#### PreparedStatment作用

1. 预编译SQL语句执行：预防SQL注入问题

#### SQL注入

* SQL注入式通过操作输入来修改事先定义好的SQL语句，用以达到执行代码对服务器进行攻击的方法


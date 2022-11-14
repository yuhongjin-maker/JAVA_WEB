# 数据库设计

## 数据库设计概述

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

## 表关系

* 一对一（如：用户和用户详情）
* 一对多 （如：部门和员工）
* 多对多（商品和订单）

### 一对多

* 实现方式：在多的一方建立外键，指向一的一方的主键

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

### 多对多

* 实现方式：建立第三张中间表，中间表至少包含两个外键，分别关联两方主键

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### 一对一

* 实现方式：在任意一方加入外键，关联另一个主键，并且设置外键为UNIQUE

<figure><img src="../.gitbook/assets/image (1) (3).png" alt=""><figcaption></figcaption></figure>

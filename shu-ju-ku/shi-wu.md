# 事务

## 事务简介

* 数据库的事务（Transaction）是一种机制、一个操作序列，包含了一组数据库操作命令
* 事务把所有命令作为一个整体一起向系统提交或撤销操作请求，即这一组数据库命令要么同时成功，要么同时失败
* 事务是一个不可分割的工作逻辑单元

<figure><img src="../.gitbook/assets/Screen Shot 2022-11-14 at 7.09.03 PM.png" alt=""><figcaption></figcaption></figure>

## 事务四大特征

* 原子性(Atomicity)：事务时不可分割的最小操作单位，要么同时成功，要么同时失效
* 一致性(Consistency)：事务完成时，必须使所有的数据都保持一致状态
* 隔离性(Isolation)：多个事务之间，操作的可见性
* 持久性(Durability)：事务一旦提交或回滚，它对数据库中的数据的改变就是永久的

### MySQL事务默认自动提交

# 删除

## 删除一个

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

## 批量删除

<figure><img src="../.gitbook/assets/image (6) (3).png" alt=""><figcaption></figcaption></figure>

#### Mybatis 会将数组参数，封装成一个Map集合

* 默认：array = 数组
* 使用@Param注解改变map集合的默认key的名称

```
// 代码优化
<delete from tb_brand whre id>
 in 
     <foreach collection="ids" item="id" separator="," open="(" close=")">
         #{id}
     </foreach>
     ;
 </delete>
         
```

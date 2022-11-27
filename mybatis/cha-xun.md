# 查询

<figure><img src="../.gitbook/assets/image (2) (2).png" alt=""><figcaption></figcaption></figure>

## 查询-所有数据

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

### 数据库表的字段名称和实体类的属性名称不一样则不能自动封装数据

* 起别名：在SQL语句中，对不一样的列名起别名，别名和实体类属性名一样 \* 可以定义\<sql>片段，提升复用性
* resultMap：定义\<resultMap>完成不一致的属性名和列名的映射

<pre><code>// resultMap
//id : 唯一标识
//type: 映射的类型。支持别名
/*
id:完成主键字段的映射
<strong>column:表的列名
</strong>property:实体类的属性名
result:完成一般字段的映射
column:表的列名
property:实体类的属性名
*/
    &#x3C;resultMap id="brandResultMap" type="brand">
        &#x3C;result column="brand_name" property="brandName"/>
        &#x3C;result column="company_name" property="companyName"/>
    &#x3C;/resultMap>

    &#x3C;select id="selectAll" resultMap = "brandResultMap">
    select 
        *
    from tb_brand;
    &#x3C;/select>
</code></pre>

## 查询-查看详情

<figure><img src="../.gitbook/assets/image (3) (4).png" alt=""><figcaption></figcaption></figure>

### 参数占位符

1. \#{}:会将其替换成?.为了防止SQL注入
2. ${}:拼sql,会存在SQL注入问题

### 参数类型

parameterType:可以省略

### 特殊字符处理

1. 转义字符
2. CDATA区

## 查询-条件查询

### 多条件查询-静态

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

### SQL语句设置多个参数有三种方式

1. 散装参数：需要使用@Param("SQL中的参数占位符名称")
2. 实体类封装参数：只需要保证SQL中的参数名和实体类属性名对应上，即可设置成功
3. map集合：只需要保证SQL中的参数名 和 map集合的键的名称对应上，即可设置成功

### 多条件查询-动态

<figure><img src="../.gitbook/assets/image (2) (4).png" alt=""><figcaption></figcaption></figure>

#### if：用于判断参数是否有值，使用test属性进行条件判断

存在的问题：第一个条件不需要逻辑运算符

解决方案

1. 使用恒等式让所有条件格式都一样
2. \<where>标签替换where关键字

```
// Example Code
<select id="selectByCondition" resultMap="brandResultMap">
            select * from tb_brand
    <where>
        <if test="status != null">
            and status = #{status}
        </if>
        <if test="companyName != null and companyName != '' ">
            and company_name like #{companyName}
        </if>
        <if test="brandName != null and brandName != ''">
            and brand_name like #{brandName}
        </if>
    </where>
</select>
```

### 单条件查询-动态

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

#### 可以用\<where>标签把它们包裹起来进行优化

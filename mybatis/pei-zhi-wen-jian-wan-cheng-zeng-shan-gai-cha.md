# 配置文件完成增删改查

## 功能列表清单

1. 查询

* 查询所有数据
* 查看详情
* 条件查询

&#x20;2\.  添加

&#x20;3\.  修改

* 修改全部字段
* 修改动态字段

&#x20;4\.  删除

* 删除一个
* 批量删除

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

## 查询所有数据

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

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

### 参数占位符

1. \#{}:会将其替换成?.为了防止SQL注入
2. ${}:拼sql,会存在SQL注入问题

### 参数类型

parameterType:可以省略

### 特殊字符处理

1. 转义字符
2. CDATA区


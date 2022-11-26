# Mapper代理开发

## 目的

* 解决原生方式的硬编码
* 简化后期执行SQL

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## 步骤

<figure><img src="../.gitbook/assets/image (1) (8).png" alt=""><figcaption></figcaption></figure>

```
// 包扫描只需要在mybatis_config.xml <mapper>标签下修改
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "https://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>
    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <property name="driver" value="com.mysql.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///account?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="1234"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
<!--        Mapper代理方式-->
        <package name ="myb.mapper"/>
    </mappers>
</configuration>
```

```
// main 的代码优化
//1. 加载mybatis的核心配置文件，获取SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory =
                new SqlSessionFactoryBuilder().build(inputStream);

        //2. 获取SqlSession对象，用它来执行sql
        SqlSession sqlSession  = sqlSessionFactory.openSession();

        //3.1 获取UserMapper接口的代理对象
        UserMapper userMapper = sqlSession.getMapper(UserMapper.class);
        List<demo1> users = userMapper.selectAll();


        System.out.println(users);

        //4. 释放资源
        sqlSession.close();
```

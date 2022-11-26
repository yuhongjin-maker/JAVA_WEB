# MyBatis快速入门

1. 创建 user 表，添加数据
2.  创建模块，导入坐标

    在 main 目录下的 resoures 配置文件目录下创建一个名为 logback.xml 的配置文件，粘贴一下内容：

    ```
     <?xml version="1.0" encoding="UTF-8"?>
       <configuration>
           <!--
               CONSOLE ：表示当前的日志信息是可以输出到控制台的。
           -->
           <appender name="Console" class="ch.qos.logback.core.ConsoleAppender">
               <encoder>
                   <pattern>【%level】 %blue(%d{HH:mm:ss.SSS}) %cyan(【%thread】) %boldGreen(%logger{15}) - %msg %n</pattern>
               </encoder>
           </appender>
       
           <logger name="com.itheima" level="DEBUG" additivity="false">
               <appender-ref ref="Console"/>
           </logger>

           <root level="DEBUG">
               <appender-ref ref="Console"/>
           </root>
       </configuration>
    ```
3. 编写 MyBatis 核心配置文件 在 main 目录下的 resoures 配置文件目录下创建一个名为 mybatis-config.xml 的配置文件，内容在MyBatis官网
4.  编写 sql 映射文件

    在 main 目录下的 resoures 配置文件目录下创建一个名为 UserMapper.xml 的配置文件，内容在MyBatis官网
5. 编码

* 定义POJO类
* 加载核心配置文件，获取SqlSessionFactory对象
* 获取SqlSession对象，执行SQL语句
* 释放资源

```
// logback.xml 配置
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <!--
        CONSOLE ：表示当前的日志信息是可以输出到控制台的。
    -->
    <appender name="Console" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>【%level】 %blue(%d{HH:mm:ss.SSS}) %cyan(【%thread】) %boldGreen(%logger{15}) - %msg %n</pattern>
        </encoder>
    </appender>

    <logger name="com.itheima" level="DEBUG" additivity="false">
        <appender-ref ref="Console"/>
    </logger>

    <root level="DEBUG">
        <appender-ref ref="Console"/>
    </root>
</configuration>
```

```
// mybatis_config.xml
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
                
                //这里记得用哪个database就改哪个
                <property name="url" value="jdbc:mysql:///account?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="1234"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
        <mapper resource="UserMapper.xml"/>
    </mappers>
</configuration>
```

```
// UserMapper.xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "https://mybatis.org/dtd/mybatis-3-mapper.dtd">

//这里写硬编码
<mapper namespace="test">
    <select id="selectAll" resultType="myb.demo1">
        select * from tb_brand;
    </select>
</mapper>
```

```
// User Class 用来装Database的参数 (Example)
public class demo1 {
    private Integer id          ;

    private String brand_name  ;

    private String company_name;

    private String ordered     ;

    private String description ;

    private String status      ;

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getBrand_name() {
        return brand_name;
    }

    public void setBrand_name(String brand_name) {
        this.brand_name = brand_name;
    }

    public String getCompany_name() {
        return company_name;
    }

    public void setCompany_name(String company_name) {
        this.company_name = company_name;
    }

    public String getOrdered() {
        return ordered;
    }

    public void setOrdered(String ordered) {
        this.ordered = ordered;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public String getStatus() {
        return status;
    }

    public void setStatus(String status) {
        this.status = status;
    }

    @Override
    public String toString() {
        return "demo1{" +
                "id=" + id +
                ", brand_name='" + brand_name + '\'' +
                ", company_name='" + company_name + '\'' +
                ", ordered='" + ordered + '\'' +
                ", description='" + description + '\'' +
                ", status='" + status + '\'' +
                '}';
    }
}

```

```
// main (Example)
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import java.io.IOException;
import java.io.InputStream;
import java.util.List;

public class myb_demo {
    public static void main(String[] args) throws IOException {

        //1. 加载mybatis的核心配置文件，获取SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory =
                new SqlSessionFactoryBuilder().build(inputStream);

        //2. 获取SqlSession对象，用它来执行sql
        SqlSession sqlSession  = sqlSessionFactory.openSession();

        //3.执行sql
        List<demo1> users = sqlSession.selectList("test.selectAll");

        System.out.println(users);

        //4. 释放资源
        sqlSession.close();
    }
}
```

# 数据库连接池

<figure><img src="../.gitbook/assets/image (4) (1) (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (2) (1) (3).png" alt=""><figcaption></figcaption></figure>

### Driud使用步骤

1. 导入jar包 druid-1.1.12.jar
2. 定义配置文件
3. 加载配置文件
4. 获取数据库连接池对象
5. 获取连接

```
// Example Code
        //1. 导入jar包

        //2. 定义配置文件

        //3. 加载配置文件
        Properties prop = new Properties();
        prop.load(new FileInputStream("src/DRUID.properties"));

        //4. 获取连接池对象
        DataSource dataSource = DruidDataSourceFactory.createDataSource(prop);

        //5. 获取数据库连接
        Connection connection = dataSource.getConnection();

        System.out.println(connection);
```

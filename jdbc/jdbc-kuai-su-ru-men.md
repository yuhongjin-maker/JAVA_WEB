# JDBC快速入门

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

```
// Example Code
        Class.forName("com.mysql.cj.jdbc.Driver");
        //新版可以不写这一行了

        String url = "jdbc:mysql://127.0.0.1:3306/db1";
        String username = "root";
        String password = "1234";
        Connection conn = DriverManager.getConnection(url,username,password);

        String sql = "update student set id = 3 ";

        Statement stmt = conn.createStatement();

        int count = stmt.executeUpdate(sql);

        System.out.println(count);

        stmt.close();
        conn.close();
```

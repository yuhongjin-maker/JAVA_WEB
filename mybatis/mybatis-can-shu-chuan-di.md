# MyBatis参数传递

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### POJO类型

#### 直接使用，属性名和参数占位符一致

### Map集合

#### 直接使用，键名和参数占位符一致

### Collection

#### 封装成Map集合

```
// Example code
map.put("arg0",Collection集合)
map.put("collection",Collection集合)
```

### List

#### 封装成Map集合

```
// Example code
map.put("arg0",List集合)
map.put("collection",List集合)
```

### Array

#### 封装成Map集合

```
// Example code
map.put("arg0",数组)
map.put("collection",数组)
```

### 其他类型

#### 直接使用

### 多个参数

#### 封装成Map集合，可以使用@Param注解，替换Map集合中默认的arg键名

```
// Example code
map.put("arg0",参数值1)
map.put("param1",参数值1)
map.put("arg2",参数值3)
```

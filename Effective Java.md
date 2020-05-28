# Effective Java

## 1. 使用静态工厂方法替代构造器

### 1.1 调用者可以根据静态工厂方法名来决定调用哪个方法

```java
// constructor
public class Person{
  public Person(String name){
    // do init
  }
  public Person(String idNo){
    // do init
  }
}

// static factory methods
public class Person{
  public static getPersonByName(String name){
    // do create instance
  }
  public static getPersonByIdNo(String idNo){
    // do create instance
  }
}
```

### 1.2 静态工厂方法不用每次执行都创建一个对象

```java
public static final Boolean TRUE = new Boolean(true);
public static final Boolean False = new Boolean(false);
public static Boolean valueOf(boolean b) {
  return (b ? TRUE : FALSE);
}
// 单例模式
```



### 1.3 静态工厂方法可以返回任意子类型的对象

```java
// java.util.Collections，这里面有许多类，返回值都是collection，但是却是由collection的子类实现的，充分体现了多态的特点
// 多态应用：返回类型是接口，而不是具体的类
```

### 1.4 静态工厂方法的返回对象可以随着输入参数的函数的不同发生变化

```java
// EnumSet 如果元素个数 <= 64, 返回 RegularEnumSet,并且使用一个long类型数字存储.否则返回JumboEnumSet,并且使用 long数组进行存储
```

### 1.5 静态工厂方法返回对象的类不需要存在

```java
// service provider framework 包含了3个必要组件：（1）服务接口（2）提供者注册API （3）服务访问API （4）服务提供者接口

// JDBC
// Connection -- 服务接口
// DriverManager.registerDriver -- 提供者注册API
// DriverManager.getConnection -- 服务访问API
// Driver -- 服务提供者接口
/*
1. 注册驱动
Class.forName("com.mysql.jdbc.Driver")
2. 获取链接
Connection conn = DriverManager.getConnection('jdbc:mysql://localhost:3306/my_db')
如果有人创造了一个数据库，想让Java访问，那么他需要实现Driver接口来完成一个Java驱动（服务提供者接口）
*/
```
































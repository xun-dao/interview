# Effective Java

## 1. 使用静态工厂方法替代构造器

### 1.1 调用者可以根据静态工厂方法名来决定调用哪个方法

```java
// constructor
public class Person{
  public Person(String name, String nickName){
    // do init
  }
  public Person(String name, String phoneNo){
    // do init
  }
}

// static factory methods
public class Person{
  public static getPersonByNameAndNickName(String name, String nickName){
    // do create instance
  }
  public static getPersonByNameAndPhoneNo(String name, String phoneNo){
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
```



### 1.3






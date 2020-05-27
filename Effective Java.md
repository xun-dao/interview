# Effective Java









































## 1. Consider static factory methods instead of constructors

```java
// 一、多个构造函数，很难区分调用哪一个
public class Person{
  private String name;
  private String nickName
  private String gender;
  public Person(){
    
  }
  public Person(String name, String nickName){
    this.name = name;
    this.nickName = name;
  }
  public Person(String name, String gender){
    this.name = name;
    this.gender = gender;
  }
}
```





## 2. hello




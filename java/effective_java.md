# EFFECTIVE JAVA

## 1. 使用静态工厂方法替代构造器

```java
/** 优点1: 静态工厂方法名字可以帮助调用者理解该方法作用*/
BigInteger(int, int, Random);
BigInteger.probablePrime();

/** 优点2: 静态工厂方法可以在类加载的时候，初始化实例，减少了重复初始化的时间，降低了多个实例的存储空间*/
// 饿汉式单利
public static Connection conn = initConn();

/** 优点3: 静态工厂方法可以返回子类型*/
// 基于接口的框架——接口类型作为静态工厂方法的返回值


/** 优点4:  返回对象的类可以根据输入参数的变化而变化 
 EnumSet返回值根据长度的变化而改变，如果长度 <= 64,返回RegularEnumSet.否则返回JumboEnumSet
*/
 public static <E extends Enum<E>> EnumSet<E> noneOf(Class<E> elementType) {
        Enum<?>[] universe = getUniverse(elementType);
        if (universe == null)
            throw new ClassCastException(elementType + " not an enum");

        if (universe.length <= 64)
            return new RegularEnumSet<>(elementType, universe);
        else
            return new JumboEnumSet<>(elementType, universe);
    }


/** 优点5: 当某个方法使用这个类的对象作为返回值的时候，这个类可以尚未创建 
例如：服务提供者框架
 JDBC 中的 Driver，DriverManager.getConnection
*/

/** 缺点1: 没有 public 或 protect 类型的构造器，类无法被初始化*/
/** 缺点2: 程序员很难找到这些静态构造方法（他们不像构造器那样，众所周知）
    我们可以使用以下通用的命名方式来克服这个问题：
    <1> from (Date.from(instant))
    <2> of (EnumSet.of(JACK, QUEEN, KING))
    <3> valueOf (Integer.valueOf())
    <4> instance or getInstance (Person.class.getInstance())
    <5> create or newInstance (Array.newInstance())
    <6> getType (Files.getFileStore())
    <7> newType (Files.newBufferedReader(path))
    <8> type (Collections.list())
*/

```

## 2. 在构造器有多个构造参数的时候，考虑使用Builder

```java
/** 
static factory method 和 constructor 都不能很好地解决构建实例需要多个参数的问题，使用Builder可以合理解决
抽象类用抽象Builder
具体类用具体Builder
在构造参数超过四个的时候考虑使用Builder
*/

public class Person{
  private String name;
  private String phoneNo;
  private String nickName;
  public static class Builder{
    private String name;
    private String phoneNo;
    private String nickName;
    public Builder(String name){
      this.name = name;
    }
    public Person(Builder builder){
      this.name = builder.name;
      this.phoneNo = builder.phoneNo;
      this.nickName = builder.nickName;
    }
    public Builder phoneNo(String phoneNo){
      this.phoneNo = phoneNo;
      return this;
    }
    public Builder nickName(String nickName){
      this.nickName = nickName;
      return this;
    }
    public Person build(){
      return new Person(this);
    }
  }
}

@Test
public void test(){
  Person.Builder('Jack').phoneNo('134554').nickName('QQ').build();
}
```

## 3. 使用私有构造器或枚举强化单例属性

```java
// 静态属性

// 静态工厂方法


// 枚举

public class Person{
  private Person(){
  }
  // static field
  public static final Person person = new Person();
  
  // static factory method
  public static Person getInstance(){
    return new person();
  }
}

// enum
public enum Person{
  instance;
  public void say(){
    System.out.println("hello");
  }
}
```



## 4.

## 5.
























##	基础数据类型
java有八大数据基础数据类型

| 关键字  | 描述       | 大小 |
| ------- | ---------- | ---- |
| int     | 整型       | 4    |
| long    | 长整型     | 8    |
| short   | 短整型     | 2    |
| float   | 单精浮点型 | 4    |
| double  | 双精浮点型 | 8    |
| boolean | 布尔型     | 1    |
| char    | 字符型     | 2    |
| byte    | 字节型     | 1    |

##	修饰符

### 访问控制修饰符

| 修饰符      | 当前类 | 同一包内 | 子孙类(同一包) | 子孙类(不同包) | 其他包 |
| :---------- | :----- | :------- | :------------- | :------------- | :----- |
| `public`    | √      | √        | √              | √              | √      |
| `protected` | √      | √        | √              | √              |        |
| `default`   | √      | √        | √              |                |        |
| `private`   | √      |          |                |                |        |

###	static 修饰符

#### 静态变量：

static 关键字用来声明独立于对象的静态变量，无论一个类实例化多少对象，它的静态变量只有一份拷贝。 静态变量也被称为类变量。局部变量不能被声明为 static 变量。

####	静态方法：

static 关键字用来声明独立于对象的静态方法。静态方法不能使用类的非静态变量。静态方法从参数列表得到数据，然后计算这些数据。

###	final 修饰符

用来修饰类、方法和变量，final 修饰的类不能够被继承，修饰的方法不能被继承类重新定义，修饰的变量为常量，是不可修改的。

#####	final 变量

final 表示"最后的、最终的"含义，变量一旦赋值后，不能被重新赋值。被 final 修饰的实例变量必须显式指定初始值。

final 修饰符通常和 static 修饰符一起使用来创建类常量。

##### final 方法

父类中的 final 方法可以被子类继承，但是不能被子类重写。

声明 final 方法的主要目的是防止该方法的内容被修改。

如下所示，使用 final 修饰符声明方法。

```	java
public class Test{
    public final void changeName(){
       // 方法体
    }
}
```

##### final 类 

final 类不能被继承，没有类能够继承 final 类的任何特性。

``` java
public final class Test {
   // 类体
}
```

> ​	String类型就是被final修饰，不能被继承的类型



###	abstract 修饰符

用来创建抽象类和抽象方法。

####	抽象类

​	抽象类不能用来实例化对象，声明抽象类的唯一目的是为了将来对该类进行扩充。

一个类不能同时被 abstract 和 final 修饰。如果一个类包含抽象方法，那么该类一定要声明为抽象类，否则将出现编译错误。

抽象类可以包含抽象方法和非抽象方法。

####	抽象方法

抽象方法是一种没有任何实现的方法，该方法的的具体实现由子类提供。

抽象方法不能被声明成 final 和 static。

任何继承抽象类的子类必须实现父类的所有抽象方法，除非该子类也是抽象类。

如果一个类包含若干个抽象方法，那么该类必须声明为抽象类。抽象类可以不包含抽象方法。

抽象方法的声明以分号结尾，例如：

``` java
public abstract sample();
```



## 接口和抽象类

* 普通类：只有具体实现

* 抽象类：具体实现和规范（抽象方法）都有！

* 接口就是规范，定义一组规则

  ---

  ### 使用

  + 抽象类通过 extends 继承
  + 类通过 implements 实现接口
  + 实现接口的类需要重写方法

### 使用接口

并创建一个常量

> 常量使用 final关键字

~~~ java
public interface UserService{
    public static final age=12
        
}

~~~

### 声明一个抽象类

~~~ java
public abstact class Action {
    public abstract do()；
}
~~~

## 内部类

获取外部类的私有彻成员

```java
public class Outer {
    private int id=10;
    public void out(){
        System.out.println("内部类方法");
        new Inner();
    }
    public  class Inner{
        public void in(){
            System.out.println("内部类方法");
        }
        //获得外部类的私有成员
        public void getID(){
            System.out.println("id:"+id);
        }
    }
}
```
## [常用数据结构](java数据结构.md)

##	常见问题

### final、finally、finalize有什么区别

- final是一个关键字，表示最终的，不变的
- finally也是一个关键字 通常和**try**联合使用，在finally{}中的代码是一定执行的
- finalize是object类的一个方法，这个方法由垃圾回收调用

## 


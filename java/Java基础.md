

* [关键字](#关键字)
* [基础数据类型](#基础数据类型)
* [修饰符](#修饰符)
  * [访问控制修饰符](#访问控制修饰符)
  * [static 修饰符](#static-修饰符)
    * [静态变量：](#静态变量)
    * [静态方法：](#静态方法)
  * [final 修饰符](#final-修饰符)
      * [final 变量](#final-变量)
      * [final 方法](#final-方法)
      * [final 类](#final-类)
  * [abstract 修饰符](#abstract-修饰符)
    * [抽象类](#抽象类)
    * [抽象方法](#抽象方法)
* [接口和抽象类](#接口和抽象类)
  * [使用](#使用)
  * [使用接口](#使用接口)
  * [声明一个抽象类](#声明一个抽象类)
* [内部类](#内部类)
* [包装类](#包装类)
* [异常](#异常)
  * [异常的概述和分类](#异常的概述和分类)
  * [Throwable类常用方法](#throwable类常用方法)
  * [什么是Exception](#什么是exception)
  * [Exception处理关键字](#exception处理关键字)
* [<a href="java%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84\.md">常用数据结构</a>](#常用数据结构)
* [常见问题](#常见问题)
    * [final、finally、finalize有什么区别](#finalfinallyfinalize有什么区别)
    * [String类、StringBuffer类与StringBuilder类](#string类stringbuffer类与stringbuilder类)

## 关键字

~~~
用于定义数据类型的关键字
class interface    byte short int long float double char boolean void               
用于定义数据类型值的关键字
true false null       
用于定义流程控制的关键字
if    else switch    case default while do for break    continue return           
用于定义访问权限修饰符的关键字
private    protected public       
用于定义类，函数，变量修饰符的关键字
abstract final static synchronized   
用于定义类与类之间关系的关键字
extends    implements           
用于定义建立实例及引用实例，判断实例的关键字
new    this super instanceof   
用于异常处理的关键字
try    catch finally throw    throws
用于包的关键字
package    import           
其他修饰符关键字
native strictfp transient volatile assert
~~~



##	基础数据类型

java有八大数据基础数据类型

| 基本类型 | 说明                   | 字节数  |
| -------- | ---------------------- | ------- |
| byte     | 字节长度的整数，八位   | 1个字节 |
| short    | 短整数，十六位         | 2个字节 |
| int      | 整数，三十二位         | 4个字节 |
| long     | 长整数，六十四位       | 8个字节 |
| float    | 单精度浮点数，三十二位 | 4个字节 |
| double   | 双精度浮点数，六十四位 | 8个字节 |
| char     | Unicode字符            | 2个字节 |
| boolean  | 布尔值                 | 1个字节 |

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
##  包装类

**1. 为什么会有基本类型包装类**

* 为了对基本数据类型进行更多的操作,更方便的操作,java就针对每一种基本数据类型提供了对应的类类型.

 **2. 基本类型和包装类的对应**

~~~
byte           Byte
short          Short
int            Integer
long           Long
float          Float
double         Double
char           Character
boolean        Boolean
~~~

##	异常

### 概述

在`Java`语言中，将程序执行中发生的不正常情况称为“异常”(开发过程中的语法错误和逻辑错误不是异常)。



### 分类

* Exception 

*  Error

  

### 继承体系

* 严重问题:    Error    不予处理,因为这种问题一般是很严重的问题，比如: 内存溢出
* 非严重问题:    Exception 
  * 编译时异常:  非RuntimeException
  * 运行时异常:  RuntimeException

### Throwable类常用方法

- Throwable类中的常用方法
- 注意：catch关键字后面括号中的Exception类型的参数e。Exception就是try代码块传递给catch代码块的变量类型，e就是变量名。catch代码块中语句"e.getMessage();"用于输出错误性质。通常异常处理常用3个函数来获取异常的有关信息:
  - getCause()：返回抛出异常的原因。如果 cause 不存在或未知，则返回 null。
  - getMeage()：返回异常的消息信息。
  - printStackTrace()：对象的堆栈跟踪输出至错误输出流，作为字段 System.err 的值。
- 有时为了简单会忽略掉catch语句后的代码，这样try-catch语句就成了一种摆设，一旦程序在运行过程中出现了异常，就会忽略处理异常，而错误发生的原因很难查找。

###	什么是Exception

+ 异常是正常程序流程所不能处理或者没有处理的异常情况或异常事件，比如算术运算被0除，数组下标越界，使用的对象为null等

- Java异常是Java提供的一种识别及响应错误的一致性机制。Java异常机制可以使程序中异常处理代码和正常业务代码分离，保证程序代码更加优雅，并提高程序健壮性。
- 在有效使用异常的情况下，异常能清晰的回答what,where,why这3个问题：异常类型回答了“什么”被抛出，异常堆栈跟踪回答了“在哪“抛出，异常信息回答了“为什么“会抛出。

### Exception处理关键字

- Java异常机制用到的几个关键字：**try、catch、finally、throw、throws。**
  - • **try**        -- 用于监听。将要被监听的代码(可能抛出异常的代码)放在try语句块之内，当try语句块内发生异常时，异常就被抛出。
  - • **catch**   -- 用于捕获异常。catch用来捕获try语句块中发生的异常。
  - • **finally**  -- finally语句块总是会被执行。它主要用于回收在try块里打开的物理资源(如数据库连接、网络连接和磁盘文件)。只有finally块，执行完成之后，才会回来执行try或者catch块中的return或者throw语句，如果finally中使用了return或者throw等终止方法的语句，则就不会跳回执行，直接停止。
  - • **throw**   -- 用于抛出异常。
  - • **throws** -- 用在方法签名中，用于声明该方法可能抛出的异常。

### 注解

注解（注释，标注，Annotation）的作用 据它所起的作用，大致可分为三类： 

+ 编写文档：通过代码里标识的元数据生成文档。 
+ 代码分析：通过代码里标识的元数据对代码进行分析。 
+ 编译检查：通过代码里标识的元数据让编译器能实现基本的编译检查



##### 基本内置注释

###### @Override

编译时检查，你可以为你的方法添加该注释，以声明该方法是用于覆盖父类中的方法。如果 该方法不是覆盖父类的方法，将会在编译时报错。例如

```java
class Demo1 extends Demopar{
    public static void main(String[] args) {
        Demo1 demo1=new Demo1();
        demo1.to();
    }
    @Override
    private  void to() {}
}
class Demopar{
    public void nto(){}
}
```



~~~cmd
>javac de.java
de.java:8: 错误: 方法不会覆盖或实现超类型的方法
@Override
^
1 个错误
~~~

###### @Deprecated

对不应该在使用的方法添加注释，当编程人员使用这些方法时，将会在编译时显示提示信息，比如用于标识方法已过时

##### 元注解

用于标识“注解类型‘的”注解“

常见元注解

###### 	@Target

用于标注“被标注的注解”可以出现在哪些位置\

###### @Retention

用于标注“被标注的注解”最终保存在哪

~~~java
@Retention(RetentionPolicy.SOURCE) //表示该注解只保留在Java源代码中
@Retention(RetentionPolicy.CLASS) //表示该注解编译后保留在CLASS文件里
@Retention(RetentionPolicy.RUNTIME) //表示该注解编译后保留在CLASS文件里，并且可以被反射类
~~~

例如：

~~~java
package java.lang;
import java.lang.annotation.*;
@Target(ElementType.METHOD) //表示该注解只能标识在方法上
@Retention(RetentionPolicy.SOURCE)
public @interface Override {
}
~~~

#### 定义注解

~~~java
import java.lang.annotation.ElementType;
import java.lang.annotation.Target;

@Target(ElementType.METHOD)
public @interface name {
    String value();
    int size() default 0;
    /*
        当一个注解中有属性时，那么属性必须赋值
        除非指定该注解的默认值
     */
}

~~~

#### 使用注解

~~~java
class Demo1  {
    @name(value = "aa")
    private  void to() {
    }
    @name("aa")//如果一个注解的属性名字是value 该属性可以省略
    private  void go() {

    }
}

~~~



## [常用数据结构](java数据结构.md)

##	常见问题

#### final、finally、finalize有什么区别

+ final是一个关键字，表示最终的，不变的

- finally也是一个关键字 通常和**try**联合使用，在finally{}中的代码是一定执行的
- finalize是object类的一个方法，这个方法由垃圾回收调用

#### String类、StringBuffer类与StringBuilder类

StringBuffer和StringBuilder都实现了AbstractStringBuilder抽象类，拥有几乎一致对外提供的调用接口；其底层在内存中的存储方式与String相同，都是以一个有序的字符序列（char类型的数组）进行存储，不同点是StringBuffer/StringBuilder对象的值是可以改变的，并且值改变以后，对象引用不会发生改变;两者对象在构造过程中，首先按照默认大小申请一个字符数组，由于会不断加入新数据，当超过默认大小后，会创建一个更大的数组，并将原先的数组内容复制过来，再丢弃旧的数组。因此，对于较大对象的扩容会涉及大量的内存复制操作，如果能够预先评估大小，可提升性能。

 +	StringBuffer和String的区别
   - String是不可变的字符序列
   - StringBuffer 是可以的字符序列

- StringBuffer类概述
  - 字符串缓冲区，StringBuffer是一个容器

  - 我们如果对字符串进行拼接操作，每次拼接，都会构建一个新的String对象，既耗时，又浪费空间。 而StringBuffer就可以解决这个问题

  - 线程安全的可变的字符序列 , 安全对应的效率比较低

- StringBuilder类
  - StringBuilder是线程不安全的，其他跟StringBuffer一样；StringBuffer和StringBuilder底层是 char[]数组实现的 


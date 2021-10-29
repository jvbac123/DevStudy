## 线程的创建和启动

### 继承 Thread 类

~~~java
public class MyThread extends Thread {
    public void run() {
        // ...
    }
    public static void main(String[] args) {
        MyThread mt = new MyThread();
        mt.start();
	}
}

~~~

### 实现 Runnable 接口

~~~java
public class MyRunnable implements Runnable {
    @Override
    public void run() {
        
    }
    public static void main(String[] args) {
        MyRunnable instance = new MyRunnable();
        Thread thread = new Thread(instance);
        thread.start();
	}
}
~~~

### 实现接口 VS 继承 Thread

实现接口会更好一些，因为：

- Java 不支持多重继承，因此继承了 Thread 类就无法继承其它类，但是可以实现多个接口；
- 类可能只要求可执行就行，继承整个 Thread 类开销过大。

## 线程的生命周期

线程的生命周期存在五个状态：新建、就绪、运行、阻塞、死亡

+ 新建：采用 new语句创建完成 
+ 就绪：执行 start 后 
+ 运行：占用 CPU 时间 
+ 阻塞：执行了 wait 语句、执行了 sleep 语句和等待某个对象锁，等待输入的场合
+  终止：退出 run()方法

##  线程的同步（加锁）

### synchronized 作用域

synchronized 关键字主要有以下几种用法： 

- 非静态方法的同步； 
- 静态方法的同步； 
- 代码块。

#### 对象锁

非静态方法使用 synchronized 修饰的写法，修饰实例方法时，锁定的是当前对象：

```java
    public synchronized void test(){
        // TODO
    }
```

代码块使用 synchronized 修饰的写法，使用代码块，如果传入的参数是 this，那么锁定的也是当前的对象

~~~java
    public void test(){
        synchronized (this) {
            // TODO
        }
    }
~~~

#### 类锁

由于静态方法是类所有对象共用的，所以进行同步后，该静态方法的锁也是所有对象唯一的。每次只能有一个线程来访问对象的该非静态同步方法。 



类锁需要 synchronized 来修饰静态 static 方法，写法如下：

```java
    public static synchronized void test(){
        // TODO
    }
```

或者使用代码块，需引用当前的类：

```java
    public static void test(){

        synchronized (TestSynchronized.class) {
            // TODO
        }

    }
```


## 常用数据结构

### Collection集合 

#### 常用方法

| 方法    | 描述                         |
| ------- | ---------------------------- |
| add     | 添加                         |
| clear   | 清空集合                     |
| contain | 判断集合中是否包含指定的元素 |
| size    | 返回集合中的元素数。         |
|         |                              |

#### 注意事项

集合的remove 和contain方法调用的是内容的equals方法，而equals方法

在没有被重写的情况下是通过 ==来进行比较

``` java
public class CollectionDemo1 {
    public static void main(String[] args) {
        Collection<String> list=new ArrayList();
        String str1=new String("jack");
        String str2=new String("jack");
        list.add(str1);
        System.out.println(list.size());
        list.remove(str2 );
        System.out.println(list.size());
    }
}
```

输出如下

> 1
> 0

其他对象也一样

``` java
package com.study.Collection;
import java.util.ArrayList;
import java.util.Collection;

public class CollectionDemo1 {
    public static void main(String[] args) {
        Collection list=new ArrayList();
        User u1=new User("jack");
        User u2=new User("jack");
        list.add(u1);
        list.add(u2);
        System.out.println(list.size());
        list.remove(u2);
        System.out.println(list.size());
    }
}
class User{
    private String name;
    public User() {
    }
    public User(String name) {
        this.name = name;
    }
    public boolean equals(Object o) {
       if (o == null || !(o instanceof User)) return false;
       if (o == this) return  true;
        User u= (User) o;
        return  u.name.equals(this.name);
    }
}
```

输出如下

> 2
> 1

#### List

##### ArrayList

- 底层采用数组数据结构

- ArrayList集合是非线程安全的

#####	LinkedList

底层使用采用双向链表数据结构

##### Vector

- 底层采用数组数据结构

- Vector集合是线程安全的，synchonized关键字修饰所以线程安全，现在保证线程安全有别的方法。所以使用比较少



#### Set

##### HashSet

实际上在使用时底层 new了一个HashMap集合，向HashSet中存储元素，HashMap是一个哈希表数据结构

##### SortSet

###### TreeSet

实际上在使用时底层 new了一个TreeMap集合，向TreeMap中存储元素，TreeMap是采用二叉树数据结构

### Map集合

- Map集合和Collection没有关系
- Map集合以key和value键值对方式存储元素
- key和value都是存储java对象的内存地址，所以不支持基础数据类型
- 所有的Map集合均。无序且不可重复

#### HashMap

- 非线程安全
- 底层是哈希表数据结构

#### HashTable

- 线程安全
- 底层是哈希表数据结构
- 由于使用synchonized修饰，效率低，一般用的少





## 异常 Exception

在方法覆盖重写的时候，重写的方法不能比重写前的方法抛出更多的异常
错误用法:

```java
class Amimal{
  public void eat() throws IOException {
    //do
  }
}
class  dog extends Amimal{
  @Override
  public void eat() throws Exception {

  }
}

```


##	排序

### 冒泡排序

冒泡排序就是进行两层循环

```java
public class SoftDemo {
  public static void main(String[] args) {
    int[] arr={88,77,66,33,55,99,11};
    SoftDemo.soft(arr);
  }
  public static void soft(int[] arr){
    System.out.println(Arrays.toString(arr));
    for(int i=0;i<arr.length-1;i++){
      for (int j=0;j<arr.length-1-i;j++){
        if (arr[j]>arr[j+1]) {
          int t=arr[j];
          arr[j]=arr[j+1];
          arr[j+1]=t;
        }
      }
    }
    System.out.println(Arrays.toString(arr));
  }
}
```

###  选择排序法

相对于冒泡排序法 ，变量交换次数变少了

```java
class SoftDemo {    
public static void SecSoft(int[] arr){
        for (int i = 0; i < arr.length-1; i++) {
            int min = i;
            for(int j=i+1;j<arr.length;j++){
                if (arr[j]<arr[min]) {
                    min=j;
                }
            }
            if(min != i){
                int t=arr[min];
                arr[min]=arr[i];
                arr[i]=t;
            }
        }
    }
}
```


#### IO流

输入输出流



##### IO流的分类

###### 类型

+ 字节流 Stream
  - java.io.InputStream  字节输入流
  - java.io.OutputStream 字节输出流
+ 字符流 Reader/Writer 
  + java.io.Reader 字符输入流
  + java.io.Writer 字符输出流

###### 常用流

+ 文件流
  + java.io.FilterInputStream
  + java.io.FilterOutputStream
+ 缓存流
  + java.io.BufferedInputStream
  + java.io.BufferedOutputStream
  + java.io.BufferedReader
  + java.io.BufferedWriter
+ 数据流
  + java.io.DataInputStream
  + java.io.DataOutputStream
+ 标准输入输出流 STDIO
  + java.io.PrintStream
  + java.io.PrintWriter
+ 对象流
  + java.io.ObjectInputStream
  + java.io.ObjectOutputStream

###### 文件字节流

文件输入流

| 方法      | 说明                                       |
| --------- | ------------------------------------------ |
| read      | 从流中读取字节                             |
| skip      | 跳过并从输入流中丢弃`n`字节的数据          |
| available | 返回输入流中读取或跳过的剩余字节数的估计值 |
| close     | 关闭此文件输入流并释放与关联的所有资源。   |



文件输入流使用例子

~~~java
        FileInputStream fis=null;
        try {
            fis=new FileInputStream("README.md");
            int readData=0;
            while ((readData = fis.read())!=-1) {
                System.out.println(readData);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (fis != null) {
                try {
                    fis.close();
                }catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
~~~

读取所有

~~~java
byte[] bytes = new byte[fis.available()];
int l = fis.read(bytes);
~~~

写出文件

~~~java
fos = new FileOutputStream("test.txt");
String str="写出文件";
byte[] bytes = str.getBytes(StandardCharsets.UTF_8);
fos.write(bytes);
~~~



待补充



#### File 类

##### 方法摘要

| 方法                  | 描述                                                         |
| :-------------------- | :----------------------------------------------------------- |
| `canExecute()`        | 测试应用程序是否可以执行此抽象路径名表示的文件。             |
| `canRead()`           | 测试应用程序是否可以读取此抽象路径名表示的文件。             |
| `canWrite()`          | 测试应用程序是否可以修改此抽象路径名表示的文件。             |
| `createNewFile()`     | 当且仅当具有此名称的文件尚不存在时，创建的新空文件。         |
| `delete()`            | 删除此路径名表示的文件或目录。                               |
| `deleteOnExit()`      | 请求在JVM终止时删除此路径名表示的文件或目录                  |
| `exists()`            | 测试此路径名表示的文件或目录是否存在。                       |
| `getAbsoluteFile()`   | 返回此路径名的绝对形式。                                     |
| `getName()`           | 返回此抽象路径名表示的文件或目录的名称。                     |
| `getParent()`         | 返回此抽象路径名父项的路径名字符串，如果此路径名未指定父目录，则返回 `null` 。 |
| `getPath()`           | 将此抽象路径名转换为路径名字符串。                           |
| `isAbsolute()`        | 测试此抽象路径名是否为绝对路径。                             |
| `isDirectory()`       | 测试此抽象路径名表示的文件是否为目录。                       |
| `isFile()`            | 测试此抽象路径名表示的文件是否为普通文件。                   |
| `length()`            | 返回路径名表示的文件的长度。                                 |
| `list()`              | 路径名表示的目录中的文件和目录。                             |
| `listFiles()`         | 返回一个抽象路径名数组，表示此抽象路径名表示的目录中的文件。 |
| `mkdir()`             | 创建的目录。                                                 |
| `mkdirs()`            | 创建目录，包括任何必需但不存在的父目录。                     |
| `renameTo(File dest)` | 重命名此抽象路径名表示的文件。                               |


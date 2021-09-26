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






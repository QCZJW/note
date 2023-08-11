# Java File类

## 一些小点　	

+ 在java中，如 E:\\java\\test.txt  实际环境中并不存在该路径时，![image-20230331163116317](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230331163116317.png)

依然可以赋给一个对象，并且调用该对象的方法（File类本身的方法）![image-20230331163229014](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230331163229014.png)

但其结果，都为否认

![image-20230331163347655](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230331163347655.png)



+ 创建文件的时候注意一件事：*** 文件和文件夹也不能同名***

## 文件对像的创建

![image-20230518200536557](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518200536557.png)

+ 其中，相对路径是相对与项目而言

  ![image-20230518200652073](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518200652073.png)

![image-20230518200706207](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518200706207.png)

``` java
    public static void main(String[] args) {
        //创建文件对象
        File a=new File("E:\\java_test_IO\\sc.txt");
        //创建很简单，百度就是了
        String temp="E:\\java_test_IO\\sc.txt";
        File b=new File(temp);
        a.delete();

    }
```

![image-20230518201557726](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518201557726.png)

![image-20230518201622923](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518201622923.png)

## 基本的方法

### 查询类方法

![image-20230518201707210](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518201707210.png)

+ 判断的方法都没什么好注意的

![image-20230518202011503](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518202011503.png)

![image-20230518202243368](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518202243368.png)

### 创建及删除

![image-20230518202322477](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518202322477.png)

#### createNewFile()方法

![image-20230518203248366](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518203248366.png)

+ 问文件可以没有后缀名

#### mkdir()方法

![image-20230518203514466](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518203514466.png)

#### mkdirs()方法

+ mkdirs方法和mkdir方法一样，创建文件或文件夹的时候，需要在创建文件对象时直接写出这个文件名。

![image-20230518203729223](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518203729223.png)

#### delete方法

![image-20230518203914020](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518203914020.png)

## 文件遍历

![image-20230518204000721](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518204000721.png)

![image-20230518205116799](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518205116799.png)

![image-20230518205143880](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518205143880.png)

![image-20230518205327476](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518205327476.png)

### 简易的文件过滤器

![image-20230518205550990](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518205550990.png)

![image-20230518205740663](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518205740663.png)

+ 实现的方式很多。核心就是再遍历时候判断就好了。

``` java
 File a=new File("E:\\java_test_IO");
        for (File tt:a.listFiles()) {
            if (tt.isFile()&& tt.getName().endsWith(".txt")) {
                System.out.println(tt);
            }
        }//稍微百度以下就知道了
```


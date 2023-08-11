# java知识

![image-20230416204323911](../../picture/image-20230416204323911.png)

![image-20230416204350353](../../picture/image-20230416204350353.png)

## foreach的使用



``` java
//遍历文件数组     
File a=new File("E:\\java_test_IO");
        File []temp=a.listFiles();
        for (File ttt:temp) {//需要做: 号左边创建需要遍历的集合或数组的相同对象。
            System.out.println(ttt);
        }
```

``` java
   		//遍历int数组
		int temp1[]=new int[12];

        for (int i = 0; i < 12; i++) {
            temp1[i]=i;
        }

        for (int tt:temp1) {
            System.out.println(tt);
        }
```

## 基本数据类型和引用类型

+ 基本类型的变量存储在堆中。

+ 引用类型的变量分开存放，在栈里存放引用类型变量的地址，这个地址指向堆中的一块区域，这块区域存放着具体数据。

+ 数组是一种引用类型，数组在堆中的空间是连续的。
+ 在java中，String一个类，是一种特殊的对象。

## 封装、继承、多态

+ 封装，指的是利用修饰符private将属性变成私有，使得其他的类不能直接访问。然后再创建可以被其他类直接访问的方法，其他类通过调用这些方法来间接地查看、改变被封装的值。封装的好处在于可以通过封装来保证避免不正确的值输入。

+ 封装用set()、get***()、this来实现，其中set***()为改变被封装值的方法,get表示对数据的读取。而 this用于实现区分本地属性与传入属性。
+ 继承，是将一个类视作父类，一个类视为子类。

​	（1）类只能继承一个类，final修饰的类不能被继承。

​	（2）当调用对象没有要调用的属性时，会找该类的父类是否有要调用的属性。

​	（2.1）在查找时，有一个类有需要调用的属性，并且不能被访问到，那么不会继续向上查找。

​	（3）所有类默认继承了object类。

## 方法 

方法是为了完成某些事而产生的，方法是语句的集合，方法分为静态方法和非静态方法。方法如同一个最基础的器官，或是一根手指，能完成属于它的任务。

方法的命名遵循驼峰命名法。

方法格式([ ]为可选)：[访问权限修饰符号] [static] 返回值类型 方法名(){

​                方法体

​                [return 数据]}

## 类

+ 类是方法分集合，一个类里可以有多个方法。可以用类名.方法名可以调用其他类的静态方法，创建对象后（创建对象又叫实例化），可以调用其他类的任意可访问到的方法。可凭借创捷对象来解决静态方法无法调用非静态方法的问题。

+ 内部类可访问外部类的任何属性。内部类与外部类的属性、方法是平级关系。

+ 如果把类定义在方法里面，那么叫局部内部类

## 一些常用类的介绍

### String类

+ ![image-20230422102218212](../../picture/image-20230422102218212.png)
+ ![image-20230422103314725](../../picture/image-20230422103314725.png)
+ ![image-20230422103453916](../../picture/image-20230422103453916.png)
+ ![image-20230422103558078](../../picture/image-20230422103558078.png)
+ ![image-20230422103717091](../../picture/image-20230422103717091.png)
+ ![image-20230422103746700](../../picture/image-20230422103746700.png)
+ ![image-20230422103813707](../../picture/image-20230422103813707.png)
+ ![image-20230422104040869](../../picture/image-20230422104040869.png)

### StringBuilder类

+ 当一个字符串要频繁地拼接时，用String太慢了，因为String将两个字符串拼成一个新的字符串和，再和下一个拼接，一直重复这个过程。所以要用StringBuilder（可变长字符序列）。

### StringJoiner

+ 能够指定拼接格式

+ ![image-20230422102022218](../../picture/image-20230422102022218.png)

  

### BigInteger

![image-20230513212602230](../../picture/image-20230513212602230.png)

![image-20230513212654360](../../picture/image-20230513212654360.png)

![image-20230513213035786](../../picture/image-20230513213035786.png)

![image-20230514145208504](../../picture/image-20230514145208504.png)

![image-20230514145251108](../../picture/image-20230514145251108.png)

### BigDecima

![image-20230514150210578](../../picture/image-20230514150210578.png)

![image-20230514150502132](../../picture/image-20230514150502132.png)

![image-20230514150524014](../../picture/image-20230514150524014.png)

### Java File类

####　一些小点　	

+ 在java中，如 E:\\java\\test.txt  实际环境中并不存在该路径时，![image-20230331163116317](../../picture/image-20230331163116317.png)

依然可以赋给一个对象，并且调用该对象的方法（File类本身的方法）![image-20230331163229014](../../picture/image-20230331163229014.png)

但其结果，都为否认

![image-20230331163347655](../../picture/image-20230331163347655.png)



+ 创建文件的时候注意一件事：*** 文件和文件夹也不能同名***

#### 文件对像的创建

![image-20230518200536557](../../picture/image-20230518200536557.png)

+ 其中，相对路径是相对与项目而言

  ![image-20230518200652073](../../picture/image-20230518200652073.png)

![image-20230518200706207](../../picture/image-20230518200706207.png)

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

#### 基本的方法

##### 查询类方法

![image-20230518201707210](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518201707210.png)

+ 判断的方法都没什么好注意的

![image-20230518202011503](../../picture/image-20230518202011503.png)

![image-20230518202243368](../../picture/image-20230518202243368.png)

##### 创建及删除方法

![image-20230518202322477](../../picture/image-20230518202322477.png)

#### createNewFile()方法

![image-20230518203248366](../../picture/image-20230518203248366.png)

+ 问文件可以没有后缀名

#### mkdir()方法

![image-20230518203514466](../../picture/image-20230518203514466.png)

#### mkdirs()方法

+ mkdirs方法和mkdir方法一样，创建文件或文件夹的时候，需要在创建文件对象时直接写出这个文件名。

![image-20230518203729223](../../picture/image-20230518203729223.png)

#### delete方法

![image-20230518203914020](../../picture/image-20230518203914020.png)

#### 文件遍历

![image-20230518204000721](../../picture/image-20230518204000721.png)

![image-20230518205116799](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518205116799.png)

![image-20230518205143880](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518205143880.png)

![image-20230518205327476](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518205327476.png)

####　简易的文件过滤器

![image-20230518205550990](../../picture/image-20230518205550990.png)

![image-20230518205740663](../../picture/image-20230518205740663.png)

+ 实现的方式很多。核心就是再遍历时候判断就好了。

``` java
 File a=new File("E:\\java_test_IO");
        for (File tt:a.listFiles()) {
            if (tt.isFile()&& tt.getName().endsWith(".txt")) {
                System.out.println(tt);
            }
        }//稍微百度以下就知道了

```





## object

+ object是所有类的父类。一个类只能继承一个类，但object依然是所有类的父类，因为一个类不管怎么继承，它的父类的父类都是object，这是种巧妙的设计。
+ object仅有三种方法
+ object没有任何参数，因为它是最高的抽象。

![image-20230424195437295](../../picture/image-20230424195437295.png)



### 对象克隆

+ 要注意的是：在创建对象的时候会产生异常
+ ![image-20230511203403457](../../picture/image-20230511203403457.png)

![image-20230425113735405](../../picture/image-20230425113735405.png)

![image-20230511204351364](../../picture/image-20230511204351364.png)

![image-20230511204515807](../../picture/image-20230511204515807.png)

![image-20230511204759844](../../picture/image-20230511204759844.png)

![image-20230511204911744](../../picture/image-20230511204911744.png)

> 深克隆重写的方法

![image-20230511205138573](../../picture/image-20230511205138573.png)

![image-20230511205400626](../../picture/image-20230511205400626.png)

![image-20230511210529399](../../picture/image-20230511210529399.png)

![image-20230513140528470](../../picture/image-20230513140528470.png)

大的这个数

## 异常

[看这个文章](https://blog.csdn.net/qq_44715943/article/details/116375510?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522168164939816800211594614%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=168164939816800211594614&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-116375510-null-null.142^v83^control,239^v2^insert_chatgpt&utm_term=java%E5%BC%82%E5%B8%B8&spm=1018.2226.3001.4187)

### 异常的处理方式

![image-20230518195127192](../../picture/image-20230518195127192.png)

![image-20230518195144865](../../picture/image-20230518195144865.png)

![image-20230518195207469](../../picture/image-20230518195207469.png)

+ 问题三指的是出现不是try捕获的异常时，会发生什么事？



> 答案一

![image-20230518195449688](../../picture/image-20230518195449688.png)

> 答案二



![image-20230518195424443](../../picture/image-20230518195424443.png)

>  答案三

![image-20230518195515839](../../picture/image-20230518195515839.png)

> 答案四

![image-20230518200012701](../../picture/image-20230518200012701.png)

![image-20230518200041958](../../picture/image-20230518200041958.png)

## 包装类

[看这里](https://blog.csdn.net/sinat_30973431/article/details/89332443?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522168447563216800227436612%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=168447563216800227436612&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-89332443-null-null.142^v87^control,239^v2^insert_chatgpt&utm_term=java%E5%8C%85%E8%A3%85%E7%B1%BB&spm=1018.2226.3001.4187)

![image-20230519135558177](../../picture/image-20230519135558177.png)

## 泛型

![image-20230524175054063](../../picture/image-20230524175054063.png)

## 反射

![image-20230519153606765](../../picture/image-20230519153606765.png)

![image-20230519154912557](../../picture/image-20230519154912557.png)

![image-20230519154940852](../../picture/image-20230519154940852.png)

![image-20230519155111053](../../picture/image-20230519155111053.png)

## 集合

***首先，抛弃你的固有观念。数组是数据结构，虽然不知道数组是怎么实现的。而集合是一群数据结构的总和，里面有哈希、树等东西。***

### 集合基本概念

![image-20230519133521932](../../picture/image-20230519133521932.png)

### 单列集合

#### ArrayList

![image-20230422105420371](../../picture/image-20230422105420371.png)

+ 打印的结果![image-20230422105654561](../../picture/image-20230422105654561.png)

+ 关于集合可能会产生的问题

![image-20230519140543154](../../picture/image-20230519140543154.png)

![image-20230519140722585](../../picture/image-20230519140722585.png)

![image-20230519133849161](../../picture/image-20230519133849161.png)

### 双列集合

![image-20230416210506048](../../picture/image-20230416210506048.png)

+ 双列集合的顶级接口是map

#### map介绍

+ map是一种键值对的集合，需要一个键和一个值。

![image-20230416211609838](../../picture/image-20230416211609838.png)

+ put方法（注意是否已有元素要插入的元素了）

![image-20230416211057827](../../picture/image-20230416211057827.png)



## JAVA注解

###### @Override 注解：用于注解重写方法，被标注的方法必须是重写方法。

+ Override只能用于方法，不能用其他

###### @Deprecated 注解：被标注过时内容。

+ 标注范围很广泛，不用记

###### @SuppressWarnings 注解：抑制编译器的警告



![image-20230330212926526](../../picture/image-20230330212926526.png)
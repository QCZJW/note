# java 学习笔记





![image-20230416204323911](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230416204323911.png)

![image-20230416204350353](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230416204350353.png)

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

### String类

+ ![image-20230422102218212](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422102218212.png)
+ ![image-20230422103314725](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422103314725.png)
+ ![image-20230422103453916](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422103453916.png)
+ ![image-20230422103558078](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422103558078.png)
+ ![image-20230422103717091](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422103717091.png)
+ ![image-20230422103746700](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422103746700.png)
+ ![image-20230422103813707](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422103813707.png)
+ ![image-20230422104040869](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422104040869.png)

### StringBuilder类

+ 当一个字符串要频繁地拼接时，用String太慢了，因为String将两个字符串拼成一个新的字符串和，再和下一个拼接，一直重复这个过程。所以要用StringBuilder（可变长字符序列）。

### StringJoiner

+ 能够指定拼接格式

+ ![image-20230422102022218](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230422102022218.png)

  

## 异常

[看这个文章](https://blog.csdn.net/qq_44715943/article/details/116375510?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522168164939816800211594614%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=168164939816800211594614&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-116375510-null-null.142^v83^control,239^v2^insert_chatgpt&utm_term=java%E5%BC%82%E5%B8%B8&spm=1018.2226.3001.4187)

### 异常的处理方式

![image-20230518195127192](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518195127192.png)

![image-20230518195144865](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518195144865.png)

![image-20230518195207469](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518195207469.png)

+ 问题三指的是出现不是try捕获的异常时，会发生什么事？



> 答案一

![image-20230518195449688](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518195449688.png)

> 答案二



![image-20230518195424443](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518195424443.png)

>  答案三

![image-20230518195515839](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518195515839.png)

> 答案四

![image-20230518200012701](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518200012701.png)

![image-20230518200041958](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518200041958.png)

## java包装类

[看这里](https://blog.csdn.net/sinat_30973431/article/details/89332443?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522168447563216800227436612%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=168447563216800227436612&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-89332443-null-null.142^v87^control,239^v2^insert_chatgpt&utm_term=java%E5%8C%85%E8%A3%85%E7%B1%BB&spm=1018.2226.3001.4187)

![image-20230519135558177](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230519135558177.png)

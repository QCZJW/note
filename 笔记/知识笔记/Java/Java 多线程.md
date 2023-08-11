# 多线程

[一些大致总结](https://blog.csdn.net/Evankaka/article/details/44153709?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522168327223216800197092133%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=168327223216800197092133&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-44153709-null-null.142^v86^control,239^v2^insert_chatgpt&utm_term=%E5%A4%9A%E7%BA%BF%E7%A8%8B&spm=1018.2226.3001.4187)

## 基本概念

![image-20230505144808004](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230505144808004.png)

![image-20230505144645774](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230505144645774.png)

![image-20230505145027596](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230505145027596.png)

多线程序特点是能同时做多件事，将等待的事件利用起来

![image-20230505145402108](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230505145402108.png)

## 多线程的两个概念

![image-20230505145444581](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230505145444581.png)

![image-20230505145629966](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230505145629966.png)

![image-20230505145702680](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230505145702680.png)

![image-20230505145717552](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230505145717552.png)

看自带的线程是否足够，不足够便成并发了

## 创建线程的三种方式

![image-20230516131007368](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516131007368.png)

### 使用Thread创建线程

![image-20230516131030651](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516131030651.png)



![image-20230516132000779](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516132000779.png)

> 结果

![image-20230516132030933](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516132030933.png)

``` java
public class MyThread extends Thread{
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            System.out.println(getName()+"  "+i);
        }
    }
}
```

``` java
public class tt {
    public static void main(String[] args) {
        MyThread a=new MyThread();
        MyThread a1=new MyThread();
        a.start();
        a1.start();
    }
}
```

+ 使用setName取名字

![image-20230516132243195](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516132243195.png)

### 使用Runnable创建线程

+ 与使用Thread创建线程没有什么大的差别。
+ ![image-20230516133130352](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516133130352.png)
+ Runnable接口仅有一个run方法，因此使用Thread来进行开启线程
+ 因为提倡使用接口编程，所以如此

![image-20230516132431413](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516132431413.png)

![image-20230516134345578](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516134345578.png)

上面这段代码很有意思（代码执行后，有三个不同的线程争着运行）

> 右边的代码

+ 第五行创建了线程要做的事。第六行也是如此。虽然他们是在做同一件事。
+ 第七行，创建了一个线程，却不打算在以后对这个线程进行任何操作，因此没有使用变量把线程存起来。后面几行也是如此

> 左边的代码

+ 为了知道做事的线程是谁，于是创建了一个Thread对象，使用这个对象的名字来进行区分不同的线程
+ 这显示了多线程的一个本质：***多个线程在争抢一个执行机会***。所以代码没有重复创建Thread对象，代码只是停住了。

![image-20230516140823123](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516140823123.png)

还可以这样为线程命名。

 ### 使用 创建线程

> 为什么要使用这两个呢？

+ 因为使用Thread和Runnable方法没有返回值，不能知道线程运行的结果

![image-20230516204347945](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516204347945.png)

![image-20230516204528301](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516204528301.png)

![image-20230516204551772](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516204551772.png)

## 多线程常用的方法

![image-20230516204741733](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516204741733.png)

#### 关于守护线程

![image-20230516205302936](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516205302936.png)

## 线程的生命周期

![image-20230516205426462](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516205426462.png)

## 锁

### 线程锁

![image-20230516211704962](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516211704962.png)

![image-20230516212330800](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230516212330800.png)

+ ***由于会创建多个Thread对象，所以如果ticket不是静态，那么数据将无法共享。（静态的东西会先加载，且仅加载一次）***
+ 上述代码可能会出现一张票卖给多个人的情况。***因为一个线程调用了方法后，休眠了，这个时候另外一个线程开始调用方法。于是产生了一张票卖给多个人的现象。***
+ 超出范围也是这个理由

![image-20230517163319005](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517163319005.png)

![image-20230517163912997](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517163912997.png)

+ 线程锁可以是任意的对象。但要求是***唯一***的，不然就不能起到锁的作用，因为不同的人用不同的锁对象

![image-20230517164053166](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517164053166.png)

+ 不能将锁写在循环外面，这样会使得其他线程无法执行到

![image-20230517171347439](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517171347439.png)

+ 为了保证锁对象是唯一的，一般使用字节码文件。

### 方法锁

![image-20230517171617438](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517171617438.png)

### Lock锁

![image-20230517203546134](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517203546134.png)

+ Lock锁可以不像synchronized锁一样，不能手动上锁、释放锁。

![image-20230517203854249](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517203854249.png)

+ 以上代码会造成lock锁无法释放的问题

![image-20230517204229511](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517204229511.png)

+ 使用异常机制来处理。也可以找别的方法，不过这是最优的

### 死锁

![image-20230517204500448](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517204500448.png)

+ 死锁指的是，两个锁都在等待着对方释放。因此场面僵住了

## 打破线程的随机执行



![image-20230518084240892](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518084240892.png)





## 线程的七大状态

![image-20230518124425117](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518124425117.png)







### 使用阻塞队列实现等待唤醒机制









![image-20230518124617879](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230518124617879.png)

+ 在java中运行这个状态并不存在。

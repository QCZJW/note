# JS 学习笔记

https://www.kuangstudy.com/download***去看这个笔记***

+ JS的变量定义只用var，var会因接收的值而改变自己的类型。
+ JS中可以为对象添加事件、属性，甚至可以用for来对一个对象数组添加事件、属性。
+ JS中，可以将对象所引用的css样式也改变。
+ 因为JS是弱类型语言，所以不能像java一样用double来处理浮点数。在js中运行1/3==1-2/3，得出是false。
+ Js中有一种叫严格检查模式的东西。![image-20230416194635195](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230416194635195.png)

打下这一行代码，就能开启严格检查模式。

+ 局部变量用let定义。

## 关于变量

![image-20230704173341929](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230704173341929.png)



## 数据类型

![image-20230704173514947](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230704173514947.png)

![image-20230704173637025](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230704173637025.png)

![image-20230704173706150](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230704173706150.png)

## 对象

+ js中的对象可以在定义完后删除属性或添加属性
+ ![image-20230416202159292](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230416202159292.png)

## DOM

+ ![image-20230504103129081](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230504103129081.png)
+ 以上有几个节点？
  + 答案是三个
  + ![image-20230504103213790](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230504103213790.png)
  + 选中的也是一个节点哦，不过是空的
+ 下面就是一个对象了

![image-20230511200955860](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230511200955860.png)

### 选择器

![image-20230607164419118](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230607164419118.png)

而#nav>li才是选择nav下一级的li，不包括子代

### 关于a标签

+ 只有在href有值的时候才会变成超链接的样子

## 关于e

可以使用 

``` js
var e=e||window
```

来使得事件对象e变成相应的浏览器的版本

+ 属性可以直接获得，而样式需要同国style来获得。

### 该死的e

![image-20230525161653939](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230525161653939.png)



## Js中的对象

![image-20230715095200271](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715095200271.png)

### json

![image-20230715095532326](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715095532326.png)

![image-20230715095552396](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715095552396.png)

+ json的基本语法

![image-20230715095808327](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715095808327.png)



+ 获取json中的值

![image-20230715095935720](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715095935720.png)

## 关于Bom

![image-20230715100202554](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715100202554.png)



+ java程序员只需要了解window和location即可
+ 很简单，所以不截图了

## 关于Dom

![image-20230715100452975](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715100452975.png)

![image-20230715101016059](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715101016059.png)

## 事件

![image-20230715101818131](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230715101818131.png)

## 关于回调函数

回调函数是一种特殊类型的函数，它作为参数传递给其他函数，并在某个特定的事件或条件发生时被调用执行。回调函数的目的是为了处理异步操作、事件处理和其他需要在特定情况下执行的代码。

异步操作是指在代码执行期间，不会立即返回结果的操作。常见的异步操作包括网络请求、文件读写、定时器等。由于这些操作需要等待一段时间才能获取结果，因此在异步操作完成后，我们需要执行一些操作来处理结果或执行其他相关任务。

回调函数的工作方式是将一个函数作为参数传递给另一个函数。当特定事件或条件满足时，另一个函数会调用传入的回调函数，将结果或其他相关信息作为参数传递给它，从而触发回调函数的执行。

回调函数在异步编程中非常常见，它们允许我们定义在异步操作完成后所需执行的代码逻辑。通过使用回调函数，我们可以确保在异步操作完成后，根据需要执行相应的操作，而不会阻塞主线程。

总结起来，回调函数是一种在特定事件或条件满足时被调用的函数，用于处理异步操作的结果或执行其他相关任务。它们在异步编程中非常有用，可以帮助我们处理异步操作的结果并进行相应的处理。


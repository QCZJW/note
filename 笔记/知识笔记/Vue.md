# Vue

![image-20230727100006789](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727100006789.png)

![image-20230727100239321](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727100239321.png)

+ vue使用双向数据绑定，view是视图层，当视图层发生改变时，model层相应数据也发送改变。反之同理



## vue的使用

### 创建vue核心对象

![image-20230727155402582](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727155402582.png)

+ 是el 不是e1
+ v-model是一个**指令**，使得数据双向绑定
+ 每一个vue实例只能由一个el
+ ![image-20230727163121466](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727163121466.png)
+ 想要控制多个元素，就需要创建多个vue
+ 图中el对应的值是id选择器加app1
+ 一个元素只能绑定一个vue元素
+ 

![image-20230727163430816](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727163430816.png)

### 差值表达式

+ {{}} 叫做差值表达式

+ ![image-20230727163656155](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727163656155.png)

+ ![image-20230727163758221](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727163758221.png)
+ 只要名称相同，可以叫任何东西
+ ![image-20230727170307043](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727170307043.png)



## 常见的vue指令

![image-20230727170400482](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727170400482.png)

![image-20230727171508697](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727171508697.png)

### 使用v-bind

![image-20230727170733420](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727170733420.png)

+ 这样a标签所链接的东西就是随着vue对象变化而变化了

![image-20230727171602303](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727171602303.png)

+ 通过更改v-on后面的click和” “中的内容，可以实现不同的事件触发不同的方法
+ 方法要写在methods区域
+ 可以使用@来简写

### v-show与v-if

![image-20230727195844032](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727195844032.png)

+ 通过v-if实现，只会出现符合条件的元素
+ ![image-20230727202147728](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230727202147728.png)

+ 而通过v-show则将所有元素加载出来，但只显示符合条件的元素

### v-for

![image-20230731095858176](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230731095858176.png)

```js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<script src="vue.js"></script>
<body> 
    <div id="app">
        <div v-for="a in arr">{{arr}}</div>
    </div>
</body>

<script>
    new Vue({
        el: "#app",
        data: {
            arr: ['a', 'b', 'c']
        }
    })
</script>

</html>
```

![image-20230731103204033](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230731103204033.png)

+ 以上代码输出这个，代表了每次遍历都输出一遍arr的内容
+ {{}}这个插值对只输出相应内容，而a in arr做到了遍历
+ in是必不可少的

``` js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<script src="vue.js"></script>
<body> 
    <div id="app">
        <div v-for="a in arr">{{a}}</div>//改动了这里
    </div>
</body>

<script>
    new Vue({
        el: "#app",
        data: {
            arr: ['a', 'b', 'c']
        }
    })
</script>

</html>
```

![image-20230731103432688](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230731103432688.png)

+ 证明a取到了相应内容，而插值对也做出了相应输出 
+ v-for 的索引默认从零开始
+ 插值表达式中可以进行算数运算

### 注意

![image-20230731164627162](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230731164627162.png)

+ 使用集合存储数据时，记得搞清楚具体的名字

## vue的生命周期

 	![image-20230731165733367](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230731165733367.png)

![image-20230731165822363](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230731165822363.png)
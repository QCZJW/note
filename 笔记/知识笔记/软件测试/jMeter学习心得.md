# jMeter学习心得

## 定时器

+ 定时器是在请求之前生效，也就是说，先等待再请求。

![image-20230620210529323](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230620210529323.png)

+ 在上图中，该定时器会对用户行为下所有子节点生效
+ ![image-20230620210818240](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230620210818240.png)
+ 因此，所有aaa等都要等待三秒

### 正确的使用方式

将定时器放在下一个录制里。或者说，不要将定时器放在一个请求下即可

### 也可以使用取样器里的测试活动来模拟间隔



## jMeter录制功能

想要使用代理功能，要先建一个 非测试单元 > http代理服务器

+ 该代理服务器要设置端口号（和你计算机的代理一样）
+ ![image-20230620203329719](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230620203329719.png)

+ 还要设置分组 （每个组放入一个新的事务）

然后添加一个线程组，在线程组添加逻辑控制器 > 录制控制器

然后就可以开始使用录制功能了



一个好用的插件叫，用于管理代理

#### **SwitchyOmega**
# MySql

+ MySql不区分大小写

+ MySql分为四种语言

  + > (1)DDL(Data Definition Language)：
    > 数据定义语言.用于数据库、数据表的定义
    >
    > (2)DML(Data Manipulation Language)：
    > 数据操作语言.用于操作表格记录(插入、更新、删除)
    >
    > (3)DCL(Data Control Language)：
    > 数据控制语言.创建用户、分配权限、设置安全级别
    >
    > (4)DQL(Data Query Language)：
    > 数据查询语言（select）

## mysql中一些操作符号

### 数据过滤的方式（where、and，or，in）

> 这是创建的完整代码

```mysql

```



![image-20230512105632890](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230512105632890.png)

+ ```mysql
  select ename,job from emp where deptno=10 or deptno=20;
  ```

  ![image-20230512110211948](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230512110211948.png)

> enam、job、deptno是列，emp是表名。

+  ***or***的作用为 或

  + 也可以用***in***来实现相同的事情

  + ```mysql
    select ename,job from emp where deptno in (10,20);
    ```

  + ![image-20230512110148174](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230512110148174.png)

+ and作用也差不多

+ 需要注意的是：可以将符号们组合起来，比如

  + ```mysql
    select ename,job,sal from emp where (deptno=10 or deptno=20) and sal>1000;
    ```

  + ![image-20230512110013335](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230512110013335.png)



# 一些特殊的东西

![image-20230517090803358](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230517090803358.png)

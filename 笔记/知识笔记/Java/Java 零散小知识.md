# java零散小知识

+ 类名 方法名;表示在栈中开辟了一块空间（T是泛型表示）

  类名 方法名=new 类名();表示在栈里开辟了一块空间，又在堆里开辟了块空间，并且栈指向了堆。

+ ==对基本类型和引用类型判断的不是相同的，对于基本类型，判断值是否相同，对于引用类型判断地址是否相同

+ 在java中，类是一种引用数据类型。对象是一种概念，对象有一些可以标识它是这种对象的东西，即可以有属性与方法，任何东西都可以成为对象。类将对象所有的抽象了出来。通过类，可以创建多个对象，对象是类的具体实现。

+ 类拥有属性、方法、构造器、代码块、内部类。类的静态代码块会先执行，但非静态的不会，静态代码块不能出现在方法的内部。

+ 内部类可直接访问外部类成员，内部类本质依然是内部类因此也有类的五部分。

  内部类如局部变量一样不能使用访问修饰符，但可以使用final。

  外部类和内部类成员重名时，遵循就近原则。可用外部类.this.成员，调用重名的外部成员。

  匿名内部类名字由系统分配。匿名内部类即是类，也是对象

+ 直接输出对象时，则默认调用toString方法

+ 销毁对象前，会调用finalize方法

+ java调用子类构造器时，会先默认调用父类无参构造器

+ ![image-20230324213256655](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230324213256655.png)

+ ![image-20230324214024443](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230324214024443.png)

+ ![image-20230326170733413](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230326170733413.png)

+ ![image-20230326212944013](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230326212944013.png)

+ System的方法![image-20230423104803582](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230423104803582.png)

+ ![image-20230423104905472](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230423104905472.png)

+ ![image-20230423104957369](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230423104957369.png)

+ lang包不需要导入

+ Null对象不能调用任何方法。

+ 左边括号表示要接收的参数，右边表示该方法的返回值。

![image-20230519134122118](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230519134122118.png)
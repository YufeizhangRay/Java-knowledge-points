# Java-knowledge-points
Java琐碎知识点

踩过的浅坑，吃过的暗亏。  
  
主要为`Java`，少量其他。  

`静态域`中包含`静态变量`、`静态块`和`静态方法`,其中`需要初始化`的是`静态变量`和`静态块`.而他们两个的初始化顺序是靠他们俩的`位置`决定的。  

对于`-128`到`127`之间的数，`Java`会对其进行`缓存`。而超出这个范围则新建一个对象。  

`Java`的赋值运算是`有返回值`的，赋了什么值，就返回什么值。  

`replaceAll`方法的第一个参数可以是一个正则表达式，例如`"."`在正则表达式中表示`任何字符`，所以会把前面字符串的所有字符都替换。如果想替换的只是`"."`，那么要写成`"\\."` 。而 `replace`可以直接使用`"."`。

`Json`格式：应该是需要加`引号`，并且是一对一对出现的。   

`abstract`关键字不可以与`final`,`private`,`static`关键字共存。  

`finally`语句块在`catch`语句块中的`return`语句之前执行。    
`finally`块中的`return`语句会`覆盖`掉`try`块中的`return`返回。  
`finally`语句是在`try`的`return``语句执行`之后，`return``返回之前`执行。  

str+='      a' 有空格需要用`双引号`。  

`Java调试器`:`jdb.exe`  

`JDK`中提供的`java`、`javac`、`jar`等开发工具也是用`Java`编写的。  

`ASCII`码包含一些`特殊空字符`，不可打印。  

`JSP` 9个内置对象  
>1.`pageContext` 表示页容器 EL表达式、 标签 、上传   
2.`request` 服务器端取得客户端的信息：头信息 、Cookie 、请求参数 ，最大用处在MVC设计模式上   
3.`response` 服务器端回应客户端信息：Cookie、重定向   
4.`session` 表示每一个用户，用于登录验证上   
5.`application` 表示整个服务器   
6.`config` 取得初始化参数，初始化参数在web.xml文件中配置   
7.`exception` 表示的是错误页的处理操作   
8.`page` 如同this一样，代表整个jsp页面自身   
9.`out` 输出 ，但是尽量使用表达式输出  
    
`Properties` 是线程安全的。   

`float [][]f = new float[6][];`可以创建  
`float f[][] = new float[][6];`不可创建  
  
`final`类型修饰的`Byte`，计算时不会自动提升。  

`final`类型的变量一定要初始化，因为`final`的变量`不可更改`。  

面向对象的五大基本原则：  
>单一职责原则（SRP）  
开放封闭原则（OCP）   
里氏替换原则（LSP）   
依赖倒置原则（DIP）   
接口隔离原则（ISP）  
  
方法的重写（`override`）`两同两小一大`原则：  
>方法名相同，参数类型相同  
子类返回类型小于等于父类方法返回类型，  
子类抛出异常小于等于父类方法抛出异常，  
子类访问权限大于等于父类方法访问权限  
  
抽象类与接口的区别：
>1.抽象类可以有构造方法，接口中不能有构造方法。  
2.抽象类中可以有普通成员变量，接口中没有普通成员变量。  
3.抽象类中可以包含非抽象的普通方法，接口中的所有方法必须都是抽象的，不能有非抽象的普通方法。（`Java8之后 接口可以有default、static方法`)  
4.抽象类中的抽象方法的访问类型可以是`public`，`protected`和（默认类型,虽然eclipse下不报错，但应该也不行），但接口中的抽象方法只能是`public`类型的，并且默认即为`public abstract`类型。  
5.抽象类中可以包含静态方法，接口中不能包含静态方法。（`Java8之后 接口可以有default、static方法`）  
6.抽象类和接口中都可以包含静态成员变量，抽象类中的静态成员变量的访问类型可以任意，但接口中定义的变量只能是`public static final`类型，并且默认即为`public static final`类型。  
  
`boolean`类型`不能`和`任何类型`进行转换。  
方法是可以和类名同名的，和构造方法唯一的区别就是，构造方法`没有返回值`。  

如果两个操作数其中有一个是`double`类型，另一个操作就会转换为`double`类型。  
否则，如果其中一个操作数是`float`类型，另一个将会转换为`float`类型。  
否则，如果其中一个操作数是`long`类型，另一个会转换为`long`类型。  

在`Java`中，声明一个数组时，不能直接限定数组长度，只有在`创建实例化对象`时，才能对给定数组长度.  

向上转型，父类的引用无法访问`子类独有`的方法。  

抛InterruptedException的代表方法有：
>java.lang.Object 类的 `wait` 方法  
java.lang.Thread 类的 `sleep `方法  
java.lang.Thread 类的 `join`方法  
CyclicBarrier.await  
  
`Java`一律采用`Unicode`编码方式，每个字符无论中文还是英文字符`都占用2个字节`。  
`Java`的`class`文件编码为`UTF-8`，而虚拟机`JVM编`码为`UTF-16`。  
`UTF-8`编码下，一个`中文占3个字节`，一个`英文占1个字节`。  

不同编码之间是可以转换的，通常流程如下：  
将字符串S以其自身编码方式分解为字节数组，再将字节数组以你想要输出的编码方式重新编码为字符串。  
例：String newUTF8Str = new String(oldGBKStr.getBytes("GBK"), "UTF8")  

`ResourceBundle`能够依据`Local`的不同，选择性的读取与`Local`对应后缀的`properties文件`，以达到国际化的目的。  

在方法内定义的变量在使用之前`必须初始化`，否则报错。  

`Java中的包`一般均包含`相关的类`，`Java`是跨平台的，所以`Java中的包`和操作系统`没有任何关系`，`Java中的包`是用来组织文件的一种`虚拟文件系统`。  

`MySQL`的`组合索引`（复合索引）的`最左优先原则`。最左优先就是说组合索引的`第一个字段必须出现`在查询组句中，这个索引才会被用到。只要组合索引最左边第一个字段出现在where中，那么不管后面的字段出现与否或者出现顺序如何，`MySQL引擎`都会自动调用索引来优化查询效率。   

`try{}catch{}`会增加额外的开销。  

`hashcode`和`equals`的约定关系如下：  
>1.如果两个对象相等，那么他们`一定`有相同的哈希值(`hash code`)。  
2.如果两个对象的哈希值相等，那么这两个对象`不一定`相等。（需要再通过`equals`来判断）  
  
`main()`函数即主函数，是一个`前台线程`，前台进程是程序中`必须执行完成`的，而`后台线程`则是`Java`中`所有前台结束后结束`，不管有没有完成。后台线程主要用与`内存分配`等方面。  

`ThreadLocal`继承`Object`，相当于没继承任何特殊的。  
`ThreadLocal`没有实现`任何接口`。  
`ThreadLocal`并不是一个`Thread`，而是`Thread`的`局部变量`。  

包装类的`“==”`运算在`不遇到算术运算`的情况下`不会`自动拆箱。  
包装类的`equals()`方法`不处理数据转型`。  

`Java`继承中对构造函数是`不继承`的，只是`显式`或者`隐式`调用。  

`Java`的`object`默认的基本方法中没有`copy()`，含有如下方法：  
`getClass()`, `hashCode()`, `equals()`, `clone()`, `toString()`, `notify()`, `notifyAll()`,  `wait()`, `finalize()` 

优化`Hibernate`所鼓励的7大措施：  
>1.尽量使用`many-to-one`，避免使用单项`one-to-many`  
2.灵活使用单向`one-to-many`  
3.不用`one-to-one`，使用多`many-to-one`代替  
4.配置对象缓存，不使用集合缓存  
5.`one-to-many`使用Bag，`many-to-one`使用Set  
6.继承使用显示多态 `HQL:from object polymorphism="exlicit"` 避免查处所有对象  
7.消除大表，使用二级缓存  
  
`wait()`方法要以`try/catch`包覆，或是掷出`InterruptedException`。  

`y=x++ + ++x`可以看成是`y=(x++)+(++x)`，当++或者--和其它变量进行运算时，x++表示`先运算再自增`，++x表示`先自增再运算`，
所以x为-1参与运算，然后自增，x此时为0，++x后x为1，然后参与运算，那么y=-1+1就为0，此时x为1。  

count = count ++;这个先将count这个值0暂存起来，然后count自加1变成1，最后将暂存的值赋值给count，count最终的值为0。  

>1.静态内部类才可以声明静态方法。  
2.静态方法不可以使用非静态变量。  
3.抽象方法不可以有函数体。  
  
`~n=-n-1` 

`UR`L的`toString`方法返回字符串，无论网址是否存在。  

>`use-a`  是依赖关系  
`has-a`  一般是组合关系  
`is-a`   一般是继承关系   
  
`局部内部类`是放在`代码块或方法`中的，`不能`有`访问控制修饰符`，且不能用`static`修饰，可以用`abstract final`修饰。  

Linux  
>`字符串拷贝`  
strcpy    
strncpy   
strlcpy  
`字符串拼接`  
strcat  
strncat  
strlcat  
`字符串分解`  
strtok  
将格式化的数据写入字符串  
snprintf  
`使用场景不同`且`snprintf`在`stdio.h`头文件中，其他的在`string.h`头文件中  
  
linux使用的进程间通信方式  
>1.管道(pipe),流管道(s_pipe)和有名管道(FIFO)  
2.信号(signal)  
3.息队列  
4.共享内存  
5.信号量  
6.套接字(socket)  
  
在`JVM`中，加载的对象在内存中包括三部分：`对象头`、`实例数据`、`填充`。其中，对象头包括`指向对象所属类型的指针`和`MarkWord`，而`MarkWord`中除了包含对象的`GC分代年龄信息`、`加锁状态信息`外，还包括了`对象的hashcode`；对象实例数据是对象真正存储的`有效信息`；填充部分仅起到`占位符`的作用, 原因是`HotSpot`要求对象`起始地址必须是8字节的整数倍`。  
  
当两个线程竞争同一资源时，如果对资源的访问顺序敏感，就称存在竞态条件。导致竞态条件发生的代码区称作临界区。  
  
`JRE` 代表 `Java 运行时`（`Java run-time`），是运行 `Java `引用所必须的。  
`JDK` 代表 `Java开发工具`（`Java development kit`），是 `Java` 程序的`开发工具`，如 `Java 编译器`，它也包含 `JRE`。  
`JVM` 代表 `Java 虚拟机`（`Java virtual machine`），它的责任是运行 `Java` 应用。  
`JIT `代表`即时编译`（`Just In Time compilation`），当代码执行的次数超过一定的`阈值`时，会将 `Java字节码`转换为`本地代码`，如，主要的热点代码会被准换为本地代码，这样有利大幅度提高 `Java` 应用的性能。  
  
常用的开源Java Web容器有Tomcat、Resin和Jetty。    
  
在Java中，char类型占2个字节，而且Java默认采用Unicode编码，一个Unicode码是16位，所以一个Unicode码占两个字节，Java中无论汉子还是英文字母都是用Unicode编码来表示的。所以，在Java中，char类型变量可以存储一个中文汉字。  
  
a += b会自动强制转换  
  
byte[] byteArray = str.getBytes();  
String str = new String(byteArray);  
  
如何将数值型字符转换为数字：Integer.parseInt(String.valueOf(ch))  
  
由于数组没有实现 toString() 方法，所以如果将数组传递给 System.out.println() 方法，将无法打印出数组的内容，但是 Arrays.toString() 可以打印每个元素。  
  
如果想使用 Java 中增强的循环来遍历，只需要实现 Iterable 接口。如果实现 Collection 接口，默认就具有该属性。  
  
Object的所有方法：  
>1.public final native Class<?> getClass()  
2.public native int hashCode()  
3.public boolean equals(Object obj)  
4.protected native Object clone() throws CloneNotSupportedException  
5.public String toString()  
6.public final native void notify()  
7.public final native void notifyAll()  
8.public final native void wait(long timeout) throws InterruptedException  
9.public final void wait(long timeout, int nanos) throws InterruptedException  
10.public final void wait() throws InterruptedException  
11.protected void finalize() throws Throwable { }  
  

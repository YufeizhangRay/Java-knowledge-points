# Java-knowledge-points
Java琐碎知识点

踩过的浅坑，吃过的暗亏。  
主要为Java，少量其他。  

静态域中包含静态变量、静态块和静态方法,其中需要初始化的是静态变量和静态块.而他们两个的初始化顺序是靠他们俩的位置决定的!  

对于-128到127之间的数，Java会对其进行缓存。而超出这个范围则新建一个对象。  

JAVA的赋值运算是有返回值的，赋了什么值，就返回什么值。  

由于replaceAll方法的第一个参数是一个正则表达式，而"."在正则表达式中表示任何字符，所以会把前面字符串的所有字符都替换成"/"。如果想替换的只是"."，那么久要写成"\\."  

Json格式：应该是需要加引号，并且是一对一对出现的。   

abstract关键字不可以与final，private,static关键字共存。  

finally语句块在catch语句块中的return语句之前执行。    
finally块中的return语句会覆盖try块中的return返回。  

str+='      a' 有空格需要用双引号。  

java调试器jdb.exe  

JDK中提供的java、javac、jar等开发工具也是用Java编写的。  

ASCII码包含一些特殊空字符，不可打印。  

JSP 9个内置对象  
>1、pageContext 表示页容器 EL表达式、 标签 、上传   
2、request 服务器端取得客户端的信息：头信息 、Cookie 、请求参数 ，最大用处在MVC设计模式上   
3、response 服务器端回应客户端信息：Cookie、重定向   
4、session 表示每一个用户，用于登录验证上   
5、application 表示整个服务器   
6、config 取得初始化参数，初始化参数在web.xml文件中配置   
7、exception 表示的是错误页的处理操作   
8、page 如同this一样，代表整个jsp页面自身   
9、out 输出 ，但是尽量使用表达式输出  
    
Properties 是线程安全的。   

float [][]f = new float[6][];可以创建  
float f[][] = new float[][6];不可创建  
  
final类型修饰的Byte，不会自动提升。  

final类型的变量一定要初始化，因为final的变量不可更改。  

面向对象的五大基本原则：  
>单一职责原则（SRP）  
开放封闭原则（OCP）   
里氏替换原则（LSP）   
依赖倒置原则（DIP）   
接口隔离原则（ISP）  
  
方法的重写（override）两同两小一大原则：  
>方法名相同，参数类型相同  
子类返回类型小于等于父类方法返回类型，  
子类抛出异常小于等于父类方法抛出异常，  
子类访问权限大于等于父类方法访问权限  
  
抽象类与接口的区别：
>1.抽象类可以有构造方法，接口中不能有构造方法。  
2.抽象类中可以有普通成员变量，接口中没有普通成员变量。  
3.抽象类中可以包含非抽象的普通方法，接口中的所有方法必须都是抽象的，不能有非抽象的普通方法。（java8之后 接口可以有default、static方法)  
4.抽象类中的抽象方法的访问类型可以是public，protected和（默认类型,虽然eclipse下不报错，但应该也不行），但接口中的抽象方法只能是public类型的，并且默认即为public abstract类型。  
5.抽象类中可以包含静态方法，接口中不能包含静态方法。（java8之后 接口可以有default、static方法）  
6.抽象类和接口中都可以包含静态成员变量，抽象类中的静态成员变量的访问类型可以任意，但接口中定义的变量只能是public static final类型，并且默认即为public static final类型。  
  
boolean类型不能和任何类型进行转换。  
方法是可以和类名同名的，和构造方法唯一的区别就是，构造方法没有返回值。  

如果两个操作数其中有一个是double类型，另一个操作就会转换为double类型。  
否则，如果其中一个操作数是float类型，另一个将会转换为float类型。  
否则，如果其中一个操作数是long类型，另一个会转换为long类型。  

在java 中，声明一个数组时，不能直接限定数组长度，只有在创建实例化对象时，才能对给定数组长度.  

向上转型，父类的引用无法访问子类独有的方法。  

抛InterruptedException的代表方法有：
>java.lang.Object 类的 wait 方法  
java.lang.Thread 类的 sleep 方法  
java.lang.Thread 类的 join 方法  
CyclicBarrier.await  
  
Java一律采用Unicode编码方式，每个字符无论中文还是英文字符都占用2个字节。  
Java的class文件编码为UTF-8，而虚拟机JVM编码为UTF-16。  
UTF-8编码下，一个中文占3个字节，一个英文占1个字节。  


不同的编码之间是可以转换的，通常流程如下：  
将字符串S以其自身编码方式分解为字节数组，再将字节数组以你想要输出的编码方式重新编码为字符串。  
例：String newUTF8Str = new String(oldGBKStr.getBytes("GBK"), "UTF8")  

ResourceBundle能够依据Local的不同，选择性的读取与Local对应后缀的properties文件，以达到国际化的目的。  

在方法内定义的变量在使用之前必须初始化，否则报错。  

Java中的包一般均包含相关的类，java是跨平台的，所以java中的包和操作系统没有任何关系，java的包是用来组织文件的一种虚拟文件系统。  

MySQL组合索引（复合索引）的最左优先原则。最左优先就是说组合索引的第一个字段必须出现在查询组句中，这个索引才会被用到。只要组合索引最左边第一个字段出现在Where中，那么不管后面的字段出现与否或者出现顺序如何，MySQL引擎都会自动调用索引来优化查询效率。   

try{}catch{}会增加额外的开销。  


hashcode和equals的约定关系如下：  
>1、如果两个对象相等，那么他们一定有相同的哈希值（hash code）。  
2、如果两个对象的哈希值相等，那么这两个对象有可能相等也有可能不相等。（需要再通过equals来判断）  
  
main()函数即主函数，是一个前台线程，前台进程是程序中必须执行完成的，而后台线程则是java中所有前台结束后结束，不管有没有完成。后台线程主要用与内存分配等方面。  


ThreadLocal继承Object，相当于没继承任何特殊的。  
ThreadLocal没有实现任何接口。  
ThreadLocal并不是一个Thread，而是Thread的局部变量。  

包装类的“==”运算在不遇到算术运算的情况下不会自动拆箱。  
包装类的equals()方法不处理数据转型。  

java继承中对构造函数是不继承的，只是显式或者隐式调用。  

java object默认的基本方法中没有copy()，含有如下方法：  
getClass(), hashCode(), equals(), clone(), toString(), notify(), notifyAll(),  wait(), finalize()  

优化Hibernate所鼓励的7大措施：  
>1.尽量使用many-to-one，避免使用单项one-to-many  
2.灵活使用单向one-to-many  
3.不用一对一，使用多对一代替一对一  
4.配置对象缓存，不使用集合缓存  
5.一对多使用Bag 多对一使用Set  
6.继承使用显示多态 HQL:from object polymorphism="exlicit" 避免查处所有对象  
7.消除大表，使用二级缓存  
  
wait() 方法要以 try/catch 包覆，或是掷出 InterruptedException。  

y=x++ + ++x可以看成是y=(x++)+(++x)，当++或者--和其它变量进行运算时，x++表示先运算，再自增，++x表示先自增再参与运算
所以就时x为-1参与运算，然后自增，x此时为0，++x后x为1，然后参与运算，那么y=-1+1就为0，此时x为1。  

count = count ++;这个先将count这个值0暂存起来，然后count自加1变成1，最后将暂存的值赋值给count，count最终的值为0。  

>1.静态内部类才可以声明静态方法。  
2.静态方法不可以使用非静态变量。  
3.抽象方法不可以有函数体。  
  
~n=-n-1  

URL的toString方法返回字符串，无论网址是否存在。  

>use-a  是依赖关系  
has-a  一般是组合关系  
is-a   一般是继承关系   
  
局部内部类是放在代码块或方法中的，不能有访问控制修饰符，且不能用static修饰，可以用abstract final修饰。  

Linux  
>字符串拷贝  
strcpy    
strncpy   
strlcpy  
字符串拼接  
strcat  
strncat  
strlcat  
字符串分解  
strtok  
将格式化的数据写入字符串  
snprintf  
使用场景不同且snprintf 在stdio.h头文件中，其他的在string.h头文件中  
  
linux使用的进程间通信方式  
>1.管道(pipe),流管道(s_pipe)和有名管道(FIFO)  
2.信号(signal)  
3.息队列  
4.共享内存  
5.信号量  
6.套接字(socket)  
  
在JVM中，加载的对象在内存中包括三部分：对象头、实例数据、填充。其中，对象头包括指向对象所属类型的指针和MarkWord，而MarkWord中除了包含对象的GC分代年龄信息、加锁状态信息外，还包括了对象的hashcode；对象实例数据是对象真正存储的有效信息；填充部分仅起到占位符的作用, 原因是HotSpot要求对象起始地址必须是8字节的整数倍。  




---


---

<pre><code>输出
System.out.print(); 仅输出字符，无换行
System.out.println(); 输出字符并换行
System.out.printf(); 需填写表示符

输入
Scanner s = new Scanner(System.in);
int a = s.nextInt(); 获取整型
float b = s.nextFloat(); 获取浮点型
Java没有char型，使用string
String str = s.next();

基本类型
整数类型 byte  short  int  long
浮点类型 double  float
字符类型 char 几乎不用
布尔类型 boolean

定义常量
final 数据类型 常量名称 = 值
常量一经赋值无法改变

Java的switch语句中表达式可以不为整型

数组
定义数组时中括号放在数据类型后，中括号中一般不写东西，且需要赋初值
静态初始化，大括号括起初值，用逗号隔开
动态初始化
int arr[] = new int[3];
二维数组很少使用

基本数据类型vs引用数据类型
基本数据类型的对象直接拥有内存，创建时就被划分了一块内存，数据直接存储在内存中
引用数据类型对象不直接拥有内存，其存储内存地址的引用，创建时首先在栈上给其引用分配一块内存，对象的具体信息都存储在堆内存上，由栈上引用指向堆内存
二者区别：
1.基本数据类型不包含其他对象及方法，引用数据类型包含其他属性和方法
2.基本数据类型直接操作变量，引用数据类型的操作一般都会用到包含的方法

java中方法只能定义在类中，称为类的成员方法

重载方法：同一类中名字相同方法不同的方法

什么是类，什么是对象
现实世界中具有相同属性和行为的物理实体的抽象
现实世界中某个具体的物理实体，有特定的属性和行为

属性私有，公开接口
一个Java源文件只能有一个共有类，且共有类名必须与源文件相同
在定义Java类时就已经分配了对象的所有属性成员（不包括方法）的内存

访问权限相关：
public：类内外都可被访问，对象名.成员
private：仅类内可以被访问，对象名.成员，在类外可被间接访问，对象名.公开方法()
类内：类的定义内部，准确来讲应该是类的所有成员方法内部
类外：类的外部

构造方法用来初始化一个对象，名称与类名相同
public Student(String aname,String ano,int ascore){
		no = ano;
		name = aname;
		score = ascore;
}
public Student(Student s){
		no = s.no;
		name = s.name;
		score = s.score;
}
使用new自动调用构造方法
this可以代替构造方法名字，在一种构造方法中调用已经存在的构造方法，但使用this的语句必须在构造方法的第一行

继承
单继承；final修饰的类不能有派生类
package使用避免命名冲突

一个派生类对象可以看作一个基类对象
1.可以调用基类继承的方法
2.不能调用派生类新增方法
3.派生类中重写的方法可以调用（重写方法需要原型相同）
Student s0 = new CollegeStudent(); //向上转型，将派生类对象赋给基类的引用
s0.setName("li"); //基类对象中的方法，可以调用
s0.getName();
s0.getMajor(); //报错，派生类新增方法，不可调用
s0.print(); //派生类中重写方法，可以调用

一个类只能有一个类，但是可以实现多个接口，要实现接口中所有抽象方法
抽象类不能实例化对象，但可以创建对它的引用
Animal a = new Dog();

Object o = new Student();
o = new Dog();
o = new CollegeStudent();
o可以调用Object类的属性方法，不能调用派生类新增属性方法，可以调用派生类重写的方法

重写equals方法
public boolean equals(Object obj){
		Student s = (Student)obj;
		if(name.equals(s.name) &amp;&amp; no.equals(s.no) &amp;&amp; this.score == score)
				return ture;
		return true;
}
</code></pre>


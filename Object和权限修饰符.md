# C-Sharp
## Object的由来
对于Object的由来，我们可以先写下如下代码：
```c#
//父类
class Fu    
{
   //父类无参构造函数
  public Fu()  
  {
    Console.WriteLine("Fu");
  }
}
//子类继承父类
class Zi : Fu
{
  //子类无参构造函数
  public Zi()
  {
    Console.WriteLine("Zi");
  }
}

class Demo
{
  static void Main(string[] args)
  {
    //创建子类对象，结果是先打印“Fu”然后是“Zi”。也就是说，创建子类对象会默认先调用父类无参构造函数，然后再调用子类无参构造函数。
    new Zi();
  }
}

//也就是说，子类无参构造函数可以显式写为：
public Zi() : base(){}    //默认先调用父类无参构造函数
```
实际上，我们随便创建一个类，即使里面什么都不写，默认也是会有内容的：
```c#
//普通类虽然没有写继承，但默认也要继承一个C#提供的类叫Object
class A : Object
{
  public A() : base(){}   //默认调用父类Object的无参构造函数
}
```
那么Object到底是怎么回事呢？我们知道C#语言为面向对象语言，也就是“万物皆对象”。C#的设计者认为，所有的对象都有或多或少的共性，那么把这些对象的共性不断的向上抽取（继承），最终会形成一个类，而这个类拥有所有对象的共性，便形成了Object类。Object本身就是对象的意思。简言之，我们写的任何类，如果没有继承任何类，那么会默认继承自Object类。Object类是C#为我们已经写好的一个基类，也是C#语言中所有类的直接或间接的基类，所以，C#中其他任何类和我们自定义的类都是Object的子类。

## Object的内容

既然Object类中有着所有对象的共性，那么我们应该知道Object中到底有哪些内容。

构造函数：Object中只有一个无参构造函数。我们都知道构造函数的作用是初始化对象，Object的构造函数也不例外。其实上例A类中的构造函数就是在调用Object的构造函数。

普通函数：Object中一共有8个函数，有两个特殊的不需要考虑，两个静态的可以直接通过类名调用，剩下4个都是可以被Object的子类继承并重写的，这4个包括：
```c#
Equals(Object)  确定指定的对象是否等于当前对象。
GetHashCode()   作为默认哈希函数。
GetType()       获取当前实例的 Type（类型）
ToString()      返回表示当前对象的字符串
```
常用方法示例：
```c#
class Program {
  static void Main(string[] args) {
    Person p1 = new Person(20);//创建Person类对象
    Person p2 = new Person(20);

   

    bool b1 = p1.Equals(p2);//比较的是地址值
    Console.WriteLine(b1);
	
    Person p3 = p2;
    Console.WriteLine(p3 == p2);//无论比较年龄还是地址，都相等。
	
    Console.WriteLine("----------");

    Console.WriteLine(Object.Equals(p1, p2));

    //GetHashCode()，可以获取当前对象的哈希值，哈希值是根据哈希算法得来。
    Console.WriteLine(p1.GetHashCode());

    //GetType获取当前对象的类型
    Console.WriteLine(p1.GetType());

    //ToString方法
    Console.WriteLine(p1.ToString());
  }
}

class Person {
  public int age;

  public Person(int age) {
    this.age = age;
  }
  //重写Object类的方法
  public override bool Equals(object obj) {
    //return base.Equals(obj);默认还是调用父类的
    Person p = (Person)obj;//强制转换
    return this.age == p.age;//比较年龄
  }
}
```
其实，我们随便定义一个类并创建这个类的对象，通过对象完全可以把这4个方法调用出来，也就是说，我们写的类都是继承自Object，并且可以把继承下来的方法进行重写或直接调用。


## 权限修饰符的作用
权限修饰符（做访问修饰符）说明了面向对象的封装性，它们代表访问权限，我们需要对不同的数据加上合适的权限来限制外界的访问。

C#中权限修饰符分为4种，分别为：
* public
* private
* protected
* internal
## public
公有的，公共的。代表权限最大，是类及类的成员修饰符。被public修饰的类或成员可以在任何地方被访问到。

## private
私有的。代表权限最小，是类的成员修饰符。被private修饰的成员只可以在本类中被访问到。

## protected
受保护的。类的成员修饰符。被protected修饰的成员只能被该类的子类访问。

## internal
内部的。类及类的成员修饰符。一般用来修饰类，被internal修饰的内容只能在本项目中被访问到，无法跨项目访问。

**注意，能修饰类的只有public和internal，如果一个类没有写修饰符，那么默认是internal。**

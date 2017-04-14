# C-Sharp

## C#运算符概述及分类
我们之前说过，C#程序的运行离不开运算。进一步讲，运算肯定又离不开运算符，因为只有运算符我们才知道应该如何去进行运算。在C#中存在很多种运算符，为了方便大家记忆和使用，我们对C#的运算符进行了归类划分。在C#中的运算符大概可以分为以下几类：
* 算数运算符
* 赋值运算符
* 比较运算符
* 逻辑运算符
* 三元运算符
* 位运算符

## 算数运算符
算数运算符主要的作用是对一些数值进行基本运算，其实我们已经接触过不少了。C#中的算数运算符包括：
![](http://nts.newbieol.com/static/k30/unity_csharp/5,%E8%BF%90%E7%AE%97%E7%AC%A6/images/1.png)

**加号还有另外的功能叫字符串连接符，可以将两个字符串或者一个字符串和数据链接成为一个更大的字符串**
* % 模是得到两个数值做除法运算后的余数，举例：
```c#
class Demo
{
  public static void Main(string[] args)
  {
    System.Console.WriteLine(5 % 2); //商2余1
  	System.Console.WriteLine(2 % 5); //商0余2
  	//任何数模2，结果不是0就是1*/
  }
}
```
* ++ 自增是在原有数据基础上加1后再赋值给原有数据，符号放到数据的前后都可。
```c#
class Demo
{
  public static void Main(string[] args)
  {
    int a = 2;
  	//a++;  
  	//++a;	      // a = a + 1;对于只有自增运算的表达式来说，自增符号放到前边和后边是一样的。
  	//System.Console.WriteLine(a);    直接打印a是自增以后的值。
  	//int b = a++;      	//运算的优先级，当自增运算符在后面的时候，先取值再+1，b是2
  	int b = ++a;       //自增符号在前面，先加1，在赋值。b是3
  	System.Console.WriteLine(b);
    int a = 3
    int b = (a++) + (a++) + (++a) ;      //  a++ 自身进行了自加，但是在赋值的时候是自加之前的值，++a是赋予自加之后的值 b = 13
  }
}
```
用c#进行代数运算
```c#
static void Main(string[] args)
{
  double x, y;
  System.Console.Write("x = ");       //命令行提示输出x值
  x = System.Convert.ToDouble(System.Console.ReadLine());   // 读取自变量x 的值 将输入的字符串转换为double类型
  y = x*x*x + 3*x*x - 24*x + 30;        //  计算y的值
  System.Console.WriteLine("y = " + y);      //输出y的值
}
```

除了算数运算符，C#还提供了大量数学函数，这些数学函数归为一类，称为**Math**类，如图所示

![](http://i2.muimg.com/1949/084e5382c0d01b66.png)

另外，Math类中还定义了两个常量，如下图

![](http://i2.muimg.com/1949/d0fa784c723590f0.png)

##  比较运算符
比较运算符的作用是用于比较两边数据的大小及相等，包括以下：

![](http://nts.newbieol.com/static/k30/unity_csharp/5,%E8%BF%90%E7%AE%97%E7%AC%A6/images/3.png)

```c#
class Demo
{
  public static void Main(string[] args)
  {
	System.Console.WriteLine(3 > 4);
	System.Console.WriteLine(3 < 4);
	System.Console.WriteLine(3 == 4);
	System.Console.WriteLine(3 >= 4);
	System.Console.WriteLine(4 <= 4);
  }
}
输出结果依次为：False 、True 、False 、False 、True
```
对于比较运算符，我们发现最后的结果要么是’是’，要么是’否’，在C#中我们用布尔类型的值来表示’是’、‘否’，即’是’可以用true表示，‘否’可以用false表示。所以，通过比较运算符运算后得到的结果一定是布尔值（bool）。

##  逻辑运算符
逻辑运算符是用来连接两个布尔值（或结果是布尔值的表达式）的，它可以将两个布尔值进行运算。逻辑运算符包含以下：

![](http://nts.newbieol.com/static/k30/unity_csharp/5,%E8%BF%90%E7%AE%97%E7%AC%A6/images/4.png)

```c#
class Demo
{
  public static void Main(string[] args)
  {
  	int x = 4;
	  System.Console.WriteLine(x > 3 & x < 5);//true
	  System.Console.WriteLine(x < 3 & x < 5);//false
	  System.Console.WriteLine(x < 3 & x > 5);//false

	  //System.Console.WriteLine(true & false);这样写也可以

	  //逻辑或运算按照上面的格式自己举例总结。

	  System.Console.WriteLine(!!true);
  }
}
```

```
表达式1    表达式2    &(&&)    |(||)   
ture      ture       ture     ture    
ture      flase      flase    ture
flase     ture       flase    ture
flase     flase      flase    flase
```
要注意 &和&&、|和||的区别：&&运算符进行运算时，如果运算符左边为false，那么右边无论是true还是false都不予计算，直接得出结果为false.
||运算符进行运算时，如果运算符左边true，那么右边无论是true还是false都不予计算，直接得出结果为true。以上效果都可以叫做短路效果。

## 三元运算符
三元运算符又可以叫三目运算符，表示三个元素参与运算的符号。三元运算符只有一种。

![](http://nts.newbieol.com/static/k30/unity_csharp/5,%E8%BF%90%E7%AE%97%E7%AC%A6/images/5.png)

三元运算符的使用格式：条件表达式 ? 数据1 : 数据2

```c#
class OpeDemo5
{
  public static void Main(string[] args)
  {
	//int a = (3 > 4) ? 100 : 200; //冒号两边可以是具体数据
	//System.Console.WriteLine(a);//结果为200

	bool a = 3 > 4 ? (3 > 4) : 3 < 4;//冒号两边可以是表达式，但要明确表达式结果的类型
	System.Console.WriteLine(a);//结果为true
  }
}
```
使用三元运算求出三个数的最大值

```c#
class Practice4
{
	static void Main(string[] args)
	{
		int a = 3, b = 4, c = 5;
		
		int max = (a > b)?((a > c)? a : c):((b > c)? b : c); //先用a 和b 做比较 然后用大的分别去和c做比较，求出最大值
		System.Console.WriteLine("max = "+ max);
	}
}
```

## 位运算符

位运算符主要是针对于二进制进行运算的，主要包括以下几种：

![](http://nts.newbieol.com/static/k30/unity_csharp/5,%E8%BF%90%E7%AE%97%E7%AC%A6/images/6.png)

```
3 << 2  = 12   //3 的二进制为 00000011， 将11向前移动两个字符变为00001100 翻译过来为12
3 >> 1  = 1    //3 的二进制为 00000011 ， 将11向后移动一个字符变为00000001（超出的字符被省略） 变成十进制为1
6 & 3  = 2    // 6的二进制为 00000110，3的二进制为00000011，将 00000110
                                                             00000011
                                                           --------------
                                                             00000010
                  取与，所以得出结果为00000010 变成十进制为2
6 | 3 = 7      //和& 一样转换为二进制然后对每一位取或，
6 ^ 3 = 5     // 将两个数转换为二进制，然后对应每一位的数做比较，两个数相等取0，不同取1，
~6 = -7        //将6转换为二进制，然后对每个数进行取反，然后转换十进制   每个位数的首位为正负运算符。
```



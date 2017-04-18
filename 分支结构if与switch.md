# C-Sharp

## if语句的三种格式（判断结构）
if语句是分支结构中的一种，也可以叫做判断结构。它包含三种格式，分别为：
第一种格式：
```c#
if(条件表达式)
{
  执行语句;
}
```
```c#
class IfDemo
{
  public static void Main(string[] args)
  {
    int a = 3;
    if(a < 4)
    {
      System.Console.WriteLine("ok");
    }
    System.Console.WriteLine("ole");
  }
}
结果为ok  ole
```
第二种格式：
```c#
if(条件表达式)
{
  执行语句;
}
else
{
  执行语句;
}
```
```c#
class IfDemo
{
  public static void Main(string[] args)
  {
    int a = 3;

    if(a > 4)
    {
      System.Console.WriteLine("ok");
    }
    else
    {
      System.Console.WriteLine("hello");
    }
    System.Console.WriteLine("ole");
    结果为hello ole
  }
}
```
在第二种格式中，无论条件表达式的结果是什么，那么至少会有一条语句被执行。

第三种格式：
```c#
if(条件表达式)
{
  执行语句;
}
else if(条件表达式)
{
  执行语句；
}
.
.
else
{
  执行语句；
}
```
```c#
class IfDemo
{
  public static void Main(string[] args)
  {
    int a = 3;

    if(a > 1)
    {
      System.Console.WriteLine("A");
    }
    else if(a > 2)
    {
      System.Console.WriteLine("B");
    }
    else if(a > 3)
    {
      System.Console.WriteLine("C");
    }
    else
    {
      System.Console.WriteLine("D");
    }
  }
}

结果为A
```

## switch..case语句（选择结构）
C#中还有另外一种分支结构叫switch..case语句，我们也可以管它叫做选择结构。如果可以把if语句理解成判断题，那么switch..case语句就可以理解成为选择题。它的格式如下：
```c#
switch(表达式)
{
  case 取值1:
    执行语句;
    break;
  case 取值2:
    执行语句;
    break;
  .
  .
  default:
    执行语句;
    break;
}
```
举例：
```c#
class SwitchDemo
{
  public static void Main(string[] args)
  {
    int x = 3;
 
    switch(x)
    {
      case 5:
        System.Console.WriteLine("A");
        break;
      case 3:
        System.Console.WriteLine("B");
        break;
      case 10:
        System.Console.WriteLine("C");
        break;
      default:                               // default这一条所在的位置对结果没有影响，一般情况最好写上
        System.Console.WriteLine("D");
        break;                                // 每一个case语句后面必须跟break，否则会报错
    }
  }
}
结果为B
```
### 货物托运运费问题
```c#
/*托运计费问题：
当货物重量小于20 公斤的时候，收费5 元，
大于20 公斤小于100 公斤的时候超出20 公斤的部分按每0.2 元每公斤计费，
如果超出100 公斤的时候，超出的部分按照每公斤0.15 元计算。
读入货物的重量，输出计算之后货物的运费。
*/
class If2
{
	static void Main(string[] args)
	{
		System.Console.Write("请输入货物重量：");
		int a = System.Convert.ToInt32(System.Console.ReadLine());
		if(a > 0 && a <= 20)
		{
			System.Console.WriteLine("收费5元");
		}
		else if(a > 20 && a <= 100)
		{
			int b;
			b = a - 20;                  //b 为超出20公斤的部分
			System.Console.WriteLine("收费{0}元", 0.20*b+5);  // 因为b为int型 与0.2做运算转为浮点型
		}
		else if(a > 100)
		{
			int c;
			c = a - 100;
			System.Console.WriteLine("收费{0}元", 21+0.15*c);
		}
	}
}
```

### 将输入的数进行从大到小排序
```c#
//将三个数进行排序，先用a和b比较。将大的数放入a中，然后用a和c比较，将大的放入a，然后b和c比较，将大的放入b中
class If4
{
	static void Main(string[] args)
	{
		System.Console.WriteLine("请依次输入三个实数：");
		double a = System.Convert.ToDouble(System.Console.ReadLine());
		double b = System.Convert.ToDouble(System.Console.ReadLine());
		double c = System.Convert.ToDouble(System.Console.ReadLine());
		double temp;
		if(a < b)
		{
			temp = a;              //利用一个空的变量temp交换a和b的值
			a = b;
			b = temp;
		}
		if(a < c)
		{
			temp = a;
			a = c;
			c = temp;
		}
		if(b < c)
		{
			temp = b;
			b = c;
			c = temp;
		}
		System.Console.WriteLine("{0} > {1} > {2}", a, b, c);
	}
}
```

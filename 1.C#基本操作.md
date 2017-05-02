
## C#语言简介

* C# 是一个现代的、通用的、面向对象的编程语言，它是由微软（Microsoft）开发的，由 Ecma 和 ISO 核准认可的。
* C# 是由 Anders Hejlsberg 和他的团队在 .Net 框架开发期间开发的。
* C# 是专为公共语言基础结构（CLI）设计的。CLI 由可执行代码和运行时环境组成，允许在不同的计算机平台和体系结构上使用各种高级语言。

### C#成为广泛应用的专业语言的原因

* 现代的、通用的编程语言。
* 面向对象。
* 面向组件。
* 容易学习。
* 结构化语言。
* 它产生高效率的程序。
* 它可以在多种计算机平台上编译。
* .Net 框架的一部分。

## 人与计算机的交互方式

人与计算机的交互有两种方式分别是：
* 图形化界面(Graphical User Interface GUI) : 简单直观容易接受，容易上手操作。
* 命令行方式(Command Line Interface CLI) : 需要有控制台，输入特定指令让计算机完成操作。麻烦，需要记住命令。

## C#运行环境简介

在Windows中，C#的运行环境存在于 C:\Windows\Microsoft.NET 下。其中，C# 的语言编译器存在于 C:\Windows\Microsoft.NET\Framework64\v4.0.30319（或v3.5）中。C# 的语言编译器为csc.exe这个文件，我们可以在dos命令行中打开这个文件对C# 原文件进行编译。

## 环境变量的配置

环境变量可以帮助我们在任何目录下都能够使用dos来调用C#的编译器，省去了输入深层次目录的烦恼。

环境变量的配置：
右键“我的电脑” -> 属性 -> 高级系统设置 -> 环境变量 -> 系统变量 -> Path

我们只需要把文件所在的目录粘贴到变量值里面就可以，注意和其他路径分开。（将编译器csc.exe所在目录路径复制到Path中，注意用分号隔开）

## 常用dos命令

dir 列出当前目录下的文件和文件夹 directory目录
md 创建目录 make directory
cd 进入指定目录 change directory
cd.. 退回到上一级目录
cd\ 直接回到根目录
rd 删除目录 remove directory
del 删除文件
exit 退出dos命令行
help 寻求帮助
ipconfig 获取当前主机的ip

## 类的简单介绍

一个 C# 程序主要包括以下部分：
* 命名空间声明（Namespace declaration）
* class (类)
* Main 函数
* 字段(或变量)
* 属性
* 函数
* 语句（Statements）& 表达式（Expressions）
* 注释

## C# Hello World实例

C#代码是以'类'的形式去体现的。类：可以简单理解为装C#代码的地方，类是C#代码中最根本的结构。
让我们看一个可以打印出 “Hello World” 的简单的代码：
```sh
class HelloWorld
{
  static void Main(string[] args)
  {
    /*我的第一个C#程序 */
     System.Console.WriteLine("Hello World");
  }
}
```
注意事项：
* Main方法是程序的入口点，保证程序的独立运行。一个C#程序必须要有Main方法，没有就报错。
* 写代码时必须要注意格式的缩进以及大小写。
* 不能以查单词的形式去理解代码。
* 注意符号的过多或缺失或格式。
* 什么时候该使用大括号，什么时候该使用分号。结构性的语句写大括号，单独一句话的写分号。
* 注意文件后缀名选项不要选。

## 关键字

* 定义：被C#语言赋予了特殊含义的单词，C#中共有近100个关键字
* 举例：class(表示一个类的创建)，static，void
* 关键字在C#中都是小写的。

## 标识符

* 标识符的定义：程序中自定义的名字。
* 标识符的使用：
  * 标识符的组成：26个英文字母大小写、0-9数字以及下划线组成
  * 注意事项：不能使用C#中的关键字，数字不能开头
  * 标识符规范：单词首字母大写，要起有意义的标识符

## 注释的运用

注释：注解、说明程序的文字。

注释的出现为我们提供了良好的编写代码的规范，也使得我们的程序更加具备可读性。

C#中常用的注释分为两种：单行注释和多行注释
* 单行注释，只能注释到一行的回车处。
举例： // 注释文字

* 多行注释，可以对多行文字进行注释。
举例:
```sh
/*
需要注释
修改的程序
*/
```

## 基本输入、输出函数
C#为我们提供了很多常用的功能，接下来为大家介绍目前比较常用的两个：输入和输出函数
```sh
输出函数（System.Console.WriteLine()、System.Console.Write()）可以在控制台输出我们指定的数据：
class HelloWorld
{
   static void Main(string[] args)
   {
    System.Console.Write("Hello World");    //不换行，括号内不能为空
	  System.Console.WriteLine("Hello World");  //自带换行效果，括号可以为空输出一个空行
	  System.Console.Write("Hello World");
   }
}
输入函数（Console.ReadLine()）可以在控制台中读取键盘上的按键：
class HelloWorld
{
   static void Main(string[] args)
   {
      System.Console.ReadLine(); //读取键盘输入
   }
}
执行到“Console.ReadLine();”后控制台会停在这里等待我们在键盘输入。输入完毕后需要按一下回车表示
输入完毕。完成后没有任何效果，后续我们会对这个函数有更多的使用和理解。
```

## 我第一个C# 程序
```sh
class Hello
{
  static void Main(string[] args)
  {
    System.Console.WriteLine("hello world");
  }
}
```

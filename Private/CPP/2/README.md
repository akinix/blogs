# 开始学习 C++

## 进入 C++

案例（如下图）：

![image](http://shadows-mall.oss-cn-shenzhen.aliyuncs.com/images/assets/cpp/3.png)

![image](http://shadows-mall.oss-cn-shenzhen.aliyuncs.com/images/assets/cpp/4.png)

通常，C++ 程序必须包含一个名为 `main()` 的函数。

### C++ 预处理器和 iostream 文件

```cpp
#include <iostream>
```

该编译指令导致预处理器将 `iostream` 文件的内容添加到程序中。这是一种典型的预处理器操作：在源代码被编译之前，替换或添加文本。`iostream` 文件的内容将取代程序中的代码行 `#include <iostream>`。

> 注意：使用 `cin` 和 `count` 进行输入和输出的程序必须包含文件 `iostream`。

### 头文件名

像 `iostream` 这样的文件叫做包含文件（include file） —— 由于它们被包含在其他文件中；也叫头文件（header file） —— 由于它们被包含在文件起始处。

C++ 编译器自带了很多头文件，每个头文件都支持一组特定的工具。C 语言的传统是，头文件使用扩展名 h，将其作为一种名称标识文件类型的简单方式。例如，头文件 `math.h` 支持各种 C 语言数学函数，但 C++ 的用法变了。现在，对老式 C 的头文件保留了扩展名 h（C++ 程序仍可以使用这种文件），而 C++ 头文件则没有扩展名。

![image](http://shadows-mall.oss-cn-shenzhen.aliyuncs.com/images/assets/cpp/5.png)

### 名称空间

如果使用 `iostream`，而不是 `iostream.h`，则需要通过名称空间编译指令 `using namespace std` 来使 `iostream` 对程序可用。

使用 `using namespace std` 可以让 `iostream` 的代码不需要带 `std` 前缀。而更好的方法是，通过 `using` 声明来使所需的名称可用：

```cpp
using std::cout;
using std::endl;
using std::cin;
```

### 使用 cout 进行 C++ 输出

从概念上看，输出是一个流，即从程序流出的一系列字符。`cout` 的对象属性包括一个插入运算符（<<），它可以将右侧的信息插入到流中。它将字符串插入到输出流中。因此，与其说程序显示了一条消息，不如说它将一个字符串插入到了输出流中（如下图）。

![image](http://shadows-mall.oss-cn-shenzhen.aliyuncs.com/images/assets/cpp/6.png)

### 类简介

类描述了一种数据类型的全部属性（包括可使用它执行的操作），对象是根据这些描述创建的实体。

## 函数

在使用函数之前，C++ 编译器必须知道函数的参数类型和返回值类型。C++ 提供这种信息的方式是使用函数原型语句。原型结尾的分号代表它是一条语句，这使得它是一个原型，而不是函数头（如下）。

```cpp
double sqrt(double);
```

`C++ 程序应当为程序中使用的每个函数提供原型。`

### 用户定义的函数

对于库函数，在使用之前必须提供其原型，通常把原型放到 `main()` 定义之前。但是自己的定义的函数必须提供新函数的源代码，通常放在 `main()` 函数的后面。

C++ 不允许将函数定义嵌套在另一个函数定义中。每个函数定义都是独立的，所有函数的创建都是平等的。

可以将计算机操作系统（Unix 或 Windows）看作调用程序。因此 `main()` 的返回值并不是返回程序的其他部分，而是返回操作系统。通常的约定是，退出值（返回值）为 0 则意味着程序运行成功，为非零则意味着存在问题。

函数原型描述了函数接口，即函数如何与程序的其他部分交互。参数列表指出了何种信息将被传递给函数，函数类型指出了返回值的类型。程序员有时将函数比作一个由出入它们的信息所指定的黑盒子（black boxes）（如下图）。

![image](http://shadows-mall.oss-cn-shenzhen.aliyuncs.com/images/assets/cpp/7.png)

## 总结

C++ 程序由一个或多个被称为函数的模块组成。程序从 `main()` 函数（全部小写）开始执行，因此该函数必不可少。函数由函数头和函数体组成。函数头指出函数的返回值（如果有的话）的类型和函数期望通过参数传递给它的信息的类型。函数体由一系列位于花括号（{}）中的 C++ 语句组成。

有多种类型的 C++ 语句，包括下述 6 种。

  - 声明语句：定义函数中使用的变量的名称和类型。
  - 赋值语句：使用赋值运算符（=）给变量赋值。
  - 消息语句：将消息发送给对象，激发某种行动。
  - 函数调用：执行函数。被调用的函数执行完毕后，程序返回到函数调用语句后面的语句。
  - 函数原型：声明函数的返回类型、函数接受的参数数量和类型。
  - 返回语句：将一个值从被调用的函数那里返回到调用函数中。

类是用户定义的数据类型规范，它详细描述了如何表示信息以及可对数据执行的操作。对象是根据类规范创建的实体，就像简单变量是根据数据类型描述创建的实体一样。

C++ 提供了两个用于处理输入和输出的预定义对象（`cin` 和 `cout`），它们是 `istream` 和 `ostream` 类的实例，这两个类是在 `iostream` 文件中定义的。为 `ostream` 类定义的插入运算符 `<<` 使得数据插入到输出流成为可能；为 `istream` 类定义的抽取运算符 `>>` 能够从输入流中抽取信息。`cin` 和 `cout` 都是智能对象，能够根据程序上下文自动将信息从一种形式转换为另一种形式。

C++ 可以使用大量的 C 库函数。要使用库函数，应当包含提供该函数原型的头文件。

# Introduction | 介绍

C# (pronounced "See Sharp") is a simple, modern, object-oriented, and type-safe programming language. C# has its roots in the C family of languages and will be immediately familiar to C, C++, and Java programmers. C# is standardized by ECMA International as the ***ECMA-334*** standard and by ISO/IEC as the ***ISO/IEC 23270*** standard. Microsoft's C# compiler for the .NET Framework is a conforming implementation of both of these standards.

C#（读作“See Sharp”）是一门简单、现代、面向对象且类型安全的编程语言。C#植根于C系语言家族，可以被C、C++和Java程序员迅速掌握。C#被ECMA International标准化为**ECMA-334**标准；被ISO/IEC标准化为**ISO/IEC 23270**标准。微软的C#编译器如实地实现了这两个标准。

<!--
1. 广告做的不错！2. 直译“微软的C#编译器是符合这两个标准的一个实现”——过于欧化。3. 标准化还是很厉害的，比Java目光长远。
-->

C# is an object-oriented language, but C# further includes support for ***component-oriented*** programming. Contemporary software design increasingly relies on software components in the form of self-contained and self-describing packages of functionality. Key to such components is that they present a programming model with properties, methods, and events; they have attributes that provide declarative information about the component; and they incorporate their own documentation. C# provides language constructs to directly support these concepts, making C# a very natural language in which to create and use software components.

C#是面向对象的语言，但C#还进一步支持**面向组件**（component-oriented）编程。当今的软件设计越来越多地依赖在以自包含（self-contained）和自描述（self-describing）的功能包为形式的软件组件上。这些组件的关键之处在于，它们能够以属性（properties）、方法（methods）和事件（events）来呈现一个编程模型（programming model）；它们拥有用来提供与组件相关的声明性信息的特征（attributes）；并且它们还能囊括自己的文档???。C#提供了用以直接支持这些概念的语言结构，所以，C#是一门在创建和使用软件组件方面十分自然的语言。

<!--1. Contemporary，当今的。2. in the form of，以...的形式。3. 当今的软件设计越来越多地依赖软件组件，所谓“组件”，就是以自包含（self-contained）和自描述（self-describing）的功能包。4. present，呈现，表达，表示。5. 从单复数上来看，表示的意思应该是“一个编程模型是由多个组件构成的”，而且，一个组件看起来有点像一个类。或者说，C#中的类就是一个组件，是相对于其他编程语言中的类的升级品。6. incorporate???，包括？不好译。-->

Several C# features aid in the construction of robust and durable applications: ***Garbage collection*** automatically reclaims memory occupied by unused objects; ***exception handling*** provides a structured and extensible approach to error detection and recovery; and the ***type-safe*** design of the language makes it impossible to read from uninitialized variables, to index arrays beyond their bounds, or to perform unchecked type casts.

C#的一些功能有助于构建健壮和耐久的应用程序：*垃圾收集*（garbage collection）会自动回收那些被闲置对象所占用的内存；*异常处理*（exception handling）提供了一个结构化、可扩展的方式用来探测错误并从错误中恢复；*类型安全*（type-safe）这项语言设计使得我们不可能访问未初始化的变量或者访问超出数组边界的索引，也不可能进行不经检验的类型转换。

<!--1. unused，未被使用的==闲置的。2. 这个it经常不太好直译。3. cast里面有不少“文化意味”的。-->

C# has a ***unified type system***. All C# types, including primitive types such as `int` and `double`, inherit from a single root `object` type. Thus, all types share a set of common operations, and values of any type can be stored, transported, and operated upon in a consistent manner. Furthermore, C# supports both user-defined reference types and value types, allowing dynamic allocation of objects as well as in-line storage of lightweight structures.

C#拥有**统一类型系统**（unified type system）。所有C#的类型，包括诸如`int`和`double`等原始类型（primitive types），都继承自单一的根——`object`类型。因此，所有类型都会享有一组共同的操作，以致于任何类型的值都可以以一种一致的方式来存储、传输和操作。此外，C#还支持用户定义的引用类型（reference types）和值类型（value types）——既允许动态地分配对象，也允许轻量级结构体的就地（in-line）存储???。

<!--1. type，类型，口述的时候可以说“数据类型”，译的时候还是不要乱讲的好。2. 人家Java中的int和double才叫“原始”，C#里的已经太高级了好不好……这明显是带有广告意味。3. manner，方式，比较口语化的一个词。4. in-line，就地。5. 最后一句原文啥意思？得去跟作者确认……-->

To ensure that C# programs and libraries can evolve over time in a compatible manner, much emphasis has been placed on ***versioning*** in C#'s design. Many programming languages pay little attention to this issue, and, as a result, programs written in those languages break more often than necessary when newer versions of dependent libraries are introduced. Aspects of C#'s design that were directly influenced by versioning considerations include the separate `virtual` and `override` modifiers, the rules for method overload resolution, and support for explicit interface member declarations.

为了保证C#的程序和库在随着时间不断进化的同时仍然能够保持向前兼容，C#的设计在*版本控制*（versioning）方面可谓下足了工夫。许多编程语言在这一点上并不很在意，所以，作为结果，当引入由语言的新版本所编写的依赖库时，程序就会遇到更多的、本不必要的问题。对版本控制的考虑直接影响了C#语言设计的诸多方面，包括将`virtual`和`override`修饰符分离、方法重载的解析规则、和显式的接口成员声明。

<!--1. "为了保证C#程序和库能够以兼容的方式随着时间不断进化，"译法生硬。2. "将`virtual`和`override`修饰符分离"这话明显是冲着Java来的。3. 一时还理解不了这与版本有什么关系。-->

The rest of this chapter describes the essential features of the C# language. Although later chapters describe rules and exceptions in a detail-oriented and sometimes mathematical manner, this chapter strives for clarity and brevity at the expense of completeness. The intent is to provide the reader with an introduction to the language that will facilitate the writing of early programs and the reading of later chapters.

本章的剩余部分将会描述C#语言那些最根本的功能。尽管后面的章节会（针对这些功能）在规则和特例方面进行细致入微的阐述，有些时候还会引入数学的方式，本章则（以牺牲一定的细节作为代价）以清晰而简明的方式力保（对C#语言介绍的）完整性。

<!--反正也不是用来出版的，我就照顾语义通顺吧！文章是给人用来读和理解的。怕挨骂就不要做翻译好了。-->

## Hello world | Hello World

The "Hello, World" program is traditionally used to introduce a programming language. Here it is in C#:

“Hello, World”程序一直以来就被用来介绍编程语言。这里是它的C#版本：

```csharp
using System;

class Hello
{
    static void Main() {
        Console.WriteLine("Hello, World");
    }
}
```

```csharp
using System;

class Hello
{
    static void Main() {
        Console.WriteLine("Hello, World");
    }
}
```

C# source files typically have the file extension `.cs`. Assuming that the "Hello, World" program is stored in the file `hello.cs`, the program can be compiled with the Microsoft C# compiler using the command line
```
csc hello.cs
```
which produces an executable assembly named `hello.exe`. The output produced by this application when it is run is
```
Hello, World
```

C#的源文件（source files）一般都会使用`.cs`作为文件的扩展名。假设这个“Hello, World”程序被存储在名为`hello.cs`的文件中，那么这个程序可以被微软的C#编译器以如下命令进行编译：
```
csc hello.cs
```
并产生一个名为`hello.exe`的可执行的程序集（assembly）。当我们运行这个应用程序的时候，它产生的输出是：
```
Hello, World
```

<!--从上下文中可以清楚地看出，program指的是“代码阶段的程序”，而application指的是编译后、可执行的“应用程序”。-->

The "Hello, World" program starts with a `using` directive that references the `System` namespace. Namespaces provide a hierarchical means of organizing C# programs and libraries. Namespaces contain types and other namespaces—for example, the `System` namespace contains a number of types, such as the `Console` class referenced in the program, and a number of other namespaces, such as `IO` and `Collections`. A `using` directive that references a given namespace enables unqualified use of the types that are members of that namespace. Because of the `using` directive, the program can use `Console.WriteLine` as shorthand for `System.Console.WriteLine`.

“Hello, World”程序以`using`指令开头，这个指令引用了`System`名称空间。名称空间（namespaces）提供了一种层级的方式来管理C#的程序和库。名称空间里可以包含类型和其他（子）名称空间。例如，`System`包含了许多类型（譬如程序中所引用的`Console`类）和许多（子）名称空间（譬如`IO`和`Collections`）。引用了给定名称空间的`using`指令使得这个名称空间中的类型可以以非限定（unqualified）的方式进行使用。举例而言，因为有了程序开头的`using`指令，原本的`System.Console.WriteLine`就可以以`Console.WriteLine`的简写方式来使用。

<!--1. 把namespace译为“名称空间”而不是“命名空间”是因为最早就接受了这种译法，改不了了！2.注意：一开头的using不是语句，而是“指令”，这个很多人没意识到。3. means，译为“手段”。例：by means of，以什么手段。4.shorthand，速记-->

The `Hello` class declared by the "Hello, World" program has a single member, the method named `Main`. The `Main` method is declared with the `static` modifier. While instance methods can reference a particular enclosing object instance using the keyword `this`, static methods operate without reference to a particular object. By convention, a static method named `Main` serves as the entry point of a program.

被“Hello, World”程序声明的`Hello`类拥有唯一的一个成员——名为`Main`的方法。`Main`方法被声明的时候带有`static`修饰符。静态方法（static methods）无需引用具体的对象就能运作，而实例方法（instance methods）可以使用`this`关键字来引用一个特定的、包含之的实例对象。按照约定，名为`Main`的静态方法将作为程序的入口点。

<!--1. 翻译完这段，我可以肯定地说：语言文档绝壁不是给新手读的——术语太多了，而这些术语要么已经被教过，要么已经在其他语言的学习中有所了解。2. this和static这段描述，英文原文有点儿烂。-->

The output of the program is produced by the `WriteLine` method of the `Console` class in the `System` namespace. This class is provided by the .NET Framework class libraries, which, by default, are automatically referenced by the Microsoft C# compiler. Note that C# itself does not have a separate runtime library. Instead, the .NET Framework is the runtime library of C#.

程序的输出由`System`名称空间中的`Console`类的`WriteLine`方法所产生。这个类由.NET Framework的类库所提供。.NET Framework类库会被微软C#编译器自动引用。注意，C#语言本身并没有独立的运行时库（???哪个语言有？）。取而代之的是，.NET Framework就是C#的运行时库。

<!--当还有没完全理解的描述时，说明自己还没有透彻理解C#这门语言。-->

## Program structure | 程序的结构

The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***. C# programs consist of one or more source files. Programs declare types, which contain members and can be organized into namespaces. Classes and interfaces are examples of types. Fields, methods, properties, and events are examples of members. When C# programs are compiled, they are physically packaged into assemblies. Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***.

C#语言与代码组织性相关的概念中，最关键的包括**程序**（programs）、**名称空间**（namespaces）、**类型**（types）、**成员**（members）和**程序集**（assemblies）。C#程序由一个或多个源文件（source files）构成。程序能够声明类型，类型可以包含成员，而且类型可以被组织进名称空间中。类型的例子有：类（classes）和接口（interfaces）。成员的例子有：字段（fieled）、方法（methods）、属性（properties）和事件（events）。C#的程序被编译之后，（编译结果）会被物理性地打包进程序集中。程序集一般都会以`.exe`或`.dll`作为文件扩展名。使用`.exe`还是`.dll`作为扩展名取决于（编译）是**应用程序**（applications）还是**库**（libraries）。

<!--1. "**程序**（programs）是C#组织性概念中的关键。"这么译，文档就废了。-->

The example

```csharp
using System;

namespace Acme.Collections
{
    public class Stack
    {
        Entry top;

        public void Push(object data) {
            top = new Entry(top, data);
        }

        public object Pop() {
            if (top == null) throw new InvalidOperationException();
            object result = top.data;
            top = top.next;
            return result;
        }

        class Entry
        {
            public Entry next;
            public object data;

            public Entry(Entry next, object data) {
                this.next = next;
                this.data = data;
            }
        }
    }
}
```
declares a class named `Stack` in a namespace called `Acme.Collections`. The fully qualified name of this class is `Acme.Collections.Stack`. The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`. The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor. Assuming that the source code of the example is stored in the file `acme.cs`, the command line

```
csc /t:library acme.cs
```
compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.

示例

```csharp
using System;

namespace Acme.Collections
{
    public class Stack
    {
        Entry top;

        public void Push(object data) {
            top = new Entry(top, data);
        }

        public object Pop() {
            if (top == null) throw new InvalidOperationException();
            object result = top.data;
            top = top.next;
            return result;
        }

        class Entry
        {
            public Entry next;
            public object data;

            public Entry(Entry next, object data) {
                this.next = next;
                this.data = data;
            }
        }
    }
}
```

在名为`Acme.Collections`的名称空间中声明了一个名为`Stack`的类。这个类的全限定名（fully qualified name）是`Acme.Collections.Stack`。这个类包含了若干个成员：一个名为`top`的字段，两个分别名为`Push`和`Pop`的方法，和一个名为`Entry`的嵌套类。进而，`Entry`类也包含自己的三个成员：一个名为`next`的字段，一个名为`data`的字段和一个构造器（constructor）。假设这个示例的源代码被存储在名为`acme.cs`的文件中，则命令行

```
csc /t:library acme.cs
```
会把示例代码编译为一个库（没有`Main`入口点的代码）并且产生一个名为`acme.dll`的程序集。

<!--1. "没有`Main`入口点的代码"这里明显有个误导，因为有`Main`方法的代码也可以被 /t:library 指令编译成库。-->

Assemblies contain executable code in the form of ***Intermediate Language*** (IL) instructions, and symbolic information in the form of ***metadata***. Before it is executed, the IL code in an assembly is automatically converted to processor-specific code by the Just-In-Time (JIT) compiler of .NET Common Language Runtime.

程序集中包含了以**中间代码**（Intermediate Language，简称 IL）形式的可执行代码和**元数据**（metadata）形式的描述性信息???。在程序集执行之前，中间语言代码会被.NET通用语言运行时（Common Language Runtime，简称CLR）中的即时（Just-In-Time，简称JIT）编译器自动转换为面向特定处理器的代码。

Because an assembly is a self-describing unit of functionality containing both code and metadata, there is no need for `#include` directives and header files in C#. The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program. For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:

```csharp
using System;
using Acme.Collections;

class Test
{
    static void Main() {
        Stack s = new Stack();
        s.Push(1);
        s.Push(10);
        s.Push(100);
        Console.WriteLine(s.Pop());
        Console.WriteLine(s.Pop());
        Console.WriteLine(s.Pop());
    }
}
```
If the program is stored in the file `test.cs`, when `test.cs` is compiled, the `acme.dll` assembly can be referenced using the compiler's `/r` option:

```
csc /r:acme.dll test.cs
```
This creates an executable assembly named `test.exe`, which, when run, produces the output:

```
100
10
1
```

因为程序集是一个既包含代码又包含元数据的、自描述的（self-describing）功能单元，所以C#不需要使用`#include`指令和头文件。对于指定的程序集，只要在编译程序的时候引用这个程序集，那么这个程序集当中的公开（public）类型和成员就能够被访问。例如，下面这个程序用到了`acme.dll`程序集中的`Acme.Collections.Stack`类：

```csharp
using System;
using Acme.Collections;

class Test
{
    static void Main() {
        Stack s = new Stack();
        s.Push(1);
        s.Push(10);
        s.Push(100);
        Console.WriteLine(s.Pop());
        Console.WriteLine(s.Pop());
        Console.WriteLine(s.Pop());
    }
}
```
假设程序被存储在文件`test.cs`中，那么当编译`test.cs`的时候，可以使用编译器的`/r`选项来引用`acme.dll`程序集：

```
csc /r:acme.dll test.cs
```
这样就会产生一个名为`test.exe`的可执行的程序集。当这个程序集运行的时候，就会产生输出：

```
100
10
1
```

C# permits the source text of a program to be stored in several source files. When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed. Forward declarations are never needed in C# because, with very few exceptions, declaration order is insignificant. C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.

C#允许程序的源文本（source text）存储在多个源文件中，而且这些源文件可以自由地互相引用。当一个多文件程序被编译的时候，所有源文件会被一起处理——概念上来说，就如同在编译前先把这些源文件连接成一个大文件，再进行处理。C#也从来不需要前置声明（forward declarations），因为声明顺序无关紧要（除了极少数例外情况）。C#既不限制一个源文件中只能声明一个公开类型，也不要求源文件必需与声明在其中的类型在名字上保持一致。

<!--快把人家C/C++和Java黑出翔来了……-->

## Types and variables | 类型与变量

There are two kinds of types in C#: ***value types*** and ***reference types***. Variables of value types directly contain their data whereas variables of reference types store references to their data, the latter being known as objects. With reference types, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable. With value types, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other (except in the case of `ref` and `out` parameter variables).

C#语言有两种类型——**值类型**（value types）和**引用类型**（reference types）。值类型的变量里直接容纳着数据，而引用类型的变量里则容纳的是对数据（也就是对象）的引用。当使用引用类型的时候，可以让两个变量引用同一个对象，这样，施加在一个变量上的操作就会影响到另一个变量所引用的对象。当使用值类型的时候，每个变量都拥有属于自己的一份对数据的拷贝，因此，也不可能发生操作一个变量会影响到另一个变量的情况（`ref`和`out`参数是例外）。

<!--1.其实应该译为“数据类型”，但有感觉画蛇添足。2.那么，值类型的“data”是不是对象？-->

C#'s value types are further divided into ***simple types***, ***enum types***, ***struct types***, and ***nullable types***, and C#'s reference types are further divided into ***class types***, ***interface types***, ***array types***, and ***delegate types***.

C#的值类型可以进一步细分为**简单类型**（simple types）、**枚举类型**（enum types）、**结构体类型**（struct types）和**可空类型**（nullable types）。C#的引用类型则可进一步细分为**类类型**（class types）、**接口类型**（interface types）、**数组类型**（array types）和**委托类型**（delegate types）。

<!--1.What??数组类型和委托类型难道不是类类型吗？我怀疑我翻译到了一份假的语言文档……-->

The following table provides an overview of C#'s type system.

| __Category__    |                 | __Description__ |
|-----------------|-----------------|-----------------|
| Value types     | Simple types    | Signed integral: `sbyte`, `short`, `int`, `long` |
|                 |                 | Unsigned integral: `byte`, `ushort`, `uint`, `ulong` |
|                 |                 | Unicode characters: `char` |
|                 |                 | IEEE floating point: `float`, `double` |
|                 |                 | High-precision decimal: `decimal` |
|                 |                 | Boolean: `bool` |
|                 | Enum types      | User-defined types of the form `enum E {...}` |
|                 | Struct types    | User-defined types of the form `struct S {...}` |
|                 | Nullable types  | Extensions of all other value types with a `null` value |
| Reference types | Class types     | Ultimate base class of all other types: `object` |
|                 |                 | Unicode strings: `string` |
|                 |                 | User-defined types of the form `class C {...}` |
|                 | Interface types | User-defined types of the form `interface I {...}` |
|                 | Array types     | Single- and multi-dimensional, for example, `int[]` and `int[,]` |
|                 | Delegate types  | User-defined types of the form e.g. `delegate int  D(...)` |

下表提供了一个对C#类型的概览。

| __类别__    |                 | __描述__ |
|-----------------|-----------------|-----------------|
| 值类型     | 简单类型   | 有符号整数： `sbyte`、 `short`、 `int`、 `long` |
|           |           | 无符号整数： `byte`、 `ushort`、 `uint`、 `ulong` |
|           |           | Unicode字符： `char` |
|           |           | IEEE浮点数： `float`、 `double` |
|           |           | 高精度十进制小数： `decimal` |
|           |           | 布林： `bool` |
|           | 枚举类型   | 用户自定义的`enum E {...}`形式 |
|           | 结构体类型 | 用户自定义的`struct S {...}`形式 |
|           | 可空类型   | 使用`null`值对其他所有值类型进行的扩展 |
| 引用类型   | 类类型     | 其他类型的终极基类： `object` |
|           |           | Unicode字符串： `string` |
|           |           | 用户自定义的`class C {...}`形式 |
|           | 接口类型   | 用户自定义的`interface I {...}`形式 |
|           | 数组类型   | 一维或多维，例如， `int[]` 和 `int[,]` |
|           | 委托类型   | 用户自定义的诸如`delegate int  D(...)`的形式 |

The eight integral types provide support for 8-bit, 16-bit, 32-bit, and 64-bit values in signed or unsigned form.

八种整数类型提供了对8位、16位、32位和64位有符号或无符号数值的支持（4×2=8）。

The two floating point types, `float` and `double`, are represented using the 32-bit single-precision and 64-bit double-precision IEEE 754 formats.

两种浮点数类型，`float`和`double`，分别以IEEE 754标准中的32位单精度和64位双精度格式来表式。

The `decimal` type is a 128-bit data type suitable for financial and monetary calculations.

`decimal`类型是一种128位的数据类型，适用于金融和货币运算。

C#'s `bool` type is used to represent boolean values—values that are either `true` or `false`.

C#的`bool`类型用来表示布林值（逻辑值）——即`true`或`假`。

Character and string processing in C# uses Unicode encoding. The `char` type represents a UTF-16 code unit, and the `string` type represents a sequence of UTF-16 code units.

C#中的字符和字符串处理使用的都是Unicode编码。`char`类型表示一个UTF-16代码单元（两个字节），`string`类型表示一个UTF-16代码单元的序列。

The following table summarizes C#'s numeric types.


| __Category__      | __Bits__ | __Type__  | __Range/Precision__ |
|-------------------|----------|-----------|---------------------|
| Signed integral   | 8        | `sbyte`   | -128...127 |
|                   | 16       | `short`   | -32,768...32,767 |
|                   | 32       | `int`     | -2,147,483,648...2,147,483,647 |
|                   | 64       | `long`    | -9,223,372,036,854,775,808...9,223,372,036,854,775,807 |
| Unsigned integral | 8        | `byte`    | 0...255 |
|                   | 16       | `ushort`  | 0...65,535 |
|                   | 32       | `uint`    | 0...4,294,967,295 |
|                   | 64       | `ulong`   | 0...18,446,744,073,709,551,615 |
| Floating point    | 32       | `float`   | 1.5 × 10^−45 to 3.4 × 10^38, 7-digit precision |
|                   | 64       | `double`  | 5.0 × 10^−324 to 1.7 × 10^308, 15-digit precision |
| Decimal           | 128      | `decimal` | 1.0 × 10^−28 to 7.9 × 10^28, 28-digit precision |

下表对C#的数值类型进行了总结。


| __类别__      | __比特数__ | __类型__  | __范围/精度__ |
|-------------------|----------|-----------|---------------------|
| 有符号整数          | 8        | `sbyte`   | -128...127 |
|                   | 16       | `short`   | -32,768...32,767 |
|                   | 32       | `int`     | -2,147,483,648...2,147,483,647 |
|                   | 64       | `long`    | -9,223,372,036,854,775,808...9,223,372,036,854,775,807 |
| 无符号整数          | 8        | `byte`    | 0...255 |
|                   | 16       | `ushort`  | 0...65,535 |
|                   | 32       | `uint`    | 0...4,294,967,295 |
|                   | 64       | `ulong`   | 0...18,446,744,073,709,551,615 |
| 浮点数             | 32       | `float`   | 1.5 × 10^−45 to 3.4 × 10^38, 精度为7位小数 |
|                   | 64       | `double`  | 5.0 × 10^−324 to 1.7 × 10^308, 精度为15位小数 |
| Decimal           | 128      | `decimal` | 1.0 × 10^−28 to 7.9 × 10^28, 精度为28位小数 |

C# programs use ***type declarations*** to create new types. A type declaration specifies the name and the members of the new type. Five of C#'s categories of types are user-definable: class types, struct types, interface types, enum types, and delegate types.

C#程序使用**类型声明**来创建新的类型。类型声明指明了类型的名字和成员。C#中有五种类型是允许用户自定义的：类类型，结构体类型，接口类型，枚举类型，和委托类型。

A class type defines a data structure that contains data members (fields) and function members (methods, properties, and others). Class types support single inheritance and polymorphism, mechanisms whereby derived classes can extend and specialize base classes.

类类型定义了包含有数据成员（字段）和函数成员（方法，属性，及其他成员）的数据结构。类类型支持单（基类）继承和多态——借由这些机制，派生类可以对基类进行扩展和专用化。

A struct type is similar to a class type in that it represents a structure with data members and function members. However, unlike classes, structs are value types and do not require heap allocation. Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type `object`.

结构体类型与类类型类似，表示的也是具有数据成员和函数成员的数据结构。然而，与类（类型）不同的是，结构体是值类型而且不要求在堆（内存）上进行分配。结构体类型不支持用户自定义的继承，并且，所有结构体都隐式地继承自`object`类型。

An interface type defines a contract as a named set of public function members. A class or struct that implements an interface must provide implementations of the interface's function members. An interface may inherit from multiple base interfaces, and a class or struct may implement multiple interfaces.

接口类型定义了一个包含有一组公开函数成员的契约。如果一个类或者结构体实现了某个接口，那么它就必需提供对接口（所有）函数成员的实现。一个接口可以继承多个基接口，一个类或结构体也可以实现多个接口。

A delegate type represents references to methods with a particular parameter list and return type. Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters. Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.

委托类型代表了对具有特定参数列表和返回值类型的方法的引用。有了委托，我们可以让方法像看上去像是能被赋值的变量，或者能像参数一样被传递。委托与其他语言中函数指针的概念类似，但与函数指针不同，委托是面向对象且类型安全的。

Class, struct, interface and delegate types all support generics, whereby they can be parameterized with other types.

类、结构体、接口和委托均支持泛型，因此它们可以被其他类型所参数化。

An enum type is a distinct type with named constants. Every enum type has an underlying type, which must be one of the eight integral types. The set of values of an enum type is the same as the set of values of the underlying type.

枚举类型是一种带有名字约束的独特类型。每个枚举类型都具有一个底层类型，这个底层类型必需是八种类型类型中的一种。枚举类型的一组值其实就是其底层类型的一组值。

C# supports single- and multi-dimensional arrays of any type. Unlike the types listed above, array types do not have to be declared before they can be used. Instead, array types are constructed by following a type name with square brackets. For example, `int[]` is a single-dimensional array of `int`, `int[,]` is a two-dimensional array of `int`, and `int[][]` is a single-dimensional array of single-dimensional arrays of `int`.

C#支持任何类型的一维或多维数组。与前述各种类型不同，使用数组类型前不必预先声明。相反，数组类型可以由一个类型名后面跟上方括号来构成。例如，`int[]`是一个`int`类型的一维数组，`int[,]`是一个`int`类型的二维数组，而`int[][]`是一个一维`int`类型数组的一维数组。

Nullable types also do not have to be declared before they can be used. For each non-nullable value type `T` there is a corresponding nullable type `T?`, which can hold an additional value `null`. For instance, `int?` is a type that can hold any 32 bit integer or the value `null`.

可空类型在使用之前也不必预先声明。对于每个非可空类型`T`来说，都有一个能够容纳`null`值的可空类型`T?`与之对应。举例而言，`int?`类型可以容纳任何32位的整数或者`null`值（译注：`int`是不能容纳`null`值的）。

C#'s type system is unified such that a value of any type can be treated as an object. Every type in C# directly or indirectly derives from the `object` class type, and `object` is the ultimate base class of all types. Values of reference types are treated as objects simply by viewing the values as type `object`. Values of value types are treated as objects by performing ***boxing*** and ***unboxing*** operations. In the following example, an `int` value is converted to `object` and back again to `int`.

```csharp
using System;

class Test
{
    static void Main() {
        int i = 123;
        object o = i;          // Boxing
        int j = (int)o;        // Unboxing
    }
}
```
When a value of a value type is converted to type `object`, an object instance, also called a "box," is allocated to hold the value, and the value is copied into that box. Conversely, when an `object` reference is cast to a value type, a check is made that the referenced object is a box of the correct value type, and, if the check succeeds, the value in the box is copied out.

C#'s unified type system effectively means that value types can become objects "on demand." Because of the unification, general-purpose libraries that use type `object` can be used with both reference types and value types.

C#具有一个统一的类型系统，任何一个值都可以被看作是一个对象。C#中的任何类型都直接或间接地派生自`object`类类型，也就是说，`object`是所有类型的最终基类。引用类型的值可以被直接当作对象来看待，方法是使用`object`类型来观察之。值类型的值也可以被当作对象来看待，但需要经过**装箱**和**拆箱**操作（boxing和unboxing操作）。随后的例子中，一个`int`类型的值被转换成了`object`类型，然后又被转换回`int`类型。

```csharp
using System;

class Test
{
    static void Main() {
        int i = 123;
        object o = i;          // 装箱
        int j = (int)o;        // 拆箱
    }
}
```
当一个值类型的值为转换为`object`类型后，一个对象实例，也称为“箱”，会被（在内存里）分配出来用以容纳这个值，原来的值会被复制到这个箱中。反过来，当一个`object`引用被转换（cast，译为“模铸”更合适）成值类型时，会检查箱里的值的类型是否正确，并且，如果检查成功，箱里的值就会被复制出来。

C#的统一类型系统明确地意味着值类型可以“按需”变成对象。正是因为这个统一性，那些使用了`object`的通用目的类库（general-purpose libraries）即可以被引用类型所使用，也可以被值类型所使用。（译注：此处应该有个例子；另：泛型就是专门不想让你这么玩儿才出现的。）

There are several kinds of ***variables*** in C#, including fields, array elements, local variables, and parameters. Variables represent storage locations, and every variable has a type that determines what values can be stored in the variable, as shown by the following table.


| __Type of Variable__    | __Possible Contents__ |
|-------------------------|-----------------------|
| Non-nullable value type | A value of that exact type |
| Nullable value type     | A null value or a value of that exact type |
| `object`                | A null reference, a reference to an object of any reference type, or a reference to a boxed value of any value type |
| Class type              | A null reference, a reference to an instance of that class type, or a reference to an instance of a class derived from that class type |
| Interface type          | A null reference, a reference to an instance of a class type that implements that interface type, or a reference to a boxed value of a value type that implements that interface type |
| Array type              | A null reference, a reference to an instance of that array type, or a reference to an instance of a compatible array type |
| Delegate type           | A null reference or a reference to an instance of that delegate type |

C#中有很多种**变量**（variables），包括：字段、数组元素，局部变量，和（方法）参数。变量代表的是（内存中的）存储位置，而且，每个变量都具有类型。变量的类型决定了什么样的值可以被存储进变量（所关联的内存空间）里，如下表：

| __变量的类型__    | __（变量内存中）可能的内容__ |
|-------------------------|-----------------------|
| 非空值类型 | 一个正是此类型的值 |
| 可空值类型 | 空值或一个正是此类型的值 |
| `object` | 一个空引用、一个对任何引用类型对象的引用、一个对装箱后的任何值类型的值的引用 |
| 类类型    | 一个空引用、一个对此类类型实例的引用、一个对此类类型派生类实例的引用 |
| 接口类型  | 一个空引用、一个对实现了此接口的类类型实例的引用、一个对装箱后的实现了这个接口的值类型的值的引用 |
| 数组类型  | 一个空引用、一个对此数组类型实例的引用、一个对兼容的数组类型实例的引用 |
| 委托类型  | 一个空引用或一个对此委托类型实例的引用 |

## Expressions | 表达式

***Expressions*** are constructed from ***operands*** and ***operators***. The operators of an expression indicate which operations to apply to the operands. Examples of operators include `+`, `-`, `*`, `/`, and `new`. Examples of operands include literals, fields, local variables, and expressions.

When an expression contains multiple operators, the ***precedence*** of the operators controls the order in which the individual operators are evaluated. For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.

Most operators can be ***overloaded***. Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.

**表达式**（expressions）由**操作数**（operands）和**操作符**（operators）构成。操作符表明了会将何种操作施加在操作数上。操作符的例子包括`+`、`-`、`*`、`/`、和 `new`（译注：操作符不一定都是符号，也可能是关键字，也就是单词）。

当一个表达式包含多个操作符时，各个操作符的求值顺序由操作符的**优先级**（precedence）来控制。例如，表达式`x + y * z`会以`x + (y * z)`的方式进行求值，因为`*`操作符具有比`+`操作符更高的优先级。

大多数操作符都能够被**重载**（overload）。当一个或两个操作数是用户定义的类或结构体时，操作符重载允许将用户定义的操作实现指派给这个操作（译注：新手断然看不懂这是什么意思）。

The following table summarizes C#'s operators, listing the operator categories in order of precedence from highest to lowest. Operators in the same category have equal precedence.


| __Category__                     | __Expression__    | __Description__ |
|----------------------------------|-------------------|-----------------|
| Primary                          | `x.m`             | Member access |
|                                  | `x(...)`          | Method and delegate invocation |
|                                  | `x[...]`          | Array and indexer access |
|                                  | `x++`             | Post-increment |
|                                  | `x--`             | Post-decrement |
|                                  | `new T(...)`      | Object and delegate creation |
|                                  | `new T(...){...}` | Object creation with initializer |
|                                  | `new {...}`       | Anonymous object initializer |
|                                  | `new T[...]`      | Array creation |
|                                  | `typeof(T)`       | Obtain `System.Type` object for `T` |
|                                  | `checked(x)`      | Evaluate expression in checked context |
|                                  | `unchecked(x)`    | Evaluate expression in unchecked context |
|                                  | `default(T)`      | Obtain default value of type `T` |
|                                  | `delegate {...}`  | Anonymous function (anonymous method) |
| Unary                            | `+x`              | Identity |
|                                  | `-x`              | Negation |
|                                  | `!x`              | Logical negation |
|                                  | `~x`              | Bitwise negation |
|                                  | `++x`             | Pre-increment |
|                                  | `--x`             | Pre-decrement |
|                                  | `(T)x`            | Explicitly convert `x` to type `T` |
|                                  | `await x`         | Asynchronously wait for `x` to complete |
| Multiplicative                   | `x * y`           | Multiplication |
|                                  | `x / y`           | Division |
|                                  | `x % y`           | Remainder |
| Additive                         | `x + y`           | Addition, string concatenation, delegate combination |
|                                  | `x - y`           | Subtraction, delegate removal |
| Shift                            | `x << y`          | Shift left |
|                                  | `x >> y`          | Shift right |
| Relational and type testing      | `x < y`           | Less than |
|                                  | `x > y`           | Greater than |
|                                  | `x <= y`          | Less than or equal |
|                                  | `x >= y`          | Greater than or equal |
|                                  | `x is T`          | Return `true` if `x` is a `T`, `false` otherwise |
|                                  | `x as T`          | Return `x` typed as `T`, or `null` if `x` is not a `T` |
| Equality                         | `x == y`          | Equal      |
|                                  | `x != y`          | Not equal |
| Logical AND                      | `x & y`           | Integer bitwise AND, boolean logical AND |
| Logical XOR                      | `x ^ y`           | Integer bitwise XOR, boolean logical XOR |
| Logical OR                       | <code>x &#124; y</code> | Integer bitwise OR, boolean logical OR |
| Conditional AND                  | `x && y`          | Evaluates `y` only if `x` is `true` |
| Conditional OR                   | <code>x &#124;&#124; y</code> | Evaluates `y` only if `x` is `false` |
| Null coalescing                  | `X ?? y`          | Evaluates to `y` if `x` is `null`, to `x` otherwise |
| Conditional                      | `x ? y : z`       | Evaluates `y` if `x` is `true`, `z` if `x` is `false` |
| Assignment or anonymous function | `x = y`           | Assignment |
|                                  | `x op= y`         | Compound assignment; supported operators are `*=` `/=` `%=` `+=` `-=` `<<=` `>>=` `&=` `^=` <code>&#124;=</code> |
|                                  | `(T x) => y`      | Anonymous function (lambda expression) |

The following table summarizes C#'s operators, listing the operator categories in order of precedence from highest to lowest. Operators in the same category have equal precedence.
下面的表格是对C#操作符的一个总结，按由高到低的优先级罗列了操作符的类别。同一个类别中的操作符具有相同的优先级。

| __类别__                     | __表达式__    | __描述__ |
|----------------------------------|-------------------|-----------------|
| 基元操作符（Primary）              | `x.m`             | 成员访问 |
|                                  | `x(...)`          | 方法及委托调用 |
|                                  | `x[...]`          | 数组及索引器访问 |
|                                  | `x++`             | 后置自增 |
|                                  | `x--`             | 后置自减 |
|                                  | `new T(...)`      | 对象及委托（实例的）创建 |
|                                  | `new T(...){...}` | 带初始化器的对象创建 |
|                                  | `new {...}`       | 匿名对象初始化器 |
|                                  | `new T[...]`      | 数组（实例）的创建 |
|                                  | `typeof(T)`       | 获取（类型）`T`的`System.Type`对象 |
|                                  | `checked(x)`      | 在检查（溢出）的上下文中对表达式求值 |
|                                  | `unchecked(x)`    | 在不检查（溢出）的上下文中对表达式求值 |
|                                  | `default(T)`      | 获取类型`T`的默认值 |
|                                  | `delegate {...}`  | 匿名函数（匿名方法形式） |
| 单目操作符（Unary）                | `+x`              | 衡等式???（原值） |
|                                  | `-x`              | 负值 |
|                                  | `!x`              | 逻辑非值 |
|                                  | `~x`              | 比特非值（补值，反值） |
|                                  | `++x`             | 前置自增 |
|                                  | `--x`             | 前置自减 |
|                                  | `(T)x`            | 显式地将`x`转换为`T`类型（cast） |
|                                  | `await x`         | 异步地等待`x`的完成 |
| 乘法操作符（Multiplicative）       | `x * y`           | 乘法 |
|                                  | `x / y`           | 除法 |
|                                  | `x % y`           | 取余数 |
| 加法操作符（Additive）             | `x + y`           | 加法，字符串连接，委托合并 |
|                                  | `x - y`           | 减法，委托移除 |
| 平移操作符（Shift）                | `x << y`          | 左移 |
|                                  | `x >> y`          | 右移 |
| 关系操作符，类型测试操作符           | `x < y`           | 小于 |
|                                  | `x > y`           | 大于 |
|                                  | `x <= y`          | 小于或等于 |
|                                  | `x >= y`          | 大于或等于 |
|                                  | `x is T`          | 如果`x`是一个`T`类型的值则求得`true`，否则求得`false` |
|                                  | `x as T`          | 如果`x`的类型是`T`则得到一个`T`类型的值，否则得到一个`null`值 |
| 相等性操作符（Equality）           | `x == y`          | 相等      |
|                                  | `x != y`          | 不相等 |
| 逻辑与操作符（Logical AND）        | `x & y`           | 整数二进制与，布林逻辑与 |
| 逻辑异或操作符（Logical XOR）      | `x ^ y`           | 整数二进制异或，布林逻辑异或 |
| 逻辑或操作符（Logical OR）         | <code>x &#124; y</code> | 整数二进制或，布林逻辑或 |
| 条件与操作符（Conditional AND）    | `x && y`          | 仅当`x`为`true`的时候`y`才会被求值 |
| 条件或操作符（Conditional OR）     | <code>x &#124;&#124; y</code> | 仅当`x`为`false`的时候`y`才会被求值 |
| 空值合并操作符（Null coalescing）  | `x ?? y`          | 如果`x`不为`null`求得`x`的值，否则求得`y`的值 |
| 条件操作符（Conditional）          | `x ? y : z`       | 如果`x`的值为`true`求得`x`的值，否则，当`x`的值为`false`求得`y`的值 |
| 赋值操作符（Assignment）及匿名函数  | `x = y`           | 赋值 |
|                                  | `x op= y`         | 复合赋值，支持的操作符包括 `*=` `/=` `%=` `+=` `-=` `<<=` `>>=` `&=` `^=` <code>&#124;=</code> |
|                                  | `(T x) => y`      | 匿名函数（lambda表达式形式） |


## Statements | 语句

The actions of a program are expressed using ***statements***. C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.

A ***block*** permits multiple statements to be written in contexts where a single statement is allowed. A block consists of a list of statements written between the delimiters `{` and `}`.

***Declaration statements*** are used to declare local variables and constants.

***Expression statements*** are used to evaluate expressions. Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and await expressions.

***Selection statements*** are used to select one of a number of possible statements for execution based on the value of some expression. In this group are the `if` and `switch` statements.

***Iteration statements*** are used to repeatedly execute an embedded statement. In this group are the `while`, `do`, `for`, and `foreach` statements.

***Jump statements*** are used to transfer control. In this group are the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.

The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.

The `checked` and `unchecked` statements are used to control the overflow checking context for integral-type arithmetic operations and conversions.

The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.

The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.

程序的动作是用**语句**（statements）来表达的。C#支持多种不同的语句，其中有不少语句称为可被嵌入语句（embedded statements）。（译注：就是一条语句可以被嵌入到另一条中。）

**块**（block）允许把多个语句写在只允许出现一条语句的地方。一个块中包含由分隔符`{`和`}`括起来的一组语句。

**声明语句**（declaration statements）用于声明局部变量和常量。

**表达式语句**（expression statements）用来对表达式进行求值。能当作语句来使用的表达式包括方法调用、使用`new`操作符分配对象、使用`=`及复合赋值操作符进行赋值、使用`++`和`--`操作符进行增加和减少，以及 `await`（等待）表达式。

**选择语句**（selection statements）会基于某些表达式的值从多个可能的语句中选一个来执行。这组语句包括`if`和`switch`。

**迭代语句**（iteration statements，亦称循环语句）被用于反复执行被嵌入其中的语句。这组语句包括`while`、`do`、`for`和`foreach`。

**跳转语句**（jump statements）用于转移（对程序执行的）控制。这组语句包括`break`、`continue`、`goto`、`throw`、`return`和`yield`。

`try`...`catch`语句用于捕捉在执行某个语句块时所发生的异常。`try`...`finally`语句则用于指定总能够被执行的收尾代码——无论有没有异常发生。

`checked`和`unchecked`语句用于为整数的算数运算或转换是否进行溢出检验做出控制。

`lock`语句用于为给定对象获取互斥锁（mutual-exclusion lock），执行一个语句，然后再释放锁。

`using`语句（译注：不是程序开头的`using`指令）用于获取一个资源（译注：这个资源一定要实现IDisposible接口），执行一个语句，然后再释放资源。

Below are examples of each kind of statement

__Local variable declarations__

```csharp
static void Main() {
   int a;
   int b = 2, c = 3;
   a = 1;
   Console.WriteLine(a + b + c);
}
```


__Local constant declaration__

```csharp
static void Main() {
    const float pi = 3.1415927f;
    const int r = 25;
    Console.WriteLine(pi * r * r);
}
```


__Expression statement__

```csharp
static void Main() {
    int i;
    i = 123;                // Expression statement
    Console.WriteLine(i);   // Expression statement
    i++;                    // Expression statement
    Console.WriteLine(i);   // Expression statement
}
```

__`if` statement__

```csharp
static void Main(string[] args) {
    if (args.Length == 0) {
        Console.WriteLine("No arguments");
    }
    else {
        Console.WriteLine("One or more arguments");
    }
}
```


__`switch` statement__

```csharp
static void Main(string[] args) {
    int n = args.Length;
    switch (n) {
        case 0:
            Console.WriteLine("No arguments");
            break;
        case 1:
            Console.WriteLine("One argument");
            break;
        default:
            Console.WriteLine("{0} arguments", n);
            break;
    }
}
```

__`while` statement__

```csharp
static void Main(string[] args) {
    int i = 0;
    while (i < args.Length) {
        Console.WriteLine(args[i]);
        i++;
    }
}
```


__`do` statement__

```csharp
static void Main() {
    string s;
    do {
        s = Console.ReadLine();
        if (s != null) Console.WriteLine(s);
    } while (s != null);
}
```

__`for` statement__

```csharp
static void Main(string[] args) {
    for (int i = 0; i < args.Length; i++) {
        Console.WriteLine(args[i]);
    }
}
```

__`foreach` statement__

```csharp
static void Main(string[] args) {
    foreach (string s in args) {
        Console.WriteLine(s);
    }
}
```

__`break` statement__

```csharp
static void Main() {
    while (true) {
        string s = Console.ReadLine();
        if (s == null) break;
        Console.WriteLine(s);
    }
}
```

__`continue` statement__

```csharp
static void Main(string[] args) {
    for (int i = 0; i < args.Length; i++) {
        if (args[i].StartsWith("/")) continue;
        Console.WriteLine(args[i]);
    }
}
```

__`goto` statement__

```csharp
static void Main(string[] args) {
    int i = 0;
    goto check;
    loop:
    Console.WriteLine(args[i++]);
    check:
    if (i < args.Length) goto loop;
}
```

__`return` statement__

```csharp
static int Add(int a, int b) {
    return a + b;
}

static void Main() {
    Console.WriteLine(Add(1, 2));
    return;
}
```

__`yield` statement__

```csharp
static IEnumerable<int> Range(int from, int to) {
    for (int i = from; i < to; i++) {
        yield return i;
    }
    yield break;
}

static void Main() {
    foreach (int x in Range(-10,10)) {
        Console.WriteLine(x);
    }
}
```

__`throw` and `try` statements__

```csharp
static double Divide(double x, double y) {
    if (y == 0) throw new DivideByZeroException();
    return x / y;
}

static void Main(string[] args) {
    try {
        if (args.Length != 2) {
            throw new Exception("Two numbers required");
        }
        double x = double.Parse(args[0]);
        double y = double.Parse(args[1]);
        Console.WriteLine(Divide(x, y));
    }
    catch (Exception e) {
        Console.WriteLine(e.Message);
    }
    finally {
        Console.WriteLine("Good bye!");
    }
}
```

__`checked` and `unchecked` statements__

```csharp
static void Main() {
    int i = int.MaxValue;
    checked {
        Console.WriteLine(i + 1);        // Exception
    }
    unchecked {
        Console.WriteLine(i + 1);        // Overflow
    }
}
```

__`lock` statement__

```csharp
class Account
{
    decimal balance;
    public void Withdraw(decimal amount) {
        lock (this) {
            if (amount > balance) {
                throw new Exception("Insufficient funds");
            }
            balance -= amount;
        }
    }
}
```

__`using` statement__

```csharp
static void Main() {
    using (TextWriter w = File.CreateText("test.txt")) {
        w.WriteLine("Line one");
        w.WriteLine("Line two");
        w.WriteLine("Line three");
    }
}
```

以下是各种语句的例子：

__局部变量声明__

```csharp
static void Main() {
   int a;
   int b = 2, c = 3;
   a = 1;
   Console.WriteLine(a + b + c);
}
```


__局部常量声明__

```csharp
static void Main() {
    const float pi = 3.1415927f;
    const int r = 25;
    Console.WriteLine(pi * r * r);
}
```


__表达式语句__

```csharp
static void Main() {
    int i;
    i = 123;                // 表达式语句
    Console.WriteLine(i);   // 表达式语句
    i++;                    // 表达式语句
    Console.WriteLine(i);   // 表达式语句
}
```

__`if`语句__

```csharp
static void Main(string[] args) {
    if (args.Length == 0) {
        Console.WriteLine("No arguments");
    }
    else {
        Console.WriteLine("One or more arguments");
    }
}
```


__`switch`语句__

```csharp
static void Main(string[] args) {
    int n = args.Length;
    switch (n) {
        case 0:
            Console.WriteLine("No arguments");
            break;
        case 1:
            Console.WriteLine("One argument");
            break;
        default:
            Console.WriteLine("{0} arguments", n);
            break;
    }
}
```

__`while`语句__

```csharp
static void Main(string[] args) {
    int i = 0;
    while (i < args.Length) {
        Console.WriteLine(args[i]);
        i++;
    }
}
```


__`do`语句__

```csharp
static void Main() {
    string s;
    do {
        s = Console.ReadLine();
        if (s != null) Console.WriteLine(s);
    } while (s != null);
}
```

__`for`语句__

```csharp
static void Main(string[] args) {
    for (int i = 0; i < args.Length; i++) {
        Console.WriteLine(args[i]);
    }
}
```

__`foreach`语句__

```csharp
static void Main(string[] args) {
    foreach (string s in args) {
        Console.WriteLine(s);
    }
}
```

__`break`语句__

```csharp
static void Main() {
    while (true) {
        string s = Console.ReadLine();
        if (s == null) break;
        Console.WriteLine(s);
    }
}
```

__`continue`语句__

```csharp
static void Main(string[] args) {
    for (int i = 0; i < args.Length; i++) {
        if (args[i].StartsWith("/")) continue;
        Console.WriteLine(args[i]);
    }
}
```

__`goto`语句__

```csharp
static void Main(string[] args) {
    int i = 0;
    goto check;
    loop:
    Console.WriteLine(args[i++]);
    check:
    if (i < args.Length) goto loop;
}
```

__`return`语句__

```csharp
static int Add(int a, int b) {
    return a + b;
}

static void Main() {
    Console.WriteLine(Add(1, 2));
    return;
}
```

__`yield`语句__

```csharp
static IEnumerable<int> Range(int from, int to) {
    for (int i = from; i < to; i++) {
        yield return i;
    }
    yield break;
}

static void Main() {
    foreach (int x in Range(-10,10)) {
        Console.WriteLine(x);
    }
}
```

__`throw`和`try`语句__

```csharp
static double Divide(double x, double y) {
    if (y == 0) throw new DivideByZeroException();
    return x / y;
}

static void Main(string[] args) {
    try {
        if (args.Length != 2) {
            throw new Exception("Two numbers required");
        }
        double x = double.Parse(args[0]);
        double y = double.Parse(args[1]);
        Console.WriteLine(Divide(x, y));
    }
    catch (Exception e) {
        Console.WriteLine(e.Message);
    }
    finally {
        Console.WriteLine("Good bye!");
    }
}
```

__`checked`和`unchecked`语句__

```csharp
static void Main() {
    int i = int.MaxValue;
    checked {
        Console.WriteLine(i + 1);        // 异常
    }
    unchecked {
        Console.WriteLine(i + 1);        // 溢出（不产生异常）
    }
}
```

__`lock`语句__

```csharp
class Account
{
    decimal balance;
    public void Withdraw(decimal amount) {
        lock (this) {
            if (amount > balance) {
                throw new Exception("Insufficient funds");
            }
            balance -= amount;
        }
    }
}
```

__`using`语句__

```csharp
static void Main() {
    using (TextWriter w = File.CreateText("test.txt")) {
        w.WriteLine("Line one");
        w.WriteLine("Line two");
        w.WriteLine("Line three");
    }
}
```

## Classes and objects | 类与对象

***Classes*** are the most fundamental of C#'s types. A class is a data structure that combines state (fields) and actions (methods and other function members) in a single unit. A class provides a definition for dynamically created ***instances*** of the class, also known as ***objects***. Classes support ***inheritance*** and ***polymorphism***, mechanisms whereby ***derived classes*** can extend and specialize ***base classes***.

**类**（classes）是C#类型系统最基础的部分。类是一种能将状态（即字段）和行为（即方法和其他函数成员）结合在一个独立单元中的数据结构。类为创建其**实例**（instances）提供了定义，实例也被称为**对象**（objects）。类支持**继承**（inheritance）和**多态**（polymorphism）机制——它们都基于**派生类**（derived classes）对**基类**（base classes）的扩展与特殊化。

New classes are created using class declarations. A class declaration starts with a header that specifies the attributes and modifiers of the class, the name of the class, the base class (if given), and the interfaces implemented by the class. The header is followed by the class body, which consists of a list of member declarations written between the delimiters `{` and `}`.

使用类声明（class declarations）可以创建新的类。类声明以一个声明头（header）开始，声明头里指明了（用于修饰）这个类的特征（attribute）和修饰符（modifiers）、类的名字、这个类的基类和所实现的接口（如果有）。跟在类的声明头之后的是类体（body），类体是书写在一对花括号分隔符（`{`和`}`）中的一系列成员声明。

The following is a declaration of a simple class named `Point`:

```csharp
public class Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
```

以下代码是一个简单的类的声明，类的名字叫`Point`：

```csharp
public class Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
```

Instances of classes are created using the `new` operator, which allocates memory for a new instance, invokes a constructor to initialize the instance, and returns a reference to the instance. The following statements create two `Point` objects and store references to those objects in two variables:

```csharp
Point p1 = new Point(0, 0);
Point p2 = new Point(10, 20);
```
The memory occupied by an object is automatically reclaimed when the object is no longer in use. It is neither necessary nor possible to explicitly deallocate objects in C#.

使用`new`操作符可以创建类的实例。`new`操作符会为实例分配内存并调用一个（指定的）构造器来对实例进行初始化，然后返回一个对实例的引用。下面的语句创建了两个`Point`（类类型的）对象并且把对这两个对象的引用存储在了两个变量里：

```csharp
Point p1 = new Point(0, 0);
Point p2 = new Point(10, 20);
```

一旦对象不再被使用，被对象所占用的内存就会被自动地回收。在C#中，既没必要也没办法显式地销毁（deallocate）一个对象。

### Members | 成员

The members of a class are either ***static members*** or ***instance members***. Static members belong to classes, and instance members belong to objects (instances of classes).

The following table provides an overview of the kinds of members a class can contain.


| __Member__   | __Description__ |
|------------  |-----------------|
| Constants    | Constant values associated with the class |
| Fields       | Variables of the class |
| Methods      | Computations and actions that can be performed by the class |
| Properties   | Actions associated with reading and writing named properties of the class |
| Indexers     | Actions associated with indexing instances of the class like an array |
| Events       | Notifications that can be generated by the class |
| Operators    | Conversions and expression operators supported by the class |
| Constructors | Actions required to initialize instances of the class or the class itself |
| Destructors  | Actions to perform before instances of the class are permanently discarded |
| Types        | Nested types declared by the class |

类的成员要么是**静态成员**（static members）要么是**实例成员**（instance members）。静态成员属于类，而实例成员属于对象（即类的实例）。

下表是对类所能包含的所有成员种类的一个概览。

| __成员__   | __描述__ |
|------------  |-----------------|
| 常量    | 与类相关联的常量 |
| 字段    | 隶属于类的变量 |
| 方法    | 可被类执行运算与行为 |
| 属性    | 与读写类的具名属性相关联的操作 |
| 索引器  | 与像数组般索引类的实例相关联的操作 |
| 事件    | 可被类所生成的通知 |
| 操作符  | 被类所支持的类型转换及表达式操作符 |
| 构造器  | 被用来初始化类的实例或类本身的行为 |
| 析构器  | 在类的对象被永久丢弃前所执行的行为 |
| 类型    | 被类所声明的嵌套类型 |

### Accessibility | 访问性

Each member of a class has an associated accessibility, which controls the regions of program text that are able to access the member. There are five possible forms of accessibility. These are summarized in the following table.


| __Accessibility__    | __Meaning__ |
|----------------------|-----------------|
| `public`             | Access not limited |
| `protected`          | Access limited to this class or classes derived from this class |
| `internal`           | Access limited to this program |
| `protected internal` | Access limited to this program or classes derived from this class |
| `private`            | Access limited to this class |

类的每个成员都有一个与之关联的访问性，访问性控制着从程序文本的哪些区域可以访问这个成员。访问性有五种可能的形式（译注：C# 7中有所增加），它们总结于下表之中：

| __访问性__    | __含义__ |
|----------------------|-----------------|
| `public`             | 访问不受限制 |
| `protected`          | 访问被限制于当前类或当前类的派生类 |
| `internal`           | 访问被限制于当前程序 |
| `protected internal` | 访问被限制于当前程序或当前类的派生类 |
| `private`            | 访问被限制于当前类 |

### Type parameters | 类型参数

A class definition may specify a set of type parameters by following the class name with angle brackets enclosing a list of type parameter names. The type parameters can the be used in the body of the class declarations to define the members of the class. In the following example, the type parameters of `Pair` are `TFirst` and `TSecond`:

```csharp
public class Pair<TFirst,TSecond>
{
    public TFirst First;
    public TSecond Second;
}
```
A class type that is declared to take type parameters is called a generic class type. Struct, interface and delegate types can also be generic.

When the generic class is used, type arguments must be provided for each of the type parameters:

```csharp
Pair<int,string> pair = new Pair<int,string> { First = 1, Second = "two" };
int i = pair.First;     // TFirst is int
string s = pair.Second; // TSecond is string
```
A generic type with type arguments provided, like `Pair<int,string>` above, is called a constructed type.

在类的定义中可以指定一组类型参数，方法是在类名后跟上一对尖括号，并在尖括号里写上一列类型参数名。这些类型参数名可以用于在类体中定义类的成员。在下面的例子中，`Pair`的类型参数是`TFirst`和`TSecond`：

```csharp
public class Pair<TFirst,TSecond>
{
    public TFirst First;
    public TSecond Second;
}
```

带有类型参数的类类型被称为泛型（generic）类类型。结构体、接口和委托也可以是泛型的。

当使用一个泛型类的时候，必需为每个类型参数（type parameters）提供类型实际参数（type arguments）：

```csharp
Pair<int,string> pair = new Pair<int,string> { First = 1, Second = "two" };
int i = pair.First;     // TFirst为int
string s = pair.Second; // TSecond为string
```

一个具有类型实际参数的泛型类，譬如前面的`Pair<int,string>`，被称为已构造的类型（constructed type）。

### Base classes | 基类

A class declaration may specify a base class by following the class name and type parameters with a colon and the name of the base class. Omitting a base class specification is the same as deriving from type `object`. In the following example, the base class of `Point3D` is `Point`, and the base class of `Point` is `object`:

```csharp
public class Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}

public class Point3D: Point
{
    public int z;

    public Point3D(int x, int y, int z): base(x, y) {
        this.z = z;
    }
}
```

在类的声明中可以指定一个基类，方法是在类名和类型参数（如果有）后面跟上一个冒号（`:`）然后再跟上基类的名字。省略基类的名字等同于从`object`类派生。在下面的例子中，`Point3D`类的基类是`Point`，而`Point`类的基类是`object`：

```csharp
public class Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}

public class Point3D: Point
{
    public int z;

    public Point3D(int x, int y, int z): base(x, y) {
        this.z = z;
    }
}
```

A class inherits the members of its base class. Inheritance means that a class implicitly contains all members of its base class, except for the instance and static constructors, and the destructors of the base class. A derived class can add new members to those it inherits, but it cannot remove the definition of an inherited member. In the previous example, `Point3D` inherits the `x` and `y` fields from `Point`, and every `Point3D` instance contains three fields, `x`, `y`, and `z`.

An implicit conversion exists from a class type to any of its base class types. Therefore, a variable of a class type can reference an instance of that class or an instance of any derived class. For example, given the previous class declarations, a variable of type `Point` can reference either a `Point` or a `Point3D`:

```csharp
Point a = new Point(10, 20);
Point b = new Point3D(10, 20, 30);
```

一个类会继承其基类的成员。继承意味着一个类会隐式地包含其基类除实例构造器、静态构造器和析构器外的所有成员。派生类可以在继承成员的基础上增添新的成员，但不能移除继承来的成员。在前面的例子中，`Point3D`类从`Point`类继承了`x`和`y`这两个字段，而每个`Point3D`类的实例包含三个字段——`x`、`y`和`z`。

从某个类类型向其基类类型可以做隐式类型转换。因此，一个类类型的变量可以引用一个此类的任意派生类类型的实例。例如，给定前述类的继承，则`Point`类型的变量即可以引用一个`Point`类型的实例，也可以引用一个`Point3D`类型的实例：

```csharp
Point a = new Point(10, 20);
Point b = new Point3D(10, 20, 30);
```

### Fields | 字段

A field is a variable that is associated with a class or with an instance of a class.

A field declared with the `static` modifier defines a ***static field***. A static field identifies exactly one storage location. No matter how many instances of a class are created, there is only ever one copy of a static field.

A field declared without the `static` modifier defines an ***instance field***. Every instance of a class contains a separate copy of all the instance fields of that class.

In the following example, each instance of the `Color` class has a separate copy of the `r`, `g`, and `b` instance fields, but there is only one copy of the `Black`, `White`, `Red`, `Green`, and `Blue` static fields:

```csharp
public class Color
{
    public static readonly Color Black = new Color(0, 0, 0);
    public static readonly Color White = new Color(255, 255, 255);
    public static readonly Color Red = new Color(255, 0, 0);
    public static readonly Color Green = new Color(0, 255, 0);
    public static readonly Color Blue = new Color(0, 0, 255);
    private byte r, g, b;

    public Color(byte r, byte g, byte b) {
        this.r = r;
        this.g = g;
        this.b = b;
    }
}
```
As shown in the previous example, ***read-only fields*** may be declared with a `readonly` modifier. Assignment to a `readonly` field can only occur as part of the field's declaration or in a constructor in the same class.

字段是与类或类的实例所关联的变量。

带有`static`修饰符的字段声明定义了一个**静态字段**（static field）。静态字段标识着唯一的存储位置。无论多少个实例或多少个（派生）类被创建出来，静态字段都是唯一的（原：永远只有一份拷贝）。

不带`static`修饰符的字段声明则定义了一个**实例字段**（instance field）。类的每个实例都包含了这个类所有实例字段的独立的拷贝。

在下面的例子中，`Color`类的每个实例都具有`r`、`g`、`b`三个实例字段的独立拷贝，但`Black`、`White`、`Red`、`Green`和`Blue`这些静态字段却只有一个拷贝。

```csharp
public class Color
{
    public static readonly Color Black = new Color(0, 0, 0);
    public static readonly Color White = new Color(255, 255, 255);
    public static readonly Color Red = new Color(255, 0, 0);
    public static readonly Color Green = new Color(0, 255, 0);
    public static readonly Color Blue = new Color(0, 0, 255);
    private byte r, g, b;

    public Color(byte r, byte g, byte b) {
        this.r = r;
        this.g = g;
        this.b = b;
    }
}
```

如前面例子中所示，通过使用`readonly`修饰符可以声明**只读字段**（read-only fields）。对`readonly`字段的赋值要么是字段声明的一部分，要么只能在这个类的（译注：静态或实例）构造器中来完成。

### Methods | 方法

A ***method*** is a member that implements a computation or action that can be performed by an object or class. ***Static methods*** are accessed through the class. ***Instance methods*** are accessed through instances of the class.

Methods have a (possibly empty) list of ***parameters***, which represent values or variable references passed to the method, and a ***return type***, which specifies the type of the value computed and returned by the method. A method's return type is `void` if it does not return a value.

Like types, methods may also have a set of type parameters, for which type arguments must be specified when the method is called. Unlike types, the type arguments can often be inferred from the arguments of a method call and need not be explicitly given.

The ***signature*** of a method must be unique in the class in which the method is declared. The signature of a method consists of the name of the method, the number of type parameters and the number, modifiers, and types of its parameters. The signature of a method does not include the return type.

**方法**（methods）是用来实现类或对象所执行的运算或行为的一种成员。**静态方法**（static methods）需要通过类来访问。**实例方法**（instance methods）需要通过类的实例来访问。

方法会具有一列**参数**（这列参数可能是空的）用以表示传进方法的值或者引用变量。方法还具有一个**返回值类型**，这个类型指定了这个方法将计算出来并返回的值。如果一个方法不返回任何值，那么这个方法的返回值类型是`void`。

如同各种类型一样，方法也可以拥有一组类型参数。当方法被调用的时候，方法的类型参数必需被明确化。与（泛型）类型不同，（泛型）方法的类型参数经常是由方法调用时的实际参数推断出来的，而不必明确给出。

在一个类中，方法的**签名**（signature）必须是唯一的。方法的签名由方法名、类型参数以及参数的个数、类型和修饰符构成。方法的签名不包含方法的返回值类型（译注：也不包含方法的参数名）。

#### Parameters | 参数

Parameters are used to pass values or variable references to methods. The parameters of a method get their actual values from the ***arguments*** that are specified when the method is invoked. There are four kinds of parameters: value parameters, reference parameters, output parameters, and parameter arrays.

参数用于将值或变量引用传入方法。方法的参数会从方法被调用时所指定的**实际参数**（arguments）上获取它们实际的值。这里有四种参数：值参数，引用参数，输出参数，和参数数组。

A ***value parameter*** is used for input parameter passing. A value parameter corresponds to a local variable that gets its initial value from the argument that was passed for the parameter. Modifications to a value parameter do not affect the argument that was passed for the parameter.

Value parameters can be optional, by specifying a default value so that corresponding arguments can be omitted.

**值参数**（value parameter）用于传递输入参数。值参数相当于一个局部变量，只是它的初始值是从实际参数那里获得的——实际参数专为传递给参数而设定。对于值参数的更改并不会影响到实际参数。

通过指定默认值给相应的值参数，这个值参数（在调用的时候）就成了可选的参数。

A ***reference parameter*** is used for both input and output parameter passing. The argument passed for a reference parameter must be a variable, and during execution of the method, the reference parameter represents the same storage location as the argument variable. A reference parameter is declared with the `ref` modifier. The following example shows the use of `ref` parameters.

```csharp
using System;

class Test
{
    static void Swap(ref int x, ref int y) {
        int temp = x;
        x = y;
        y = temp;
    }

    static void Main() {
        int i = 1, j = 2;
        Swap(ref i, ref j);
        Console.WriteLine("{0} {1}", i, j);            // Outputs "2 1"
    }
}
```

**引用参数**在进行参数传递的时候既可以用于输入也可以用于输出。被传递给引用参数的实际参数必需是一个变量，而且，在方法执行的过程中，引用参数与实际参数代表的是同一个存储位置。引用参数的声明中带有`ref`修饰符。下面的例子展示了`ref`参数的使用：

```csharp
using System;

class Test
{
    static void Swap(ref int x, ref int y) {
        int temp = x;
        x = y;
        y = temp;
    }

    static void Main() {
        int i = 1, j = 2;
        Swap(ref i, ref j);
        Console.WriteLine("{0} {1}", i, j);            // 输出 "2 1"
    }
}
```
An ***output parameter*** is used for output parameter passing. An output parameter is similar to a reference parameter except that the initial value of the caller-provided argument is unimportant. An output parameter is declared with the `out` modifier. The following example shows the use of `out` parameters.

```csharp
using System;

class Test
{
    static void Divide(int x, int y, out int result, out int remainder) {
        result = x / y;
        remainder = x % y;
    }

    static void Main() {
        int res, rem;
        Divide(10, 3, out res, out rem);
        Console.WriteLine("{0} {1}", res, rem);    // Outputs "3 1"
    }
}
```

**输出参数**在参数传递的时候用于输出。输出参数类似于引用参数，只是由调用者的提供的、用于初始化参数的实参值并不重要（译注：因为会在方法体里被改写）。输出参数的声明中带有`out`修饰符。下面的例子中展示了`out`参数的用法：

```csharp
using System;

class Test
{
    static void Divide(int x, int y, out int result, out int remainder) {
        result = x / y;
        remainder = x % y;
    }

    static void Main() {
        int res, rem;
        Divide(10, 3, out res, out rem);
        Console.WriteLine("{0} {1}", res, rem);    // 输出 "3 1"
    }
}
```

A ***parameter array*** permits a variable number of arguments to be passed to a method. A parameter array is declared with the `params` modifier. Only the last parameter of a method can be a parameter array, and the type of a parameter array must be a single-dimensional array type. The `Write` and `WriteLine` methods of the `System.Console` class are good examples of parameter array usage. They are declared as follows.

```csharp
public class Console
{
    public static void Write(string fmt, params object[] args) {...}
    public static void WriteLine(string fmt, params object[] args) {...}
    ...
}
```

**参数数组**允许向方法传入个数不固定的实际参数。参数数组在声明的时候带有`params`修饰符。方法的参数列表中，只有最后一个参数可以是参数数组，而且这个参数的类型必须是一维数组类型。`System.Console`类的`Write`和`WriteLine`方法就是参数数组两个典型应用。它们的声明如下：

```csharp
public class Console
{
    public static void Write(string fmt, params object[] args) {...}
    public static void WriteLine(string fmt, params object[] args) {...}
    ...
}
```

Within a method that uses a parameter array, the parameter array behaves exactly like a regular parameter of an array type. However, in an invocation of a method with a parameter array, it is possible to pass either a single argument of the parameter array type or any number of arguments of the element type of the parameter array. In the latter case, an array instance is automatically created and initialized with the given arguments. This example

```csharp
Console.WriteLine("x={0} y={1} z={2}", x, y, z);
```
is equivalent to writing the following.

```csharp
string s = "x={0} y={1} z={2}";
object[] args = new object[3];
args[0] = x;
args[1] = y;
args[2] = z;
Console.WriteLine(s, args);
```

在一个使用了参数数组的方法中，参数数组的行为与标准的数组无异。然而，调用一个带有参数数组的方法时，既可以传入一个数组类型的实际参数，又可以传入任意个数的数组元素类型的实际参数。在后面的例子中，会自动生成一个数组实例并用传入的实际参数进行了初始化。请看例子：

```csharp
Console.WriteLine("x={0} y={1} z={2}", x, y, z);
```

与后面的写法是等价的：

```csharp
string s = "x={0} y={1} z={2}";
object[] args = new object[3];
args[0] = x;
args[1] = y;
args[2] = z;
Console.WriteLine(s, args);
```

#### Method body and local variables | 方法体与局部变量

A method's body specifies the statements to execute when the method is invoked.

A method body can declare variables that are specific to the invocation of the method. Such variables are called ***local variables***. A local variable declaration specifies a type name, a variable name, and possibly an initial value. The following example declares a local variable `i` with an initial value of zero and a local variable `j` with no initial value.

```csharp
using System;

class Squares
{
    static void Main() {
        int i = 0;
        int j;
        while (i < 10) {
            j = i * i;
            Console.WriteLine("{0} x {0} = {1}", i, j);
            i = i + 1;
        }
    }
}
```
C# requires a local variable to be ***definitely assigned*** before its value can be obtained. For example, if the declaration of the previous `i` did not include an initial value, the compiler would report an error for the subsequent usages of `i` because `i` would not be definitely assigned at those points in the program.

A method can use `return` statements to return control to its caller. In a method returning `void`, `return` statements cannot specify an expression. In a method returning non-`void`, `return` statements must include an expression that computes the return value.

方法体指定了方法被调用时将要执行的语句。

在方法体中可以声明专属于方法调用的变量。这样的变量被称为**局部变量**。局部变量的声明指定了一个类型名、一个变量名、和一个可选的初始值。后面的例子中声明了一个以零为初始值的局部变量`i`和一个没有初始值的局部变量`j`。

```csharp
using System;

class Squares
{
    static void Main() {
        int i = 0;
        int j;
        while (i < 10) {
            j = i * i;
            Console.WriteLine("{0} x {0} = {1}", i, j);
            i = i + 1;
        }
    }
}
```

C#要求局部变量必须先被**确保赋值**（definitely assigned）才能从之获取值。例如，如果前面例子中的`i`没有初始值，编译器就会为后续对`i`的使用报告一个错误，因为`i`在程序中并没有确保被赋值。

方法可以使用`return`语句把（程序执行的）控制权交还给它的调用者。在一个会返还`void`的方法中，`return`语句不能指定（被作为返还值）的表达式。在返还非`void`的方法中，`return`语句必须包含一个用于计算返还值的表达式。

#### Static and instance methods | 静态与实例方法

A method declared with a `static` modifier is a ***static method***. A static method does not operate on a specific instance and can only directly access static members.

A method declared without a `static` modifier is an ***instance method***. An instance method operates on a specific instance and can access both static and instance members. The instance on which an instance method was invoked can be explicitly accessed as `this`. It is an error to refer to `this` in a static method.

声明时带有`static`修饰符的方法称为**静态方法**。静态方法只能访问静态成员而不能在实例上进行操作。（译注：这句话新手比较难懂，特别是“在实例上操作”。）

声明时不带有`static`修饰符的方法称为**实例方法**。实例方法可以在指定实例上进行操作（译注：实例方法实例上操作的是this对象，或者说“在this引用的对象上进行操作”，而this是个隐含参数，这个参数在C系语言中看不到，但在Python里是能看到的），而且既可以访问静态成员又可以访问实例成员。在其之上调用实例方法的这个实例，在实例方法中可以通过`this`来显式地访问。在静态方法中使用`this`是错误的。

The following `Entity` class has both static and instance members.

```csharp
class Entity
{
    static int nextSerialNo;
    int serialNo;

    public Entity() {
        serialNo = nextSerialNo++;
    }

    public int GetSerialNo() {
        return serialNo;
    }

    public static int GetNextSerialNo() {
        return nextSerialNo;
    }

    public static void SetNextSerialNo(int value) {
        nextSerialNo = value;
    }
}
```
Each `Entity` instance contains a serial number (and presumably some other information that is not shown here). The `Entity` constructor (which is like an instance method) initializes the new instance with the next available serial number. Because the constructor is an instance member, it is permitted to access both the `serialNo` instance field and the `nextSerialNo` static field.

The `GetNextSerialNo` and `SetNextSerialNo` static methods can access the `nextSerialNo` static field, but it would be an error for them to directly access the `serialNo` instance field.

下面的`Entity`类既拥有静态成员也拥有实例成员。

```csharp
class Entity
{
    static int nextSerialNo;
    int serialNo;

    public Entity() {
        serialNo = nextSerialNo++;
    }

    public int GetSerialNo() {
        return serialNo;
    }

    public static int GetNextSerialNo() {
        return nextSerialNo;
    }

    public static void SetNextSerialNo(int value) {
        nextSerialNo = value;
    }
}
```

每个`Entity`实例都包含有一个序列号（译注：由`serialNo`字段表示），也可以假设还有一些其他的信息，只是没有显示在这里。`Entity`的构造器（看起来像是个实例方法）会用下一个可用的序列号（译注：由静态的`nextSerialNo`字段表示）来初始化新的实例。因为这个构造器是一个实例成员，所以它既可以访问实例字段`serialNo`又可以访问静态字段`nextSerialNo`。

`GetNextSerialNo`和`SetNextSerialNo`两个静态方法可以访问静态字段`nextSerialNo`，但是它们无法访问实例字段`serialNo`，否则会产生错误。

The following example shows the use of the `Entity` class.

```csharp
using System;

class Test
{
    static void Main() {
        Entity.SetNextSerialNo(1000);
        Entity e1 = new Entity();
        Entity e2 = new Entity();
        Console.WriteLine(e1.GetSerialNo());           // Outputs "1000"
        Console.WriteLine(e2.GetSerialNo());           // Outputs "1001"
        Console.WriteLine(Entity.GetNextSerialNo());   // Outputs "1002"
    }
}
```
Note that the `SetNextSerialNo` and `GetNextSerialNo` static methods are invoked on the class whereas the `GetSerialNo` instance method is invoked on instances of the class.

以下的例子展示了对`Entity`类的使用。

```csharp
using System;

class Test
{
    static void Main() {
        Entity.SetNextSerialNo(1000);
        Entity e1 = new Entity();
        Entity e2 = new Entity();
        Console.WriteLine(e1.GetSerialNo());           // 输出"1000"
        Console.WriteLine(e2.GetSerialNo());           // 输出"1001"
        Console.WriteLine(Entity.GetNextSerialNo());   // 输出"1002"
    }
}
```

请注意，`SetNextSerialNo`和`GetNextSerialNo`静态方法是在类上被调用，而`GetSerialNo`实例方法则是在类的实例上被调用。（译注：仍然是这个“方法在……上被调用”）

#### Virtual, override, and abstract methods | 虚方法、重写方法和抽象方法

When an instance method declaration includes a `virtual` modifier, the method is said to be a ***virtual method***. When no `virtual` modifier is present, the method is said to be a ***non-virtual method***.

When a virtual method is invoked, the ***run-time type*** of the instance for which that invocation takes place determines the actual method implementation to invoke. In a nonvirtual method invocation, the ***compile-time type*** of the instance is the determining factor.

A virtual method can be ***overridden*** in a derived class. When an instance method declaration includes an `override` modifier, the method overrides an inherited virtual method with the same signature. Whereas a virtual method declaration introduces a new method, an override method declaration specializes an existing inherited virtual method by providing a new implementation of that method.

An ***abstract*** method is a virtual method with no implementation. An abstract method is declared with the `abstract` modifier and is permitted only in a class that is also declared `abstract`. An abstract method must be overridden in every non-abstract derived class.

当一个实例方法的声明中包含有`virtual`修饰符的时候，这个方法就是一个**虚方法**（virtual method）。当（实例方法的声明中）未出现`virtual`修饰符的时候，这个方法被称为**非虚方法**（non-virtual method）。

当一个虚方法被调用的时候，实例的**运行期类型**（run-time type）决定了方法哪个实现会被调用。在一个非虚方法的调用中，实例的**编译期类型**是决定因素。

在派生类中，虚方法可以被**重写**（overridden）。当一个实例方法的声明中包含有`override`修饰符的时候，这个方法就会重写继承而来的、与之签名相同的虚方法。虚方法的定义会引入一个新的方法，而重写方法（不会引入新的方法，它）的声明会通过提供一个新的实现将继承得来、已经存在的虚方法进行特殊化。

**抽象方法**（abstract method）是一个没有实现的虚方法（译注：所以抽象方法也叫“纯虚方法”）。抽象方法的声明中会包含`abstract`修饰符，且抽象方法只允许声明在被`abstract`所修饰的类中（译注：即抽象类中）。在每个非抽象的派生类中，抽象方法都必须被重写（译注：或者说必须被实现）。

The following example declares an abstract class, `Expression`, which represents an expression tree node, and three derived classes, `Constant`, `VariableReference`, and `Operation`, which implement expression tree nodes for constants, variable references, and arithmetic operations. (This is similar to, but not to be confused with the expression tree types introduced in [Expression tree types](types.md#expression-tree-types)).

```csharp
using System;
using System.Collections;

public abstract class Expression
{
    public abstract double Evaluate(Hashtable vars);
}

public class Constant: Expression
{
    double value;

    public Constant(double value) {
        this.value = value;
    }

    public override double Evaluate(Hashtable vars) {
        return value;
    }
}

public class VariableReference: Expression
{
    string name;

    public VariableReference(string name) {
        this.name = name;
    }

    public override double Evaluate(Hashtable vars) {
        object value = vars[name];
        if (value == null) {
            throw new Exception("Unknown variable: " + name);
        }
        return Convert.ToDouble(value);
    }
}

public class Operation: Expression
{
    Expression left;
    char op;
    Expression right;

    public Operation(Expression left, char op, Expression right) {
        this.left = left;
        this.op = op;
        this.right = right;
    }

    public override double Evaluate(Hashtable vars) {
        double x = left.Evaluate(vars);
        double y = right.Evaluate(vars);
        switch (op) {
            case '+': return x + y;
            case '-': return x - y;
            case '*': return x * y;
            case '/': return x / y;
        }
        throw new Exception("Unknown operator");
    }
}
```
The previous four classes can be used to model arithmetic expressions. For example, using instances of these classes, the expression `x + 3` can be represented as follows.

```csharp
Expression e = new Operation(
    new VariableReference("x"),
    '+',
    new Constant(3));
```
The `Evaluate` method of an `Expression` instance is invoked to evaluate the given expression and produce a `double` value. The method takes as an argument a `Hashtable` that contains variable names (as keys of the entries) and values (as values of the entries). The `Evaluate` method is a virtual abstract method, meaning that non-abstract derived classes must override it to provide an actual implementation.

A `Constant`'s implementation of `Evaluate` simply returns the stored constant. A `VariableReference`'s implementation looks up the variable name in the hashtable and returns the resulting value. An `Operation`'s implementation first evaluates the left and right operands (by recursively invoking their `Evaluate` methods) and then performs the given arithmetic operation.

The following program uses the `Expression` classes to evaluate the expression `x * (y + 2)` for different values of `x` and `y`.

```csharp
using System;
using System.Collections;

class Test
{
    static void Main() {
        Expression e = new Operation(
            new VariableReference("x"),
            '*',
            new Operation(
                new VariableReference("y"),
                '+',
                new Constant(2)
            )
        );
        Hashtable vars = new Hashtable();
        vars["x"] = 3;
        vars["y"] = 5;
        Console.WriteLine(e.Evaluate(vars));        // Outputs "21"
        vars["x"] = 1.5;
        vars["y"] = 9;
        Console.WriteLine(e.Evaluate(vars));        // Outputs "16.5"
    }
}
```

下面的例子声明了一个名为`Expression`的抽象类（它表示的是表达式树上的结点）和三个（具体）类`Constant`、`VariableReference`和`Operation`（分别表示对常量、变量引用和数学运算符这三种表达式树结点的实现）。（注意：这个例子只是与[表达式树类型](types.md#expression-tree-types)中引入的概念相似，请不要与之混淆。）（译注：都知道容易混淆了，干嘛不换个例子？）

```csharp
using System;
using System.Collections;

public abstract class Expression
{
    public abstract double Evaluate(Hashtable vars);
}

public class Constant: Expression
{
    double value;

    public Constant(double value) {
        this.value = value;
    }

    public override double Evaluate(Hashtable vars) {
        return value;
    }
}

public class VariableReference: Expression
{
    string name;

    public VariableReference(string name) {
        this.name = name;
    }

    public override double Evaluate(Hashtable vars) {
        object value = vars[name];
        if (value == null) {
            throw new Exception("Unknown variable: " + name);
        }
        return Convert.ToDouble(value);
    }
}

public class Operation: Expression
{
    Expression left;
    char op;
    Expression right;

    public Operation(Expression left, char op, Expression right) {
        this.left = left;
        this.op = op;
        this.right = right;
    }

    public override double Evaluate(Hashtable vars) {
        double x = left.Evaluate(vars);
        double y = right.Evaluate(vars);
        switch (op) {
            case '+': return x + y;
            case '-': return x - y;
            case '*': return x * y;
            case '/': return x / y;
        }
        throw new Exception("Unknown operator");
    }
}
```

上面的这四个类可以用来表示数学运算的模型。例如，使用这些类的实例，表达式`x + 3`可以被表示为：

```csharp
Expression e = new Operation(
    new VariableReference("x"),
    '+',
    new Constant(3));
```

`Expression`实例的`Evaluate`方法在被调用的时候，会对给定的表达式进行求值，并产生一个`double`值。这个方法以一个`Hashtable`实例为实际参数，`Hashtable`实例里容纳了变量的名字（元素实体的键）和值（元素实体的值）。`Evaluate`方法是一个抽象方法，这意味着，非抽象的派生类必须重写之、为之提供一个真正的实现。

`Constant`类中对`Evaluate`方法的实现只是简单地返还所存储的常量。`VariableReference`类中的实现会在先在哈希表中查找变量的名字，然后返还查找到的值。`Operation`类的实现会先对左右两边的操作数进行求值（方法是递归地调用它们的`Evaluate`方法），然后执行给定的算数运算。

下面的程序使用了`Expression`类对表达式`x * (y + 2)`进行求值，`x`与`y`的值不相同。

```csharp
using System;
using System.Collections;

class Test
{
    static void Main() {
        Expression e = new Operation(
            new VariableReference("x"),
            '*',
            new Operation(
                new VariableReference("y"),
                '+',
                new Constant(2)
            )
        );
        Hashtable vars = new Hashtable();
        vars["x"] = 3;
        vars["y"] = 5;
        Console.WriteLine(e.Evaluate(vars));        // 输出"21"
        vars["x"] = 1.5;
        vars["y"] = 9;
        Console.WriteLine(e.Evaluate(vars));        // 输出"16.5"
    }
}
```

#### Method overloading

Method ***overloading*** permits multiple methods in the same class to have the same name as long as they have unique signatures. When compiling an invocation of an overloaded method, the compiler uses ***overload resolution*** to determine the specific method to invoke. Overload resolution finds the one method that best matches the arguments or reports an error if no single best match can be found. The following example shows overload resolution in effect. The comment for each invocation in the `Main` method shows which method is actually invoked.

```csharp
class Test
{
    static void F() {
        Console.WriteLine("F()");
    }

    static void F(object x) {
        Console.WriteLine("F(object)");
    }

    static void F(int x) {
        Console.WriteLine("F(int)");
    }

    static void F(double x) {
        Console.WriteLine("F(double)");
    }

    static void F<T>(T x) {
        Console.WriteLine("F<T>(T)");
    }

    static void F(double x, double y) {
        Console.WriteLine("F(double, double)");
    }

    static void Main() {
        F();                 // Invokes F()
        F(1);                // Invokes F(int)
        F(1.0);              // Invokes F(double)
        F("abc");            // Invokes F(object)
        F((double)1);        // Invokes F(double)
        F((object)1);        // Invokes F(object)
        F<int>(1);           // Invokes F<T>(T)
        F(1, 1);             // Invokes F(double, double)
    }
}
```
As shown by the example, a particular method can always be selected by explicitly casting the arguments to the exact parameter types and/or explicitly supplying type arguments.

方法的**重载**（overloading）允许同一个类中的多个方法具有相当的名字——只要它们的签名是唯一的即可。当编译一个对重载方法的调用时，编译器会使用**重载解析**（overload resolution）来决定具体会调用哪个方法。重载解析会找到那个与实际参数最匹配的那个方法，如果没找到这个唯一匹配的方法，那么就会报告一个错误。下面的例子展示了重载解析是如何起作用的。`Main`方法中对每个调用的注释说明了具体哪个方法被调用了。

```csharp
class Test
{
    static void F() {
        Console.WriteLine("F()");
    }

    static void F(object x) {
        Console.WriteLine("F(object)");
    }

    static void F(int x) {
        Console.WriteLine("F(int)");
    }

    static void F(double x) {
        Console.WriteLine("F(double)");
    }

    static void F<T>(T x) {
        Console.WriteLine("F<T>(T)");
    }

    static void F(double x, double y) {
        Console.WriteLine("F(double, double)");
    }

    static void Main() {
        F();                 // 调用F()
        F(1);                // 调用F(int)
        F(1.0);              // 调用F(double)
        F("abc");            // 调用F(object)
        F((double)1);        // 调用F(double)
        F((object)1);        // 调用F(object)
        F<int>(1);           // 调用F<T>(T)
        F(1, 1);             // 调用F(double, double)
    }
}
```

如例子所示，通过把实际参数显式地转换成形式参数的确切类型，和/或显式提供类型参数（译注：指的是泛型方法），总是能够选中一个特定的方法。

### Other function members | 其他函数成员

Members that contain executable code are collectively known as the ***function members*** of a class. The preceding section describes methods, which are the primary kind of function members. This section describes the other kinds of function members supported by C#: constructors, properties, indexers, events, operators, and destructors.

The following code shows a generic class called `List<T>`, which implements a growable list of objects. The class contains several examples of the most common kinds of function members.

```csharp
public class List<T> {
    // Constant...
    const int defaultCapacity = 4;

    // Fields...
    T[] items;
    int count;

    // Constructors...
    public List(int capacity = defaultCapacity) {
        items = new T[capacity];
    }

    // Properties...
    public int Count {
        get { return count; }
    }
    public int Capacity {
        get {
            return items.Length;
        }
        set {
            if (value < count) value = count;
            if (value != items.Length) {
                T[] newItems = new T[value];
                Array.Copy(items, 0, newItems, 0, count);
                items = newItems;
            }
        }
    }

    // Indexer...
    public T this[int index] {
        get {
            return items[index];
        }
        set {
            items[index] = value;
            OnChanged();
        }
    }

    // Methods...
    public void Add(T item) {
        if (count == Capacity) Capacity = count * 2;
        items[count] = item;
        count++;
        OnChanged();
    }
    protected virtual void OnChanged() {
        if (Changed != null) Changed(this, EventArgs.Empty);
    }
    public override bool Equals(object other) {
        return Equals(this, other as List<T>);
    }
    static bool Equals(List<T> a, List<T> b) {
        if (a == null) return b == null;
        if (b == null || a.count != b.count) return false;
        for (int i = 0; i < a.count; i++) {
            if (!object.Equals(a.items[i], b.items[i])) {
                return false;
            }
        }
        return true;
    }

    // Event...
    public event EventHandler Changed;

    // Operators...
    public static bool operator ==(List<T> a, List<T> b) {
        return Equals(a, b);
    }
    public static bool operator !=(List<T> a, List<T> b) {
        return !Equals(a, b);
    }
}
```

在类中，包含有可执行代码的成员被统称为**函数成员**（funtion members）。前面的段落里描述了方法。方法是最主要的函数成员。本段落将描述C#所支持的其他种类的函数成员，包括：构造器、属性、索引器、事件、操作符、和析构器。

下面的代码展示了名为`List<T>`的泛型类，它实现了一列可增长的对象。这个类包含了几类最常用函数成员的例子。

```csharp
public class List<T> {
    // 常量（译注：不是函数成员）...
    const int defaultCapacity = 4;

    // 字段（译注：不是函数成员）...
    T[] items;
    int count;

    // 构造器（译注：实例构造器，是函数成员）...
    public List(int capacity = defaultCapacity) {
        items = new T[capacity];
    }

    // 属性（译注：实例属性是函数成员，静态属性也是）...
    public int Count {
        get { return count; }
    }
    public int Capacity {
        get {
            return items.Length;
        }
        set {
            if (value < count) value = count;
            if (value != items.Length) {
                T[] newItems = new T[value];
                Array.Copy(items, 0, newItems, 0, count);
                items = newItems;
            }
        }
    }

    // 索引器（译注：实例属性是函数成员，没有静态索引器）...
    public T this[int index] {
        get {
            return items[index];
        }
        set {
            items[index] = value;
            OnChanged();
        }
    }

    // 方法（译注：最典型的函数成员）...
    public void Add(T item) {
        if (count == Capacity) Capacity = count * 2;
        items[count] = item;
        count++;
        OnChanged();
    }
    protected virtual void OnChanged() {
        if (Changed != null) Changed(this, EventArgs.Empty);
    }
    public override bool Equals(object other) {
        return Equals(this, other as List<T>);
    }
    static bool Equals(List<T> a, List<T> b) {
        if (a == null) return b == null;
        if (b == null || a.count != b.count) return false;
        for (int i = 0; i < a.count; i++) {
            if (!object.Equals(a.items[i], b.items[i])) {
                return false;
            }
        }
        return true;
    }

    // 事件（译注：事件是函数成员，类似于属性）...
    public event EventHandler Changed;

    // 操作符（译注：操作符是函数的简记法，因此也是函数成员）...
    public static bool operator ==(List<T> a, List<T> b) {
        return Equals(a, b);
    }
    public static bool operator !=(List<T> a, List<T> b) {
        return !Equals(a, b);
    }
}
```

#### Constructors | 构造器

C# supports both instance and static constructors. An ***instance constructor*** is a member that implements the actions required to initialize an instance of a class. A ***static constructor*** is a member that implements the actions required to initialize a class itself when it is first loaded.

A constructor is declared like a method with no return type and the same name as the containing class. If a constructor declaration includes a `static` modifier, it declares a static constructor. Otherwise, it declares an instance constructor.

Instance constructors can be overloaded. For example, the `List<T>` class declares two instance constructors, one with no parameters and one that takes an `int` parameter. Instance constructors are invoked using the `new` operator. The following statements allocate two `List<string>` instances using each of the constructors of the `List` class.

```csharp
List<string> list1 = new List<string>();
List<string> list2 = new List<string>(10);
```
Unlike other members, instance constructors are not inherited, and a class has no instance constructors other than those actually declared in the class. If no instance constructor is supplied for a class, then an empty one with no parameters is automatically provided.

C#既支持**实例构造器**（instance constructor）也支持**静态构造器**（static constructor）。实例构造器，作为一个成员，它实现了实例在被初始化的时候所要求执行的动作。静态构造器，作为一个成员，它实现了一个类被首次加载时被要求执行的动作。

构造器的声明看上去很像方法的声明，只是没有返回值类型，而且构造器的名字也必须与包含它的类名保持一致。如果构造器的声明中包含有`static`修饰符，那么它声明的是一个静态构造器。否则，它声明的就是一个实例构造器。

实例构造器是可被重载的。例如，下面的`List<T>`类声明了两个实例构造器，一个不带参数，另一个能接受一个`int`类型的参数。实例构造器通过`new`操作符来调用（译注：程序员没机会直接调用构造器，包括在使用反射的时候）。下面的例子中分别使用`List`类的两个实例构造器分配了两个`List<string>`的实例。

```csharp
List<string> list1 = new List<string>();
List<string> list2 = new List<string>(10);
```

与其他成员不同，实例构造器不会被继承，所以，除了那些在真正被声明的构造器之外，类中不会具有其他的构造器。如果没有为一个类提供实例构造器，那么一个空的、不带参数的实例构造器就会被自动生成。

#### Properties | 属性

***Properties*** are a natural extension of fields. Both are named members with associated types, and the syntax for accessing fields and properties is the same. However, unlike fields, properties do not denote storage locations. Instead, properties have ***accessors*** that specify the statements to be executed when their values are read or written.

A property is declared like a field, except that the declaration ends with a `get` accessor and/or a `set` accessor written between the delimiters `{` and `}` instead of ending in a semicolon. A property that has both a `get` accessor and a `set` accessor is a ***read-write property***, a property that has only a `get` accessor is a ***read-only property***, and a property that has only a `set` accessor is a ***write-only property***.

A `get` accessor corresponds to a parameterless method with a return value of the property type. Except as the target of an assignment, when a property is referenced in an expression, the `get` accessor of the property is invoked to compute the value of the property.

A `set` accessor corresponds to a method with a single parameter named `value` and no return type. When a property is referenced as the target of an assignment or as the operand of `++` or `--`, the `set` accessor is invoked with an argument that provides the new value.

The `List<T>` class declares two properties, `Count` and `Capacity`, which are read-only and read-write, respectively. The following is an example of use of these properties.

```csharp
List<string> names = new List<string>();
names.Capacity = 100;            // Invokes set accessor
int i = names.Count;             // Invokes get accessor
int j = names.Capacity;          // Invokes get accessor
```
Similar to fields and methods, C# supports both instance properties and static properties. Static properties are declared with the `static` modifier, and instance properties are declared without it.

The accessor(s) of a property can be virtual. When a property declaration includes a `virtual`, `abstract`, or `override` modifier, it applies to the accessor(s) of the property.

**属性**（properties）是字段的自然延伸（译注：擦，好有哲学意境！）。它们都是有名字的成员、都有与之相关联的类型，而且访问它们时的语法也是一样的（译注：甚至包括++、--这样的操作符）。 然而，与字段不同，属性并不意味着存储空间。相反，属性具有**访问器**（accessors）用以指定当对其读取或写入值时会被执行的语句。

属性的声明看上去很像字段，不同的是属性的声明中会以放在一对花括号（`{`和`}` ）中的`get`访问器和/或`set`访问器来结束，而不是以一个分号（`;`）来结束。即带有`get`访问器又带有`set`访问器的属性称为**读写属性**（read-write property）；只有`get`访问器的属性称为**只读属性**（read-only property）；只有`set`访问器的属性称为**只写属性**（write-only property）。（译注：在实际工作中从来没使用过只写属性。）

`get`访问器对应于一个没有参数的方法，这个方法会返还一个与属性类型一致的值。在不被作为赋值目标的时候，当一个属性在表达式中被引用时，属性的`get`访问器就会被调用并计算出属性的值。（译注：从属性身上读取值的时候，`get`就会被调用。反之，向属性赋值、写入值的时候，`get`就会被调用。）

`set`访问器也对应于一个方法，这个方法带有一个名为`value`的参数而且没有返还值类型。当一个属性被当作赋值的目标或者`++`、`--`操作符的操作数时`set`访问器就会被调用，并且会由一个实际参数提供属性的新值（译注：新值就保存在`value`里，`value`是一个上下文关键字）。

`List<T>`类声明了两个属性，`Count`和`Capacity`，`Count`是只读属性，`Capacity`是读写属性。下面的例子中展示了如何使用这两个属性：

```csharp
List<string> names = new List<string>();
names.Capacity = 100;            // 调用`set`访问器
int i = names.Count;             // 调用`get`访问器
int j = names.Capacity;          // 调用`get`访问器
```

与字段和方法类似，C#既支持实例属性也支持静态属性。静态属性的声明带有`static`修饰符，而实例属性的声明则不带`static`修饰符。

属性的访问器可以是虚的。当属性的声明带有`virtual`、`abstract`或`override`修饰符的时候，即为这种情况。

#### Indexers | 索引器

An ***indexer*** is a member that enables objects to be indexed in the same way as an array. An indexer is declared like a property except that the name of the member is `this` followed by a parameter list written between the delimiters `[` and `]`. The parameters are available in the accessor(s) of the indexer. Similar to properties, indexers can be read-write, read-only, and write-only, and the accessor(s) of an indexer can be virtual.

The `List` class declares a single read-write indexer that takes an `int` parameter. The indexer makes it possible to index `List` instances with `int` values. For example

```csharp
List<string> names = new List<string>();
names.Add("Liz");
names.Add("Martha");
names.Add("Beth");
for (int i = 0; i < names.Count; i++) {
    string s = names[i];
    names[i] = s.ToUpper();
}
```
Indexers can be overloaded, meaning that a class can declare multiple indexers as long as the number or types of their parameters differ.

**索引器**（indexer）这种成员能够让对象像被数组一样被索引。索引器的声明很像属性，但索引器的名字必须是`this`，并在后面跟上放在一对方括号（`[`和`]`）中的参数列表。这些参数可以在访问器中被使用。与属性类似，索引器也可以是读写的、只读的或只写的，而且索引器的访问器可以是虚的。

`List`类声明的唯一一个索引器可以接收一个`int`类型参数。这个索引器使得`List`的实例可以使用`int`值进行索引。如下面的例子：

```csharp
List<string> names = new List<string>();
names.Add("Liz");
names.Add("Martha");
names.Add("Beth");
for (int i = 0; i < names.Count; i++) {
    string s = names[i];
    names[i] = s.ToUpper();
}
```

索引器可以被重载，也就是说，一个类可以声明多个索引器，只要索引器参数的个数或类型不同即可。（译注：我还真没见过多个参数的索引器，回头搞一个玩玩儿。）

#### Events | 事件

An ***event*** is a member that enables a class or object to provide notifications. An event is declared like a field except that the declaration includes an `event` keyword and the type must be a delegate type.

Within a class that declares an event member, the event behaves just like a field of a delegate type (provided the event is not abstract and does not declare accessors). The field stores a reference to a delegate that represents the event handlers that have been added to the event. If no event handles are present, the field is `null`.

The `List<T>
` class declares a single event member called `Changed`, which indicates that a new item has been added to the list. The `Changed` event is raised by the `OnChanged` virtual method, which first checks whether the event is `null` (meaning that no handlers are present). The notion of raising an event is precisely equivalent to invoking the delegate represented by the event—thus, there are no special language constructs for raising events.

**事件**（event）这种成员使得类或对象具备了通知（其他类或对象）的能力。事件的声明很像一个字段，但事件的声明中会带有`event`关键字，而且必须是委托类型的。

在声明有事件的类中，事件的行为很像一个委托类型的字段（这种声明方式不能用于声明抽象事件，也不必提供事件的访问器）（译注：事件的完整声明的确用的不多）。这个字段存储着一个对委托（实例）的引用，而这个委托实例则代表着被分配给事件的事件的处理器。如果事件处理器不存在，那么这个委托字段的值为`null`。

Clients react to events through ***event handlers***. Event handlers are attached using the `+=` operator and removed using the `-=` operator. The following example attaches an event handler to the `Changed` event of a `List<string>`.

```csharp
using System;

class Test
{
    static int changeCount;

    static void ListChanged(object sender, EventArgs e) {
        changeCount++;
    }

    static void Main() {
        List<string> names = new List<string>();
        names.Changed += new EventHandler(ListChanged);
        names.Add("Liz");
        names.Add("Martha");
        names.Add("Beth");
        Console.WriteLine(changeCount);        // Outputs "3"
    }
}
```
For advanced scenarios where control of the underlying storage of an event is desired, an event declaration can explicitly provide `add` and `remove` accessors, which are somewhat similar to the `set` accessor of a property.

事件的客户（译注：也叫“订阅者”）通过**事件处理器**（event handlers）来对事件做出反应（译注：又称“响应事件”）。使用`+=`操作符可以为事件添加事件处理器，使用`-=`操作符则可以移除事件处理器。下面的例子展示了如何将一个事件处理器附加到了`List<string>`的`Changed`事件上：

```csharp
using System;

class Test
{
    static int changeCount;

    static void ListChanged(object sender, EventArgs e) {
        changeCount++;
    }

    static void Main() {
        List<string> names = new List<string>();
        names.Changed += new EventHandler(ListChanged);
        names.Add("Liz");
        names.Add("Martha");
        names.Add("Beth");
        Console.WriteLine(changeCount);        // 输出"3"
    }
}
```

在遇到某些高级场景时，我们可以在事件的声明中控制底层（委托字段）的存储，方法是在事件的声明中显式地提供`add`和`remove`访问器——它们有点类似于属性的`set`访问器。

#### Operators | 操作符

An ***operator*** is a member that defines the meaning of applying a particular expression operator to instances of a class. Three kinds of operators can be defined: unary operators, binary operators, and conversion operators. All operators must be declared as `public` and `static`.

The `List<T>` class declares two operators, `operator==` and `operator!=`, and thus gives new meaning to expressions that apply those operators to `List` instances. Specifically, the operators define equality of two `List<T>` instances as comparing each of the contained objects using their `Equals` methods. The following example uses the `==` operator to compare two `List<int>` instances.

```csharp
using System;

class Test
{
    static void Main() {
        List<int> a = new List<int>();
        a.Add(1);
        a.Add(2);
        List<int> b = new List<int>();
        b.Add(1);
        b.Add(2);
        Console.WriteLine(a == b);        // Outputs "True"
        b.Add(3);
        Console.WriteLine(a == b);        // Outputs "False"
    }
}
```

The first `Console.WriteLine` outputs `True` because the two lists contain the same number of objects with the same values in the same order. Had `List<T>` not defined `operator==`, the first `Console.WriteLine` would have output `False` because `a` and `b` reference different `List<int>` instances.

**操作符**（operator）这种成员定义了当某种表达式操作符应用在类的实例上时的意义。我们可以定义三种操作符：单目操作符（unary operators）、双目操作符（binary operators）和类型转换操作符（conversion operators）。所有操作符都必须被声明为`public`和`static`的。

`List<T>`类声明了两个操作符，`operator==`和`operator!=`，借此给出了将这些操作符应用在`List`实例上时表达式所具有的新的意义。具体而言，这两个操作符定义了两个`List<T>`实例的相等性是通过调用所包含元素的`Equals`方法、比较每个元素对象而得来的。下面的例子展示了如何使用`==`操作符来比较两个`List<int>`的实例：

```csharp
using System;

class Test
{
    static void Main() {
        List<int> a = new List<int>();
        a.Add(1);
        a.Add(2);
        List<int> b = new List<int>();
        b.Add(1);
        b.Add(2);
        Console.WriteLine(a == b);        // 输出"True"
        b.Add(3);
        Console.WriteLine(a == b);        // 输出"False"
    }
}
```

第一个`Console.WriteLine`的输出为`True`，因为两个`List`实例中包含了同样多个对象，而且这些对象的值和顺序都是一样的。如果`List<T>`没有定义`operator==`，那么第一个`Console.WriteLine`就会输出`False`，因为`a`和`b`引用着两个不同的`List<int>`实例。

#### Destructors | 析构器

A ***destructor*** is a member that implements the actions required to destruct an instance of a class. Destructors cannot have parameters, they cannot have accessibility modifiers, and they cannot be invoked explicitly. The destructor for an instance is invoked automatically during garbage collection.

The garbage collector is allowed wide latitude in deciding when to collect objects and run destructors. Specifically, the timing of destructor invocations is not deterministic, and destructors may be executed on any thread. For these and other reasons, classes should implement destructors only when no other solutions are feasible.

The `using` statement provides a better approach to object destruction.

**析构器**这种成员实现了类的实例在被销毁时需要执行的动作。析构器既不能带有参数也没有可访问性修饰符，而且不能显式地被调用。实例的析构器会在垃圾收集期间被自动调用。

垃圾收集器在决定何时收集对象并执行析构器方面具有很大的自由度。具体来说就是，析构器器被调用的时机是不确定的，而且有可能在被任何线程中初调用。介于这些以及其他的原因，仅当没有其他合适的解决方案时，类才会考虑实现析构器。

## Structs | 结构体

Like classes, ***structs*** are data structures that can contain data members and function members, but unlike classes, structs are value types and do not require heap allocation. A variable of a struct type directly stores the data of the struct, whereas a variable of a class type stores a reference to a dynamically allocated object. Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type `object`.

Structs are particularly useful for small data structures that have value semantics. Complex numbers, points in a coordinate system, or key-value pairs in a dictionary are all good examples of structs. The use of structs rather than classes for small data structures can make a large difference in the number of memory allocations an application performs. For example, the following program creates and initializes an array of 100 points. With `Point` implemented as a class, 101 separate objects are instantiated—one for the array and one each for the 100 elements.

```csharp
class Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}

class Test
{
    static void Main() {
        Point[] points = new Point[100];
        for (int i = 0; i < 100; i++) points[i] = new Point(i, i);
    }
}
```
An alternative is to make `Point` a struct.

```csharp
struct Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
```
Now, only one object is instantiated—the one for the array—and the `Point` instances are stored in-line in the array.

与类类似，**结构体**（structs）也是一种可以容纳数据成员和函数成员的数据结构；但与类不同的是，结构体是值类型，并且不要求在堆上进行（为对象）分配（内存）。结构体类型的变量会直接存储结构体数据，而类类型的变量存储的则是对动态分配的对象的引用。结构体类型不支持用户自定义的继承，并且，所有结构体类型都隐式地继承了`object`类型。

特别是对于那些具有值语义（???）的小型数据类型，结构体十分有用。复杂的数字、坐标系中的点、以及字典中的键-值对，都是结构体很好的例子。针对小型数据类型使用结构体而非类，会在程序运行时内存分配大小方面产生巨大的不同。例如，在下面的程序创建并初始化了包含有100个点的数组。如果把`Point`实现成一个类，那么就会创建101个独立的对象——数组本身是一个对象，还要为每个数组元素创建一个对象。

```csharp
class Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}

class Test
{
    static void Main() {
        Point[] points = new Point[100];
        for (int i = 0; i < 100; i++) points[i] = new Point(i, i);
    }
}
```

但如果把`Point`转换成结构体，

```csharp
struct Point
{
    public int x, y;

    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
```

此时就只有一个对象被实例化了——即那个数组对象——`Point`的实例们则是就地存储在数组实例里。

Struct constructors are invoked with the `new` operator, but that does not imply that memory is being allocated. Instead of dynamically allocating an object and returning a reference to it, a struct constructor simply returns the struct value itself (typically in a temporary location on the stack), and this value is then copied as necessary.

With classes, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable. With structs, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other. For example, the output produced by the following code fragment depends on whether `Point` is a class or a struct.

```csharp
Point a = new Point(10, 10);
Point b = a;
a.x = 20;
Console.WriteLine(b.x);
```
If `Point` is a class, the output is `20` because `a` and `b` reference the same object. If `Point` is a struct, the output is `10` because the assignment of `a` to `b` creates a copy of the value, and this copy is unaffected by the subsequent assignment to `a.x`.

The previous example highlights two of the limitations of structs. First, copying an entire struct is typically less efficient than copying an object reference, so assignment and value parameter passing can be more expensive with structs than with reference types. Second, except for `ref` and `out` parameters, it is not possible to create references to structs, which rules out their usage in a number of situations.

结构体的构造器会随着`new`操作符的使用而被调用，但这并不意味着会有（对象所占用的）内存被分配。与（对引用类型使用`new`操作符会）动态分配对象并返还一个对象的引用不同，结构体的构造器会返还值本身（通常是一个位于栈上的临时存储位置）（译注：构造器啥时候有返回值了？创建对象不是`new`的事儿吗？），随后这个值会在必要的时候被拷贝（译注：装箱的时候）。

使用类的时候，允许两个变量引用着同一个对象，所以可以通过操作一个变量来影响到由另一个变量所引用着的对象（译注：因为两个变量引用的是同一个对象）。当使用结构体的时候，每个变量都拥有属于自己的（独立的）数据拷贝，所以不可能发生操作一个变量而影响到另一个的情况了。例如，下面的代码所产生的输出就取决于`Point`是类还是结构体：

```csharp
Point a = new Point(10, 10);
Point b = a;
a.x = 20;
Console.WriteLine(b.x);
```

如果`Point`是类，那么输出会是`20`，因为`a`和`b`引用的是同一个对象。如果`Point`是结构体，那么输入会是`10`，因为由`a`向`b`的赋值会创建（`a`中）值的一个拷贝，并且这个拷贝不会被后续对`a.x`的赋值所影响。

前面这个例子同时也指出了结构体的两个局限性。首先，复制整个结构体（对象）明显不如仅复制一个对象引用效率高，所以，结构体之间的赋值和值参数传递明显要比引用类型之间的代替高。其次，抛开`ref`和`out`参数不谈，（目前还）无法创建对结构体（值/对象）的引用，因此结构体在很多情况下就不适用了。

## Arrays | 数组

An ***array*** is a data structure that contains a number of variables that are accessed through computed indices. The variables contained in an array, also called the ***elements*** of the array, are all of the same type, and this type is called the ***element type*** of the array.

Array types are reference types, and the declaration of an array variable simply sets aside space for a reference to an array instance. Actual array instances are created dynamically at run-time using the `new` operator. The `new` operation specifies the ***length*** of the new array instance, which is then fixed for the lifetime of the instance. The indices of the elements of an array range from `0` to `Length - 1`. The `new` operator automatically initializes the elements of an array to their default value, which, for example, is zero for all numeric types and `null` for all reference types.

**数组**（array）是一种能够容纳多个变量的数据结构，这些变量可以通过计算出来的索引来访问。数组中所包含的变量又被称为数组的**元素**（elements），它们的类型是相同的，这个类型被称为数组的**元素类型**（element type）。

数组类型是引用类型(译注：因为是类啊！)，所以数组变量的声明只会得到足以容纳一个对数组实例的引用所需的空间。真正的数组实例是在运行时被`new`操作符创建的。`new`操作符指定了新的数组实例的**长度**（length）。在数组对象的整个生命周期中，它的长度是固定不变的。数组元素索引的范围是`0`到`Length - 1`（译注：长度减1，或者说元素个数减1）。`new`操作符会自动将元素的值初始化为它们的默认值（译注：参见`default`操作符），这意味着，对于所有数字类型来说是零（译注：整数的话是`0`，浮点数的话是`0.0`），对于引用类型来说是`null`（译注：即内存清零）。

The following example creates an array of `int` elements, initializes the array, and prints out the contents of the array.

```csharp
using System;

class Test
{
    static void Main() {
        int[] a = new int[10];
        for (int i = 0; i < a.Length; i++) {
            a[i] = i * i;
        }
        for (int i = 0; i < a.Length; i++) {
            Console.WriteLine("a[{0}] = {1}", i, a[i]);
        }
    }
}
```
This example creates and operates on a ***single-dimensional array***. C# also supports ***multi-dimensional arrays***. The number of dimensions of an array type, also known as the ***rank*** of the array type, is one plus the number of commas written between the square brackets of the array type. The following example allocates a one-dimensional, a two-dimensional, and a three-dimensional array.

```csharp
int[] a1 = new int[10];
int[,] a2 = new int[10, 5];
int[,,] a3 = new int[10, 5, 2];
```
The `a1` array contains 10 elements, the `a2` array contains 50 (10 × 5) elements, and the `a3` array contains 100 (10 × 5 × 2) elements.

The element type of an array can be any type, including an array type. An array with elements of an array type is sometimes called a ***jagged array*** because the lengths of the element arrays do not all have to be the same. The following example allocates an array of arrays of `int`:

```csharp
int[][] a = new int[3][];
a[0] = new int[10];
a[1] = new int[5];
a[2] = new int[20];
```
The first line creates an array with three elements, each of type `int[]` and each with an initial value of `null`. The subsequent lines then initialize the three elements with references to individual array instances of varying lengths.

The `new` operator permits the initial values of the array elements to be specified using an ***array initializer***, which is a list of expressions written between the delimiters `{` and `}`. The following example allocates and initializes an `int[]` with three elements.

```csharp
int[] a = new int[] {1, 2, 3};
```
Note that the length of the array is inferred from the number of expressions between `{` and `}`. Local variable and field declarations can be shortened further such that the array type does not have to be restated.

```csharp
int[] a = {1, 2, 3};
```
Both of the previous examples are equivalent to the following:

```csharp
int[] t = new int[3];
t[0] = 1;
t[1] = 2;
t[2] = 3;
int[] a = t;
```

下面的例子创建了一个元素为`int`的数组，然后初始化了这个数组，最后把这个数组中的内容打印了出来。

```csharp
using System;

class Test
{
    static void Main() {
        int[] a = new int[10];
        for (int i = 0; i < a.Length; i++) {
            a[i] = i * i;
        }
        for (int i = 0; i < a.Length; i++) {
            Console.WriteLine("a[{0}] = {1}", i, a[i]);
        }
    }
}
```

This example creates and operates on a ***single-dimensional array***. C# also supports ***multi-dimensional arrays***. The number of dimensions of an array type, also known as the ***rank*** of the array type, is one plus the number of commas written between the square brackets of the array type. The following example allocates a one-dimensional, a two-dimensional, and a three-dimensional array.

这个例子创建并操作的是一个**一维数组**（single-dimensional array）。C#也支持**多维数组**（multi-dimensional arrays）（译注：是真正的多维数组哦！）。数组类型的维度数，也称数组类型的**级**（rank），等于方括号中的逗号数量加一。下面的例子分配了一个一维数组、一个二维数组、和一个三维数组。

```csharp
int[] a1 = new int[10];
int[,] a2 = new int[10, 5];
int[,,] a3 = new int[10, 5, 2];
```

数组`a1`包含有10个元素，数组`a2`包含有50个元素（10 × 5），数组`a3`包含100个元素（10 × 5 × 2）。

数组元素的类型可以是任意的，包括数组类型。元素也是数组类型的数组，被称为**锯齿状数组**（jugged array），因为作为元素的数组不一定都具有相同的长度。下面的例子分配了一个数组，这个数组的元素是元素为`int`的数组：

```csharp
int[][] a = new int[3][];
a[0] = new int[10];
a[1] = new int[5];
a[2] = new int[20];
```

代码的第一行创建了一个具有三个元素的数组，每个元素的类型都是`int[]`且初始值为`null`。接下来的代码将对不同长度数组实例的引用赋值给了这三个数组元素（译注：原文不精确，因为这时候已经不是初始化了）。

在创建数组实例的时候，`new`操作符允许使用**数组初始化器**（array initializer）来初始化数组元素的值。数组初始化器是一列放在一对花括号（`{`和`}`）中的表达式（译注：表达式即是值，值即是表达式）。下面的代码分配并用三个元素初始化了一个`int[]`。

```csharp
int[] a = new int[] {1, 2, 3};
```

请注意，数组的长度是由花括号中元素的个数推断出来的。数组类型的局部变量和字段的声明可以变得更短，方法是省略对数组类型的重复：

```csharp
int[] a = {1, 2, 3};
```

前面这两个例子都等价于下面这个例子（译注：感觉有点儿画蛇添足）：


```csharp
int[] t = new int[3];
t[0] = 1;
t[1] = 2;
t[2] = 3;
int[] a = t;
```

（译注：应该在这里展示一下多维数组的初始化。）

## Interfaces | 接口

An ***interface*** defines a contract that can be implemented by classes and structs. An interface can contain methods, properties, events, and indexers. An interface does not provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.

Interfaces may employ ***multiple inheritance***. In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.

```csharp
interface IControl
{
    void Paint();
}

interface ITextBox: IControl
{
    void SetText(string text);
}

interface IListBox: IControl
{
    void SetItems(string[] items);
}

interface IComboBox: ITextBox, IListBox {}
```
Classes and structs can implement multiple interfaces. In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.

```csharp
interface IDataBound
{
    void Bind(Binder b);
}

public class EditBox: IControl, IDataBound
{
    public void Paint() {...}
    public void Bind(Binder b) {...}
}
```
When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type. For example

```csharp
EditBox editBox = new EditBox();
IControl control = editBox;
IDataBound dataBound = editBox;
```
In cases where an instance is not statically known to implement a particular interface, dynamic type casts can be used. For example, the following statements use dynamic type casts to obtain an object's `IControl` and `IDataBound` interface implementations. Because the actual type of the object is `EditBox`, the casts succeed.

```csharp
object obj = new EditBox();
IControl control = (IControl)obj;
IDataBound dataBound = (IDataBound)obj;
```
In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using `public` members. C# also supports ***explicit interface member implementations***, using which the class or struct can avoid making the members `public`. An explicit interface member implementation is written using the fully qualified interface member name. For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.

```csharp
public class EditBox: IControl, IDataBound
{
    void IControl.Paint() {...}
    void IDataBound.Bind(Binder b) {...}
}
```
Explicit interface members can only be accessed via the interface type. For example, the implementation of `IControl.Paint` provided by the previous `EditBox` class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.

```csharp
EditBox editBox = new EditBox();
editBox.Paint();                        // Error, no such method
IControl control = editBox;
control.Paint();                        // Ok
```

**接口**定义了可被类和结构体实现的契约。接口可以包含方法、属性、事件、和索引器。在定义接口的时候，不必提供成员的实现（译注：C#新版有默认实现）。这些成员基本上勾勒出了当类或结构体实现这个接口的时候所必须实现的成员的一个轮廓。

接口可以进行**多继承**。下面的例子中，`IComboBox`接口就继承了`ITextBox`和`IListBox`两个接口（译注：接口之间叫“继承”，接口与类之间叫“实现”）。

```csharp
interface IControl
{
    void Paint();
}

interface ITextBox: IControl
{
    void SetText(string text);
}

interface IListBox: IControl
{
    void SetItems(string[] items);
}

interface IComboBox: ITextBox, IListBox {}
```

类和结构体可以实现多个接口。下面的例子中，`EditBox`类就实现了`IControl`和`IDataBound`两个接口。

```csharp
interface IDataBound
{
    void Bind(Binder b);
}

public class EditBox: IControl, IDataBound
{
    public void Paint() {...}
    public void Bind(Binder b) {...}
}
```

当一个类或结构体实现了某个接口的时候，这个类或结构体的实例可以被隐式地转换成此接口类型（译注：“是一个”原则）。例如：

```csharp
EditBox editBox = new EditBox();
IControl control = editBox;
IDataBound dataBound = editBox;
```

当一个实例不能静态地得知是否实现了某个接口的时候，那就需要借助动态类型转换了（译注：其实就是显式类型转换）。例如，在下面的例子就进行了动态类型转换，从而获取到对象对`IControl`和`IDataBound`两个接口的实现。因为对象的类型是`EditBox`，所以这次类型转换是成功的。（译注：这种“硬转换”在实际工作中是不推荐的，而是应该使用`is`或`as`操作符。）

```csharp
object obj = new EditBox();
IControl control = (IControl)obj;
IDataBound dataBound = (IDataBound)obj;
```

在前面的例子中，`EditBox`类中来自`IControl`接口的`Paint`方法和来自`IDataBound`接口的`Bind`方法均被实现为了`public`成员。C#同时也支持**显式接口成员实现**，以避免接口成员成为`public`的。显式接口成员实现在书写的时候必需使用全限定名来书写接口的成员。如后面的例子所示，`EditBox`类可以使用显式成员实现的方式来实现`IControl.Paint`和`IDataBound.Bind`方法：

```csharp
public class EditBox: IControl, IDataBound
{
    void IControl.Paint() {...}
    void IDataBound.Bind(Binder b) {...}
}
```

显式接口成员只能通过接口类型来访问。例如，要访问由`EditBox`类提供的`IControl.Paint`方法则必须先把对`EditBox`的引用（译注：即`EditBox`类型的引用变量）转换成`IControl`接口类型。

```csharp
EditBox editBox = new EditBox();
editBox.Paint();                        // 错误：无此方法
IControl control = editBox;
control.Paint();                        // 正确
```

## Enums | 枚举

An ***enum type*** is a distinct value type with a set of named constants. The following example declares and uses an enum type named `Color` with three constant values, `Red`, `Green`, and `Blue`.

```csharp
using System;

enum Color
{
    Red,
    Green,
    Blue
}

class Test
{
    static void PrintColor(Color color) {
        switch (color) {
            case Color.Red:
                Console.WriteLine("Red");
                break;
            case Color.Green:
                Console.WriteLine("Green");
                break;
            case Color.Blue:
                Console.WriteLine("Blue");
                break;
            default:
                Console.WriteLine("Unknown color");
                break;
        }
    }

    static void Main() {
        Color c = Color.Red;
        PrintColor(c);
        PrintColor(Color.Blue);
    }
}
```
Each enum type has a corresponding integral type called the ***underlying type*** of the enum type. An enum type that does not explicitly declare an underlying type has an underlying type of `int`. An enum type's storage format and range of possible values are determined by its underlying type. The set of values that an enum type can take on is not limited by its enum members. In particular, any value of the underlying type of an enum can be cast to the enum type and is a distinct valid value of that enum type.

The following example declares an enum type named `Alignment` with an underlying type of `sbyte`.

```csharp
enum Alignment: sbyte
{
    Left = -1,
    Center = 0,
    Right = 1
}
```
As shown by the previous example, an enum member declaration can include a constant expression that specifies the value of the member. The constant value for each enum member must be in the range of the underlying type of the enum. When an enum member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the enum type) or the value of the textually preceding enum member plus one.

Enum values can be converted to integral values and vice versa using type casts. For example

```csharp
int i = (int)Color.Blue;        // int i = 2;
Color c = (Color)2;             // Color c = Color.Blue;
```
The default value of any enum type is the integral value zero converted to the enum type. In cases where variables are automatically initialized to a default value, this is the value given to variables of enum types. In order for the default value of an enum type to be easily available, the literal `0` implicitly converts to any enum type. Thus, the following is permitted.

```csharp
Color c = 0;
```

**枚举类型**是一种独特的值类型，它拥有一个由带名字的常量所组成的集合。下面的例子中声明并使用了一个名为`Color`的枚举类型，而且这个枚举类型具有三个常量值：`Red`、`Green`和`Blue`。

```csharp
using System;

enum Color
{
    Red,
    Green,
    Blue
}

class Test
{
    static void PrintColor(Color color) {
        switch (color) {
            case Color.Red:
                Console.WriteLine("Red");
                break;
            case Color.Green:
                Console.WriteLine("Green");
                break;
            case Color.Blue:
                Console.WriteLine("Blue");
                break;
            default:
                Console.WriteLine("Unknown color");
                break;
        }
    }

    static void Main() {
        Color c = Color.Red;
        PrintColor(c);
        PrintColor(Color.Blue);
    }
}
```

每个枚举类型都具有一个相应的整数类型，称为这个枚举类型的**底层类型**。如果一个枚举类型没有明确地声明底层类型，那么它的底层类型就是`int`类型。一个枚举类型值的存储格式和取值范围都由其底层类型决定。枚举类型可以具有的一个集合的值并不受枚举个数的限制。具体来说就是，任意底层类型的值都可以通过类型转换成这一枚举类型的值，并且是此枚举类型的一个独特的值（译注：还真没试过！）。

下面的例子以`sbyte`作为底层类型声明了一个名为`Alignment`的枚举类型。

```csharp
enum Alignment: sbyte
{
    Left = -1,
    Center = 0,
    Right = 1
}
```

如前面例子所示，枚举成员的声明可以包含一个常量表达式用以指定这个成员的值。每个枚举成员的常量值都必须落在底层类型的取值范围内。当一个枚举成员没有被显式地指派一个值的时候，如果它是枚举类型的第一个成员，那么就被赋予零值，否则就按照文本顺序依次在前面的枚举值上加一。

使用显式类型转换，枚举类型的值可以被转换为整数类型的值，反之亦然。如下例所示：

```csharp
int i = (int)Color.Blue;        // int i = 2;
Color c = (Color)2;             // Color c = Color.Blue;
```

枚举类型的默认值就是整数零转换后所对应的枚举值。有的时候，变量会被自动地初始化为一个默认值（译注：比如字段），那么，零值就是赋给枚举类型变量的默认值。为了让枚举类型的默认值便于使用，常值`0`可以被隐式地转换成任何枚举类型（译注：强调是“隐式转换”；另外，一个枚举类型如果没有与零值对应的成员，怎么办？）。因此，下面的代码是允许的：

```csharp
Color c = 0;
```

## Delegates

A ***delegate type*** represents references to methods with a particular parameter list and return type. Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters. Delegates are similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.

The following example declares and uses a delegate type named `Function`.

```csharp
using System;

delegate double Function(double x);

class Multiplier
{
    double factor;

    public Multiplier(double factor) {
        this.factor = factor;
    }

    public double Multiply(double x) {
        return x * factor;
    }
}

class Test
{
    static double Square(double x) {
        return x * x;
    }

    static double[] Apply(double[] a, Function f) {
        double[] result = new double[a.Length];
        for (int i = 0; i < a.Length; i++) result[i] = f(a[i]);
        return result;
    }

    static void Main() {
        double[] a = {0.0, 0.5, 1.0};
        double[] squares = Apply(a, Square);
        double[] sines = Apply(a, Math.Sin);
        Multiplier m = new Multiplier(2.0);
        double[] doubles =  Apply(a, m.Multiply);
    }
}
```
An instance of the `Function` delegate type can reference any method that takes a `double` argument and returns a `double` value. The `Apply` method applies a given `Function` to the elements of a `double[]`, returning a `double[]` with the results. In the `Main` method, `Apply` is used to apply three different functions to a `double[]`.

A delegate can reference either a static method (such as `Square` or `Math.Sin` in the previous example) or an instance method (such as `m.Multiply` in the previous example). A delegate that references an instance method also references a particular object, and when the instance method is invoked through the delegate, that object becomes `this` in the invocation.

Delegates can also be created using anonymous functions, which are "inline methods" that are created on the fly. Anonymous functions can see the local variables of the surrounding methods. Thus, the multiplier example above can be written more easily without using a `Multiplier` class:

```csharp
double[] doubles =  Apply(a, (double x) => x * 2.0);
```
An interesting and useful property of a delegate is that it does not know or care about the class of the method it references; all that matters is that the referenced method has the same parameters and return type as the delegate.

## Attributes

Types, members, and other entities in a C# program support modifiers that control certain aspects of their behavior. For example, the accessibility of a method is controlled using the `public`, `protected`, `internal`, and `private` modifiers. C# generalizes this capability such that user-defined types of declarative information can be attached to program entities and retrieved at run-time. Programs specify this additional declarative information by defining and using ***attributes***.

The following example declares a `HelpAttribute` attribute that can be placed on program entities to provide links to their associated documentation.

```csharp
using System;

public class HelpAttribute: Attribute
{
    string url;
    string topic;

    public HelpAttribute(string url) {
        this.url = url;
    }

    public string Url {
        get { return url; }
    }

    public string Topic {
        get { return topic; }
        set { topic = value; }
    }
}
```
All attribute classes derive from the `System.Attribute` base class provided by the .NET Framework. Attributes can be applied by giving their name, along with any arguments, inside square brackets just before the associated declaration. If an attribute's name ends in `Attribute`, that part of the name can be omitted when the attribute is referenced. For example, the `HelpAttribute` attribute can be used as follows.

```csharp
[Help("http://msdn.microsoft.com/.../MyClass.htm")]
public class Widget
{
    [Help("http://msdn.microsoft.com/.../MyClass.htm", Topic = "Display")]
    public void Display(string text) {}
}
```
This example attaches a `HelpAttribute` to the `Widget` class and another `HelpAttribute` to the `Display` method in the class. The public constructors of an attribute class control the information that must be provided when the attribute is attached to a program entity. Additional information can be provided by referencing public read-write properties of the attribute class (such as the reference to the `Topic` property previously).

The following example shows how attribute information for a given program entity can be retrieved at run-time using reflection.

```csharp
using System;
using System.Reflection;

class Test
{
    static void ShowHelp(MemberInfo member) {
        HelpAttribute a = Attribute.GetCustomAttribute(member,
            typeof(HelpAttribute)) as HelpAttribute;
        if (a == null) {
            Console.WriteLine("No help for {0}", member);
        }
        else {
            Console.WriteLine("Help for {0}:", member);
            Console.WriteLine("  Url={0}, Topic={1}", a.Url, a.Topic);
        }
    }

    static void Main() {
        ShowHelp(typeof(Widget));
        ShowHelp(typeof(Widget).GetMethod("Display"));
    }
}
```
When a particular attribute is requested through reflection, the constructor for the attribute class is invoked with the information provided in the program source, and the resulting attribute instance is returned. If additional information was provided through properties, those properties are set to the given values before the attribute instance is returned.

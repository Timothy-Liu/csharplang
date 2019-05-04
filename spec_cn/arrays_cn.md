# 数组

数组是一种包含了若干变量的数据结构，这些变量可以通过计算出来的索引来访问。数组所包含的变量也被称为数组的元素（elements），它们的类型是相同的，而这一类型被称为数组的元素类型（element type）。

每个数组都拥有一个等级（rank），数组的等级决定了有多少个索引与每个数组元素相关联。数组的等级也被称为数组的维度（dimensions）。等级为一的数组被称为**单维数组**（single-dimensional array，即一维数组）。如果一个数组的等级大于一，那么就称为**多维数组**（multi-dimensional array）。具有特定等级的多维数组也经常被称为“二维数组”、“三维数组”等等。

数组的每个维度都有一个与之关联的长度（length），此长度是一个大于等于零的整数。数组维度的长度并非数组类型的组成部分，这个值会在运行期、数组实例被创建的时候被设定（established）。数组维度的长度决定了此维度上索引的合法取值范围：假设一个维度的长度是`N`，那么索引的取值范围就是从`0`到`N - 1`(包含`0`和`N - 1`)。数组的元素总个数是数组所有维度长度的乘积。如果数组的一个或多个维度长度为零，那么这个数组就是一个空数组。

数组的元素类型可以是任意的——包括数组类型（译注：即一个数组的元素可以是子数组）。

## 数组类型

数组类型被书写为*非数组类型*后面跟上一个或者多个*级别指定符*：

```antlr
array_type
    : non_array_type rank_specifier+
    ;

non_array_type
    : type
    ;

rank_specifier
    : '[' dim_separator* ']'
    ;

dim_separator
    : ','
    ;
```

*non_array_type*指的是除*array_type*之外的任意*type*，即这个类型自身不能是一个数组类型。

数组类型的级别由*array_type*中最左边的*rank_specifier*所指定：这个*rank_specifier*指定了这个数组的级别是其所包含的`,`的数量加一。（译注：`int[,]`和`int[,][]`都是二维数组。）

数组元素的类型是数组类型删除了最左边的*rank_specifier*后所得到的类型：

* `T[R]`所表示的是一个级别为`R`、元素类型为`T`（非数组类型）的数组类型（译注：`R`可以是诸如`10`或`10,20`的值）。
* `T[R][R1]...[Rn]`所表示的是级别为`R`、元素类型为`T[R1]...[Rn]`的数组类型。

实际上，在最终的非数组元素类型之前的*rank_specifier*是从左向右读取的（???）。类型`int[][,,][,]`是一个一维数组，这个数组的元素是一个三维数组，而这个三维数组的元素又是一个二维数组，这个二维数组的元素类型是`int`。

在运行时，数组类型的值可以是`null`或者是此数组类型实例的一个引用（译注：因为数组的本质是类）。

### System.Array类型

`System.Array`类型是所有数组类型的抽象基类型（译注：它是个抽象类）。从任何数组类型到`System.Array`都可以进行隐式的引用（类型）转换（[隐式引用转换](conversions.md#implicit-reference-conversions)），反之，从`System.Array`类型向任何（具体的）数组类型转换则需要使用显式引用（类型）转换（[显式引用转换](conversions.md#explicit-reference-conversions)）。请注意，`System.Array`本身并不是一个*array_type*；`System.Array`是一个*class_type*，而且所有*array_type*都是从它派生出来的。

在运行期，一个`System.Array`类型的值可以是`null`或者是一个对任意数组类型实例的引用。

### 数组与泛型的`IList`接口

一维数组`T[]`实现了`System.Collections.Generic.IList<T>`（简写为`IList<T>`）泛型接口和它的基接口。相应的，从`T[]`向`IList<T>`和`IList<T>`的基接口可以进行隐式转换。进而，如果有类型`S`可以向类型`T`进行隐式转换的话，那么`S[]`便实现了`IList<T>`，因此`S[]`也可以向`List<T>`和`IList<T>`的基接口进行隐式转换（[隐式引用转换](conversions.md#implicit-reference-conversions)）。如果类型`S`可以向类型`T`进行显式类型转换，那么`S[]`也可以向`IList<T>`和`IList<T>`的基接口进行显式类型转换（[显式引用转换](conversions.md#explicit-reference-conversions)）。例如：
```csharp
using System.Collections.Generic;

class Test
{
    static void Main() {
        string[] sa = new string[5];
        object[] oa1 = new object[5];
        object[] oa2 = sa;

        IList<string> lst1 = sa;                    // 允许
        IList<string> lst2 = oa1;                   // 错误，需要显式转换
        IList<object> lst3 = sa;                    // 允许
        IList<object> lst4 = oa1;                   // 允许

        IList<string> lst5 = (IList<string>)oa1;    // 异常
        IList<string> lst6 = (IList<string>)oa2;    // 允许
    }
}
```

赋值操作`lst2 = oa1`会产生一个编译期错误，因为从`object[]`到`IList<string>`需要做显式转换（译注：即使做了这个转换，也只是在编译期骗过编译器，运行期还是会出异常），这里的隐式转换是不行的。类型转换（译注：case需要一个更好的译文）`(IList<string>)oa1`则会在运行期产生一个异常（译注：“错误”和“异常”，一个是编译期的，一个是运行期的），因为`oa1`引用的是一个`object[]`而非`string[]`（译注：因为`object`不能向`string`进行隐/显式转换）。然而，`(IList<string>)oa2`这个转换就不会产生异常，因为`oa2`引用的就是一个`string[]`。（译注：这个例子不是很好，应该使用`int[]`和`long[]`来重写这个例子。）

无论何时，只要从`S[]`到`List<T>`可以进行隐式或者显式转换，那么从`IList<T>`和`IList<T>`的基接口向`S[]`就都可以进行显式转换（[显式引用转换](conversions.md#explicit-reference-conversions)）。（译注：最好有个例子）

当数组类型`S[]`实现了`IList<T>`后，这些被实现的接口里的某些成员有可能会抛出异常。不过，关于接口实现时的精确行为已经超出了本规范的范畴。

## 数组的创建

藉由*array_creation_expression*（[数组创建表达式](expressions.md#array-creation-expressions)）或者带有*array_initializer*（[数组初始化器](arrays.md#array-initializers)）的字段及局部变量，可以创建数组的实例。

当创建一个数组实例的时候，这个数组的级别和每个维度的长度就都被确定了，而且会在数组实例的整个生命周期中都保持不变。换言之，我不既不可能改变已有数组的级别也不可能改变数组维度的长度。

数组实例的类型永远是数组类型。`System.Array`则是一个不能被实例化的抽象类型，（，它是所有数组类型的基类型）。（译注：这里是在强调`System.Array`类并非数组类型）

由*array_creation_expression*所创建的数组里的元素总是会被初始化为它们的（译注：其实是数组元素类型的）默认值（[默认值](variables.md#default-values)）。

## 访问数组元素

数组元素的访问需要用到形式如`A[I1, I2, ..., In]`的*element_access*表达式（[数组访问](expressions.md#array-access)），其中，`A`是一个数组类型的表达式（译注：即要么是个数组，要么是一个表达式求值之后能得到一个数组），而每个`Ix`都是一个`int`、`uint`、`long`或`ulong`类型（或者可隐式转换成这些类型的）表达式。数组元素访问的结果是一个变量。（译注：当方括号中的`Ix`多于一个时，是在访问多维数组。）

数组的元素可使用`foreach`语句来进行枚举（[`foreach`语句](statements.md#the-foreach-statement)）。

## 数组的成员

所有数组类型都继承了由`System.Array`类型所声明的成员。

## 数组的协变

对于两个引用类型`A`与`B`来说，如果从`A`到`B`能进行隐式引用转换（[隐式引用转换](conversions.md#implicit-reference-conversions)）或显式引用转换（[显式引用转换](conversions.md#explicit-reference-conversions)），那么，从数组类型`A[R]`到数组类型`B[R]`也能够发生同样的转换，这里的`R`是任意给定的*rank_specifier*（但两个数组的`R`必须一致）。这样的关系称为**数组的协变**。数组的协变一定程度上意味着一个`A[R]`数组类型的值有可能实际上是一个对数组类型`B[R]`的实例的引用。（译注：争议！引用类型的值到底是不是对象？）

因为数组协变的存在，对引用类型数组元素赋值的时候会有一个运行期的检查，用以保证向数组元素赋予的值的确是被允许的类型（[简单赋值](expressions.md#simple-assignment)）。例如：
```csharp
class Test
{
    static void Fill(object[] array, int index, int count, object value) {
        for (int i = index; i < index + count; i++) array[i] = value;
    }

    static void Main() {
        string[] strings = new string[100];
        Fill(strings, 0, 100, "Undefined");
        Fill(strings, 0, 10, null);
        Fill(strings, 90, 10, 0);
    }
}
```

`Fill`方法中对`array[i]`的赋值隐式地包含了一个运行期的（类型）检查，这个检查保证了被`value`所引用着的对象要么是`null`要么是一个与`array`数组实际元素类型兼容的对象。在`Main`方法中，前两个对`Fill`的调用会是成功的，但在第三个调中，一执行对`array[i]`的赋值马上就会抛出`System.ArrayTypeMismatchException`异常。原因是被装箱的`int`不能被存储进一个`string`数组中。

*value_type*数组不会发生数组协变。例如，能允许`int[]`像被`object[]`一样对待的转换是不存在的。（译注：`int`与`long`兼容，那么`int[]`实例是否可以被`long[]`变量引用？）

## 数组初始化器

在字段声明（[字段](classes.md#fields)）、局部变量声明（[局部变量声明](statements.md#local-variable-declarations)）、和数组创建表达式（[数组创建表达式](expressions.md#array-creation-expressions)）中，可以指定数组初始化器。

```antlr
array_initializer
    : '{' variable_initializer_list? '}'
    | '{' variable_initializer_list ',' '}'
    ;

variable_initializer_list
    : variable_initializer (',' variable_initializer)*
    ;

variable_initializer
    : expression
    | array_initializer
    ;
```

数组初始化器是在一对花括号（`{`和`}`）中包含一组由逗号（`,`）分隔的变量初始化器。每个变量初始化器都是一个表达式，或者是一个嵌套的数组初始化器（当被初始化的是一个多维数组的时候）。

使用了数组初始化器的上下文能够决定被初始化的数组的类型。在数组创建表达式中，数组的类型要么紧挨着放在数组初始化器前面，要么由数组初始化器中的表达式推断出来。在字段和变量声明中，数组的类型就是被用来声明字段和变量的类型。当数组初始化器被用在字段或变量声明里时，例如：
```csharp
int[] a = {0, 2, 4, 6, 8};
```
其实就是下面这个等价的数组创建表达式的简写：
```csharp
int[] a = new int[] {0, 2, 4, 6, 8};
```

对于一维数组，它的数组初始化器必需由一系表达式构成，这些表达式的类型必需与数组的元素类型兼容。这些表达式从索引为零的元素开始，以上升的顺序来初始化数组的元素。初始化器中表达式的个数决定了被创建的数组实例的长度。例如，前面例子中的数组初始化器创建的`int[]`实例长度为5，并且将数组中的元素初始化为了如下的值：
```csharp
a[0] = 0; a[1] = 2; a[2] = 4; a[3] = 6; a[4] = 8;
```

对于多维数组，它的初始化器必须具有与数组维度一样多的嵌套级别。最外层的嵌套级别对应的是（数组类型）最左侧的维度，而最内层的嵌套级别对应的是（数组类型）最右侧的维度。数组在每个维度上的长度由相应嵌套级别中的元素个数决定。处于同一个级别上的嵌套（子级）数组初始化器必须具有相同的长度。例子：
```csharp
int[,] b = {{0, 1}, {2, 3}, {4, 5}, {6, 7}, {8, 9}};
```
创建了一个二维数组，它的最左边的维度的长度为5，最右边的维度的长度为2（，相当于）：
```csharp
int[,] b = new int[5, 2];
```
然后再用下面的值来初始化这个数组实例：
```csharp
b[0, 0] = 0; b[0, 1] = 1;
b[1, 0] = 2; b[1, 1] = 3;
b[2, 0] = 4; b[2, 1] = 5;
b[3, 0] = 6; b[3, 1] = 7;
b[4, 0] = 8; b[4, 1] = 9;
```

除最右侧的维度外，如果哪个维度的长度是零，那么其后续的维度长度也都会被视为零。例如：
```csharp
int[,] c = {};
```
创建了一个最左、最右两个维度长度都为零的二维数组：
```csharp
int[,] c = new int[0, 0];
```

当一个数组创建表达式既包含显式的维度长度又带有数组初始化器的时候，长度就必须是常量表达式，而且，每个嵌套级别中的元素个数都必须与相应维度的长度相匹配。这里有些例子：
```csharp
int i = 3;
int[] x = new int[3] {0, 1, 2};        // 允许
int[] y = new int[i] {0, 1, 2};        // 错误，因为i不是一个常量
int[] z = new int[3] {0, 1, 2, 3};     // 错误，长度与初始化器不匹配
```

这里，数组`y`的初始化器会引发一个编译期错误，因为作为维度长度的表达式（`i`）不是一个常量。数组`z`的初始化器也会引起一个编译期错误，因为数组的长度与初始化器中元素的个数不相符。（译注：初始化器中的元素个数可以少于数组的显式维度长度。）

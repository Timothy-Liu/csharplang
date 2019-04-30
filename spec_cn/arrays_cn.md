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
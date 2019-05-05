# 类

类是一种可以包含数据成员、函数成员和嵌套类型的数据结构。类的数据成员包括常量和字段。类的函数成员包括方法、属性、事件、索引器、操作符、实例构造器和析构器、静态构造器。类类型支持继承。藉由继承这种机制，派生类能够对基类进行扩展和特殊化。

## 类的声明

*class_declaration*是一种*type_declaration*（[类型声明](namespaces.md#type-declarations))），它用于声明一个新的类。

```antlr
class_declaration
    : attributes? class_modifier* 'partial'? 'class' identifier type_parameter_list?
      class_base? type_parameter_constraints_clause* class_body ';'?
    ;
```

*class_declaration*包含了一组可选的*attributes*（[特征](attributes.md)），后面跟上一组可选的*class_modifier*（[类修饰符](classes.md#class-modifiers)），再跟上可选的`partial`修饰符，再跟上（必须出现的）关键字`class`和一个用来给类命名的*identifier*，再跟上一个可选的*type_parameter_list*（[类型参数](classes.md#type-parameters)），再跟上一个可选的*class_base*定义（[Class base specification](classes.md#class-base-specification)），再跟上一组可选的*type_parameter_constraints_clause*（[类型参数约束](classes.md#type-parameter-constraints)），再跟上（必须有的）*class_body*（[类体](classes.md#class-body)），最后是一个可选的分号（`;`）。

仅当类的声明中带有*type_parameter_list*的时候，才能为其配有*type_parameter_constraints_clause*。

带有*type_parameter_list*的类声明称为**泛型类声明**。进而，任何一个嵌套于泛型类声明或者泛型结构体声明中的类声明，也会是泛型的——因为外层类型的类型参数是被用于完整构建一个类型的。（译注：这里需要代码解释。???）

### 类修饰符

*class_declaration*中可以包含一组可选的类修饰符：

```antlr
class_modifier
    : 'new'
    | 'public'
    | 'protected'
    | 'internal'
    | 'private'
    | 'abstract'
    | 'sealed'
    | 'static'
    | class_modifier_unsafe
    ;
```

如果同一个修饰符在类声明中出现多次，就会产生一个编译期错误。

`new`修饰符（译注：这里的`new`不是操作符）被允许用来修饰嵌套类。`new`修饰符的作用是告诉（派生类）使用被`new`修饰符所修饰的成员去隐藏一个继承来的同名成员（参见[`new`修饰符](classes.md#the-new-modifier)）。如果`new`修饰符出现在非嵌套类的声明中，就会产生一个编译期错误。

修饰符`public`、`protected`、`internal`和`private`用于控制类的（可）访问性。基于类声明出现位置的上下文，某几个访问性控制操作符会不被允许（[访问性声明](basic-concepts.md#declared-accessibility)）。

修饰符`abstract`、`sealed`和`static`会在随后章节中详细讨论。

#### 抽象类

修饰符`abstract`的作用是指明被它修饰的类是不完整的。抽象类作为不完整的类，其存在的意义（旨在），是只能被当作基类来使用。抽象类与非抽象类的区别在于：

* 抽象类不能被直接实例化（译注：还能间接实例化的？），如果使用`new`操作符去实例化一个抽象类，就会产生一个编译期错误。然而，使用编译期类型为抽象类型的变量或者值是可以的，这样的变量和值必须要么是`null`要么包含着对非抽象类实例的引用，这里的非抽象类实例必须是派生自前述的抽象类型。
* 抽象类允许（但不一定）包含抽象成员。（译注：抽象成员必须声明在抽象类中。）
* 抽象类不能是封闭的。（译注：即不能同时使用`abstract`和`sealed`来修饰同一个类。）

当一个非抽象类派生自一个抽象类的时候，这个非抽象类必包含对所有继承来的抽象成员的实际实现，借此重写这些抽象成员。下面的例子中：
```csharp
abstract class A
{
    public abstract void F();
}

abstract class B: A
{
    public void G() {}
}

class C: B
{
    public override void F() {
        // actual implementation of F
    }
}
```
抽象类`A`引入了一个抽象方法`F`。类`B`又引入了一个方法`G`，但由于它并没有提供对`F`的实现，所以类`B`也必须声明为抽象的。因为类`C`中并没有抽象成员，所以类`C`被允许（但并不一定要）成为非抽象的。
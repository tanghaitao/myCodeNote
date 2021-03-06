# c++概述

# 目录

1. [c++概述](#cpp1data001)
    1. [c++简介](#cpp1data001a)
    2. [c++起源](#cpp1data001b)
    3. [可移植性和标准](#cpp1data001c)
    4. [为什么C++会成功](#cpp1data001d)
    




### cpp1data001
# 1. c++概述


### cpp1data001a
## 1.1 c++简介

“`c++`”中的`++`来自于c语言中的递增运算符`++`，该运算符将变量加1。`c++`起初也叫”c with clsss”.通过名称表明，`c++`是对C的扩展，因此`c++`是c语言的超集，这意味着任何有效的c程序都是有效的`c++`程序。`c++`程序可以使用已有的c程序库。


c++语言在c语言的基础上添加了**面向对象编程**和**泛型编程**的支持。c++继承了c语言高效，简洁，快速和可移植的传统。

**c++融合了3种不同的编程方式**:

1. c语言代表的过程性语言.

2. c++在c语言基础上添加的类代表的面向对象语言.

3. c++模板支持的泛型编程。

**c语言和c++语言的关系:**

`c++`语言是在C语言的基础上，添加了面向对象、模板等现代程序设计语言的特性而发展起来的。两者无论是从语法规则上，还是从运算符的数量和使用上，都非常相似，所以我们常常将这两门语言统称为“C/`C++`”。

C语言和`C++`并不是对立的竞争关系：

1)`C++`是C语言的加强，是一种更好的C语言。

2)`C++`是以C语言为基础的，并且完全兼容C语言的特性。

c语言和`C++`语言的学习是可以相互促进。学好C语言，可以为我们将来进一步地学习`C++`语言打好基础，而`C++`语言的学习，也会促进我们对于C语言的理解，从而更好地运用C语言。


### cpp1data001b
## 1.2 c++起源

与c语言一样，`c++`也是在贝尔实验室诞生的，Bjarne Stroustrup(本贾尼·斯特劳斯特卢普)在20世纪80年代在这里开发了这种语言。


Stroustrup关心的是让`C++`更有用，而不是实施特定的编程原理或风格。在确定语言特性方面，真正的编程比纯粹的原理更重要。Stroustrup之所以在c的基础上创建`C++`,是因为c语言简洁、适合系统编程、使用广泛且与UNIX操作系统联系紧密。

### cpp1data001c
## 1.3 可移植性和标准

假设为运行windows  2000的老式奔腾pc编写了一个很好用的`C++`程序，而管理员决定使用不同操作系统(比如说Mac OS 或 Linux)和处理器的计算机替换它。该程序是否可在新平台运行呢？当然，但是必须使用为新平台设计的`C++`编译器重新编译。但是是否需要修改写好的代码？如果不需要修改代码的情况下，重新编译程序后，程序依然运行良好，该程序是可移植的。

程序是否可移植性有两个问题需要解决。第一是硬件，针对特定硬件编程的程序是不可移植的。第二，语言的实现，windows  xp `C++` 和  Redhat  Linux  或  Mac  OS  X对`C++`的实现不一定相同。虽然我们希望`C++`版本与其他版本兼容，但是如果没有一个公开的标准，很难做到。因此，美国国家标准局(American National Standards Institute,ANSI)在1990年设立一个委员会专门负责制定`C++`标准(ANSI制定了c语言的标准)。国际标准化组织(International Organization for Standardization，ISO)很快通过自己的委员会加入到这个行列，创建了联合组织ANSI/ISO,制定`C++`标准。

经过多年的努力，制定出了一个国际标准ISO/IEC  14882:1998  ，并于1998年获得了ISO、IEC(International Electrotechnical Committee,国际电工技术委员会)和ANSI的批准。这个标准就是我们经常所说的`C++`98。它不仅描述了已有的`C++`特性，还对语言进行了扩展，添加了异常、运行阶段类型识别(RTTI)、模板和标准模板库(STL).

2003年，发布了`C++`标准第二版(IOS/IEC 14882:2003),这一版本对第一版修订了一些错误，但并没有改变语言特性，因此`C++`98表示`C++`98/`C++`2003.

`C++`不断发展。IOS标准委员会于2011年8月批准了新标准ISO/IEC  14882:2011,该标准被称为`C++`11,与`C++`98一样`C++`11也新增了许多特性。

ISO `C++`标准还吸收了ANSI  c语言标准，`C++`尽量做到是c的超集。意味着在理想情况下，任何有效的c程序都应该是有效的`C++`程序。

ANSI不仅定义了c语言，还  定义了一个ANSI  c必须实现的标准c库。`C++`也在使用这个库，另外ANSI/ISO `C++`标准还提供了一个`C++`标准类库。

### cpp1data001d
## 1.4 为什么C++会成功

`C++`最初的目的是将c语言转变为OOP语言，但是`C++`后来并没有这么做，而是立足于程序的实际。因为在c语言方面大量投入的程序员使其完全丢掉c语言那种编程的思考方式，转而去接受一种新的语言，新的思维，那么将会导致这些程序员中大部分人在短时间内可能毫无成果，使其生产率降低。但是如果让这些c程序员在已有知识的基础上，再去学习`C++`语言，理解运用OOP，那么也只是在其已有思维的基础上进行扩展而已，这样可以保持其更好的生产率。

简而言之，强迫程序员放弃c语言和c语言的思考方式，而去转到OOP上是需要代价的，但是从c语言转到`C++`所花费的代价就会小很多。所以也可以理解为`C++`的出现并不是去替代c,而是对c的扩展，所以在`C++`中既可以使用`C++`新特性，并且可以使用c的过程式思维来编写程序。





> 对于传统的结构化语言，我们向来没有太多的疑惑，函数调用那么自然而明显，只是从程序的某一个地点调到另一个地点去执行。但是对于面向对象(OO)语言，我们疑惑就会很多。其原因就是c++编译器为我们程序员做了太多隐藏的工作：构造函数，析构函数、虚函数、继承、多态....有时候它为我们合成出一些额外的函数,有时候它又偷偷在我们写的函数里，放进更多的操作。有时候也会给我们的对象里放进一些奇妙的东西，使得我们sizeof的时候结果可我们预期不一样。





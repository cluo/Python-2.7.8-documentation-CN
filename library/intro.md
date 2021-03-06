Python标准库包括了各种不同类型的组件，关于标准库的组成，在此做一番说明：

首先，它包括一些作为Python核心部分的数据类型，比如number和list类型。Python<u>语言核心</u>(language core)只是定义了这些数据类型的书写方式，并简单地对其意义做了一定的限制。换句话说，语言核心只是定义了语法层面的属性，比如书写方式以及运算符的优先级。

其次，标准库还包括了一些内置函数和内置异常，即一些不需要通过*import*语句就可以被所有pyhon代码使用的对象。语言核心定义了一小部分，更大的一部分对于定义Python核心语法并不必须，因此只是放在标准库中定义。

另外，标准库的很大一部分，是由一系列的模块集组成的，有很多对它们进行分类的方式，例如：从编程语言来看，一些模块用C语言编写并内置于python解释器中，另一些则用python编写并通过import导入。从接口类型上看，一些模块提供针对python自身的接口，例如打印<u>堆栈踪迹</u>(stack trace)，另一些则提供针对于特定操作系统的接口，如访问特定硬件或特定应用领域(如World Wide Web)。从兼容性角度看，一些模块在所有版本的python中都是可用的，一些只有在底层系统支持它们时才可用，还有一些则只有在特定的编译及安装环境才是可用的。

这一手册是按照“由里及表”（From the inside out）的原则组织的：它首先叙述了内置的数据类型，然后叙述内置函数与内置异常，最后再分章节叙述各个模块。其中章节的排列顺序大致按照这些模块的重要程度来决定的。

这意味着，如果你从头开始读这本手册并且跳过你觉得无聊的章节，你就可以对可用的模块及pyhon标准库支持的应用领域有一个很好的了解。当然，你不一定要将它当成一本小说从头读到尾，你可以浏览目录或者在索引中找到特定的函数、模块或术语。并且，如果你喜欢随意的阅读一些主题，你也可以选择随便翻到一页然后阅读几小节。不过，不论你按照什么顺序来阅读这本手册，最好还是从
[内置函数](./functions.md)
这一章开始，因为这本手册的其他部分都假设你熟悉内置函数这一部分。

现在让我们开始吧！





|        			|				|	内置函数		|				|		 		|
|:-------------:	|:-------------:| 	:-----:		| 	:-----:		|	:------:	|
|abs绝对值/模			|divmod  		|input  		|open  			|staticmethod  	|
|all全部				|enumerate  	|int  			|ord  			|str  			|
|any存在一个			|eval  			|isinstance  	|pow  			|sum  			|
|basestring类		|execfile  		|issubclass  	|print  		|super  		|
|bin二进制转换		|file  			|iter  			|property  		|tuple  		|
|bool类				|filter  		|len  			|range  		|type  			|
|bytearray类  		|float  		|list  			|raw_input  	|unichr  		|
|callable是否可调用	|format  		|locals  		|reduce  		|unicode  		|
|chr数字->字符		|frozenset  	|long  			|reload  		|vars  			|
|classmethod声明类方法|getattr  		|map  			|repr  			|xrange  		|
|cmp 比较			|globals  		|max  			|reversed  		|zip  			|
|compile  			|hasattr  		|memoryview  	|round  		|\_\_import\_\_ |
|complex  			|hash  			|min  			|set  			|apply  		|
|delattr  			|help  			|next  			|setattr  		|buffer  		|
|dict  				|hex  			|object  		|slice  		|coerce  		|
|dir  				|id  			|oct  			|sorted  		|intern  		|

- - - 
**说明：**  

- 函数名前的斜体class是为了强调这是一个类型，需要特别注意能否被调用以及实例化  
- 参数列表中由[]包括的为可选参数

- - -

**abs(*x*)**  

返回一个数的绝对值。  
参数可以是任意整数或者浮点数。当参数是复数时，则返回它的模。

- - -

**all(*iterable*)**  

当*iterable*的所有元素都为*True*时（或者*iterable*为空）返回*True*，在逻辑上相当于：任意一个为真。  
	等价于：

	def all(iterable):  
		for element in iterable:  
			if not element:  
				return False  
		return True

最早出现在2.5版本中。

- - -

**any(*iterable*)**  

当*iterable*中只要存在一个为*True*时返回*True*，当*iterable*为空时返回假，在逻辑上相当于：存在一个为真。  
等价于：

	def any(iterable):
	    for element in iterable:
	        if element:
	            return True
	    return False
最早出现在2.5版本中

- - -

*class* **basestring()**  

这个抽象类是str和unicode的父类。它不能被调用或者实例化，但是它可以用来测试一个对象是否是str或unicode对象的实例。  

isinstance(*obj, basestring*)等价于isinstance(*obj, (str, unicode)*)。  

最早出现在2.3版本中。  

- - -

**bin(*x*)**  

将一个整数转换为二进制字符串，结果是一个有效的python表达式。  
当x不是Python的int对象时,必须定义一个返回整型的方法： \_\_index\_\_()。  

最早出现在2.6版本中。

- - -

*class* **bool(*[x]*)**  

返回一个Bool值（True或False）。  
将x按照标准的真值测试流程转换为Bool值：当x为假或为空时返回False；否则返回True。  
bool实际上是int的子类。bool不能被继承，它只有两个实例：False与True。False。  

最早出现在2.2.1版本中。

在2.3版本有所变化：如果没有指定参数，则返回False。	

- - -

*class* **bytearray(*[source[,encoding[,errors]]]*)**  

返回一个新的字节型矩阵。  
bytearray类是一种可变序列(Mutable sequence)，存储字节型整数x：0&lt;=x&lt;256。  
它包含可变序列以及str类型所具有的绝大多数方法。  
	
可以利用可选的source参数来对数组作如下几种方式的初始化：

- 如果是unicode类型的字符串，必须再指定encoding参数(errors参数依然是可选的)：bytearray()会利用unicode.encode()将unicode转换为字节。
- 如果是integer：则初始化生成的数组大小为source，内容为无效字节(nullbyte)。
- 如果是具有缓冲区(buffer)接口的对象：则该对象的缓冲区内容将以只读方式初始化bytearray。
- 如果是可迭代对象：它必须由[0,256)之间的的整数组成，初始化成为数组的内容。
- 若不指定参数，则生成一个大小为0的数组。

最早出现在2.6版本中。

- - -

**callable(*object*)**  

当object是可调用的时候，返回True，反之返回False。  
当返回True时，调用该object仍然**有可能**失败；但返回False时调用该对象**一定会**失败。

- - -

**chr(*i*)**  

返回十进制整数*i*在ASCII码上对应的字符，例如*chr(97)*返回字符串'a'。  
chr()与ord()在功能上恰好相反。  
参数必须在[0...255]范围内，否则将抛出ValueError。  
参见*unichr()*

- - -
**classmethod(*function*)**  

返回*function*的类方法。  

与实例方法将一样，一个类方法隐式地将类自身作为第一个参数。  
采用如下方式声明一个类方法：

	class C(object):
	    @classmethod
	    def f(cls, arg1, arg2, ...):
		        ...
*@classmethod*是一个函数修饰符 —— 具体内容参考
[函数定义](https://docs.python.org/2/reference/compound_stmts.html#function)
类方法既可以被类自身调用，也可以被该类的实例对象所调用。在调用类方法时，实例只是作为对象而忽略其他内容。如果一个类方法是由派生对象所调用的，那么该派生对象隐式地将自身作为第一个参数。

Python中的类方法与C++与Java的静态方法(static method)不同，具体细节在本章*staticmethod()*函数部分介绍。

关于类方法的更多细节，可以在[标准类型继承](https://docs.python.org/2/reference/compound_stmts.html#function)中找到。

最早出现在2.2版本中。

在2.4版本有所变化：增加了函数修饰符的语法

- - -

**cmp(*x,y*)**  

比较对象x与y的值，根据比较结果返回整数。当x<y时返回值为负，当x==y时返回零，当x>y时返回值为正。

- - -

**compile(*source,filename,mode[,flags[,dont_inherit]]*)**  

将源代码编译成为Code 或 AST文件。**暂未译**

- - -

*class* **complex(*[real[,imag]]*)**

返回一个（实部+虚部j）形式的复数。参数可以为字符串或者数值（包括复数）。具体表现如下：

- 若不指定参数：返回*0j*
- 若第一个参数为数值
	- 若不指定第二个参数：*complex()*返回第一个参数的复数版本,*imag*默认为*0*
	- 若指定第二个参数：*complex(a+bj,c+dj)*返回 (a-d)+(b+c)j
- 若第一个参数为字符串：第二个参数必须为空，否则抛出TypeError；字符串中的+或-周围不应该具有空格，否则抛出ValueError，complex("1+2j")返回(1+2j)而complex("1 + 2j")抛出异常。

复数类型在[数值类型](./library/stdtypes.md)中介绍

- - -

**delattr(*object,name*)**

删除*object*对象的*name*属性，例如：delattr(x,'foobar') 等价于 del x.foobar 。与*setattr()*对应。

- - -

*class* **dict(*\*\*kwarg*)**  
*class* **dict(*mapping,\*\*kwarg*)**  
*class* **dict(*iterable,\*\*kwarg*)**  

创造一个新的字典。见[内置类型](./library/stdtypes.md)中的*dict*。

- - -

**dir(*[object]*)**

不带参数时返回当前作用域中的变量名（包括内置变量）；带参数时返回*object*对象的有效属性。

如果被调用对象有*\_\_dir\_\_*()方法，则*dir()*会调用对象的*\_\_dir\_\_*()方法并返回属性列表。这使得对象可以通过自定义*\_\_getattr\_\_*()和*_\_\getattribute\_\_*()函数来自定义*dir()*的效果。

如果被调用对象不具有*\_\_dir\_\_*()方法，则*dir()*会试图从对象的*\_\_dict\_\_*属性（如果定义了的话）和类型对象（type object）中收集信息。返回值未必完整，并且当被调用对象自定义了*\_\_getattr\_\_*()时结果会有所改变。

*dir()*的默认机制对于不同的对象类型表现也不尽相同，原因是该函数是为了尽可能收集到重要的信息而不是完整的信息：

- 如果对象是模块(module)，则返回模块的属性名。
- 如果对象是类型或类时(type or class)，则返回该对象及其全部基类的属性名。
- 否则， 返回对象的属性名，对象的类(class)及其全部基类的属性名。

返回的结果列表按照字母顺序显示。例如：

	>>> import struct
	>>> dir()   # show the names in the module namespace
	['__builtins__', '__doc__', '__name__', 'struct']
	>>> dir(struct)   # show the names in the struct module
	['Struct', '__builtins__', '__doc__', '__file__', '__name__',
	 '__package__', '_clearcache', 'calcsize', 'error', 'pack', 'pack_into',
	 'unpack', 'unpack_from']
	>>> class Shape(object):
	        def __dir__(self):
	            return ['area', 'perimeter', 'location']
	>>> s = Shape()
	>>> dir(s)
	['area', 'perimeter', 'location']

**注：**由于*dir()*函数主要是为了交互式编程的方便，因此它主要是为了提供用户感兴趣的结果而不是严格完整的结果，并且各个版本之间它的具体行为方式也有所不同。例如，当被调用对象是一个类时，元类(metaclass)的属性不会出现在结果中

- - -

**divmod(*a,b*)**

带余除法：第一个参数为被除数，第二个参数为除数，采用长除法计算，并按照（商，余数）的形式返回结果。
	
	divmod(5,2)			#(2,1)
	divmod(5.0,2.0)		#(2.0,1.0)
	divmod(5,-2)		#(-3,-1)

对于参数的数值类型不相同的，采用二进制算术运算。对整型（包括长整型）则返回*(a//b,a%b)*；对浮点数则返回*(q,a%b)*，其中q一般为*math.floor(a/b)*但也许会比它小，对浮点数来说*q\*b+a%b*的值总是非常**接近于***a*的。

当余数*a%b*不为零时，总与除数*b*的值相同。



在版本2.3中有所变化：弃用参数为复数时的情况（可以调用，但结果没有意义）

- - -

**enumerate(*sequence[,start=0]*)**

返回一个枚举对象。*sequence*必须是可迭代对象(序列、 迭代器或其他的支持迭代的对象 )。*enumerate*返回的迭代器的*next()*方法返回一个元组*(count,value)*，其中*count*从*start*（默认为0)开始，value为*sequence*中的依次被迭代的值。

	>>> seasons = ['Spring', 'Summer', 'Fall', 'Winter']
	>>> list(enumerate(seasons))
	[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
	>>> list(enumerate(seasons, start=1))
	[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]

该函数等价于：

	def enumerate(sequence, start=0):
    n = start
    for elem in sequence:
        yield n, elem
        n += 1

最早在2.3版本出现

在2.6版本有所改变：添加了*start*参数

- - -
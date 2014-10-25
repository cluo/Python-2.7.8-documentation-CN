

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
* 函数名前的斜体class是为了强调这是一个类型，需要特别注意能否被调用以及实例化  
* 参数列表中由[]包括的为可选参数

- - -

**abs(*x*)**  
>	返回一个数的绝对值。  
	参数可以是任意整数或者浮点数。当参数是复数时，则返回它的模。

- - -

**all(*iterable*)**  
>	当*iterable*的所有元素都为*True*时（或者*iterable*为空）返回*True*，在逻辑上相当于：任意一个为真。  
	等价于：

		def all(iterable):  
			for element in iterable:  
				if not element:  
					return False  
			return True

>	最早出现在2.5版本中。

- - -

**any(*iterable*)**
>	当*iterable*中只要存在一个为*True*时返回*True*，当*iterable*为空时返回假，在逻辑上相当于：存在一个为真。  
	等价于：

		def any(iterable):
		    for element in iterable:
		        if element:
		            return True
		    return False
>	最早出现在2.5版本中

- - -

*class* **basestring()**
>	这个抽象类是str和unicode的父类。它不能被调用或者实例化，但是它可以用来测试一个对象是否是str或unicode对象的实例。  
	isinstance(obj, basestring)等价于isinstance(obj, (str, unicode))。  

>	最早出现在2.3版本中。  

- - -

**bin(*x*)**
>	将一个整数转换为二进制字符串，结果是一个有效的python表达式。  
	当x不是Python的int对象时,必须定义一个返回整形的方法： \_\_index\_\_()。  

>	最早出现在2.6版本中。

- - -

*class* **bool(*[x]*)**
>	返回一个Bool值（True或False）。  
	将x按照标准的真值测试流程转换为Bool值：当x为假或为空时返回False；否则返回True。  
	bool实际上是int的子类。bool不能被继承，它只有两个实例：False与True。False。  

>	最早出现在2.2.1版本中。

>	在2.3版本有所变化：如果没有指定参数，则返回False。	

- - -

*class* **bytearray(*[source[,encoding[,errors]]]*)**
>	返回一个新的字节型矩阵。  
	bytearray类是一种可变序列(Mutable sequence)，存储字节型整数x：0&lt;=x&lt;256。  
	它包含可变序列以及str类型所具有的绝大多数方法。  
	
>	可以利用可选的source参数来对数组作如下几种方式的初始化：

>	- 如果是unicode类型的字符串，必须再指定encoding参数(errors参数依然是可选的)：bytearray()会利用unicode.encode()将unicode转换为字节。
>	- 如果是integer：则初始化生成的数组大小为source，内容为无效字节(nullbyte)。
>	- 如果是具有缓冲区(buffer)接口的对象：则该对象的缓冲区内容将以只读方式初始化bytearray。
>	- 如果是可迭代对象：它必须由[0,256)之间的的整数组成，初始化成为数组的内容。
>	- 若不指定参数，则生成一个大小为0的数组。

>	最早出现在2.6版本中。

- - -

**callable(*object*)**
>	当object是可调用的时候，返回True，反之返回False。  
	当返回True时，调用该object仍然*有可能*失败；但返回False时调用该对象*一定会*失败。

- - -

**chr(*i*)**
>	返回十进制整数*i*在ASCII码上对应的字符，例如*chr(97)*返回字符串'a'。  
	chr()与ord()在功能上恰好相反。  
	参数必须在[0...255]范围内，否则将抛出ValueError。  
	参见*unichr()*

- - -
**classmethod(*function*)**
>	返回*function*的类方法。  

>	与实例方法将一样，一个类方法隐式地将类自身作为第一个参数。  
	采用如下方式声明一个类方法：

		class C(object):
		    @classmethod
		    def f(cls, arg1, arg2, ...):
		        ...
>	*@classmethod*是一个函数修饰符 —— 具体内容参考
[函数定义](https://docs.python.org/2/reference/compound_stmts.html#function)
>	类方法既可以被类自身调用，也可以被该类的实例对象所调用。在调用类方法时，实例只是作为对象而忽略其他内容。如果一个类方法是由派生对象所调用的，那么该派生对象隐式地将自身作为第一个参数。

>	Python中的类方法与C++与Java的静态方法(static method)不同，具体细节在本章*staticmethod()*函数部分介绍。

>	关于类方法的更多细节，可以在[标准类型继承](https://docs.python.org/2/reference/compound_stmts.html#function)中找到。

>	最早出现在2.2版本中。

>	在2.4版本有所变化：增加了函数修饰符的语法

- - -
**cmp(*x,y*)**
>	比较对象x与y的值，根据比较结果返回整数。当x<y时返回值为负，当x==y时返回零，当x>y时返回值为正。

- - -
**compile(*source,filename,mode[,flags[,dont_inherit]]*)**
>
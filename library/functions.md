<table border="1px solid black" align='center'>
	<thead><tr><th></th><th></th><th>内置函数</th><th></th><th></th></tr></thead>
	<tbody valign="top">
		<tr><td>abs()绝对值</td><td>divmod()</td><td>input()</td><td>open()</td><td>staticmethod()</td></tr>
		<tr><td>all()</td><td>enumerate()</td><td>int()</td><td>ord()</td><td>str()</td></tr>
		<tr><td>any()</td><td>eval()</td><td>isinstance()</td><td>pow()</td><td>sum()</td></tr>
		<tr><td>basestring()</td><td>execfile()</td><td>issubclass()</td><td>print()</td><td>super()</td></tr>
		<tr><td>bin()</td><td>file()</td><td>iter()</td><td>property()</td><td>tuple()</td></tr>
		<tr><td>bool()</td><td>filter()</td><td>len()</td><td>range()</td><td>type()</td></tr>
		<tr><td>bytearray()</td><td>float()</td><td>list()</td><td>raw_input()</td><td>unichr()</td></tr>
		<tr><td>callable()</td><td>format()</td><td>locals()</td><td>reduce()</td><td>unicode()</td></tr>
		<tr><td>chr()</td><td>frozenset()</td><td>long()</td><td>reload()</td><td>vars()</td></tr>
		<tr><td>classmethod()</td><td>getattr()</td><td>map()</td><td>repr()</td><td>xrange()</td></tr>
		<tr><td>cmp()</td><td>globals()</td><td>max()</td><td>reversed()</td><td>zip()</td></tr>
		<tr><td>compile()</td><td>hasattr()</td><td>memoryview()</td><td>round()</td><td>__import__()</td></tr>
		<tr><td>complex()</td><td>hash()</td><td>min()</td><td>set()</td><td>apply()</td></tr>
		<tr><td>delattr()</td><td>help()</td><td>next()</td><td>setattr()</td><td>buffer()</td></tr>
		<tr><td>dict()</td><td>hex()</td><td>object()</td><td>slice()</td><td>coerce()</td></tr>
		<tr><td>dir()</td><td>id()</td><td>oct()</td><td>sorted()</td><td>intern()</td></tr>
	</tbody>
</table>

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

- - - 
说明：  
- 函数名前的斜体class是为了强调这是一个类型，需要特别注意能否被调用以及实例化  
- 参数列表中由[]包括的为可选参数
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
	当x不是Python的int对象时,必须定义一个返回整形的方法： __index__()。  

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

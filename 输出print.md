#print（）
	>>> help(print)
	Help on built-in function print in module builtins:

	print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
    
    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
##输出
	1. 字符串和数值类型
	   可以直接输出
	2. 变量
	   无论什么类型，数值，布尔，列表，字典...都可以直接输出
	3.格式化输出  跳转到[格式化输出](#index)

##内置方法sep和end
###sep
	分割：默认是“ ”分割
###end
	结尾：默认是“\n” ,换行作 结尾追加值










##《Python基础编程》中对格式化输出的总结：

	(1). %字符：标记转换说明符的开始
	(2). 转换标志：-表示左对齐；+表示在转换值之前要加上正负号；“”（空白字符）表示正数之前保留空格；0表示转换值若位数不够则用0填充
	(3). 最小字段宽度：转换后的字符串至少应该具有该值指定的宽度。如果是*，则宽度会从值元组中读出。
	(4). 点(.)后跟精度值：如果转换的是实数，精度值就表示出现在小数点后的位数。如果转换的是字符串，那么该数字就表示最大字段宽度。如果是*，那么精度将从元组中读出
	(5).字符串格式化转换类型

#
	转换类型          含义
	
	d,i                 带符号的十进制整数
	o                   不带符号的八进制
	u                   不带符号的十进制
	x                    不带符号的十六进制（小写）
	X                   不带符号的十六进制（大写）
	e                   科学计数法表示的浮点数（小写）
	E                   科学计数法表示的浮点数（大写）
	f,F                 十进制浮点数
	g                   如果指数大于-4或者小于精度值则和e相同，其他情况和f相同
	G                  如果指数大于-4或者小于精度值则和E相同，其他情况和F相同
	C                  单字符（接受整数或者单字符字符串）
	r                    字符串（使用repr转换任意python对象)
	s                   字符串（使用str转换任意python对象）
#
 
	>>> pi = 3.141592653  
	>>> print('%10.3f' % pi) #字段宽10，精度3  
	     3.142  
	>>> print("pi = %.*f" % (3,pi)) #用*从后面的元组中读取字段宽度或精度  
	pi = 3.142  
	>>> print('%010.3f' % pi) #用0填充空白  
	000003.142  
	>>> print('%-10.3f' % pi) #左对齐  
	3.142       
	>>> print('%+f' % pi) #显示正负号  
	+3.141593 
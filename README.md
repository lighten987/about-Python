# about-Python  
做一些关于Python的笔记  
  
***Python3***  
py使用 缩进 来表示代码块，不需要使用大括号{}  缩进的空格数是可变的，但是同一个代码块的语句必须包括相同的缩进空格数  
if True:  
   print("True")  #值得注意的是，语句结尾没有分号，输出打印语句也不同，注释用“#”号  
else:  
   print("False")  
    
py中数字四种类型，int bool float complex    
   
**字符串**    
py中单引号和双引号使用完全相同 三引号（'''或者"""）可以指定一个多行字符串     
r"dsfas\r\d\n"并不会发生转义，**被那个r抓住不准跑**      
字符串两种索引方式 从左往右以0开始，从右往左以-1开始  
py中没有字符类型，一个字符就是长度为1的字符串  
字符串截取的语法格式：**变量[头下标：尾下标]**  
str='Runoob'  
print(str)                 # 输出字符串  
print(str[0:-1])           # 输出第一个到倒数第二个的所有字符  
print(str[0])              # 输出字符串第一个字符  
print(str[2:5])            # 输出从第三个开始到第五个的字符  
print(str[2:])             # 输出从第三个开始的后的所有字符  
print(str * 2)             # 输出字符串两次  
print(str + '你好')        # 连接字符串  

函数之间或类的方法之间用空行分隔，表示一段新的代码的开始。类和函数入口之间也用一行空行分隔，以突出函数入口的开始。  

缩进相同的一组语句构成一个代码块，称为代码组  if,while,def,class这种复合语句关键词后用冒号：表示首行结束，之后的就是一个代码块  
  
print输出默认换行，如果不想换行，在变量末尾加**，end=""**  
  
**py的导入**  
import导入整个模块 from  import导入模块中的某些函数甚至所有函数  
将整个模块(somemodule)导入，格式为： import somemodule  
从某个模块中导入某个函数,格式为： from somemodule import somefunction  
从某个模块中导入多个函数,格式为： from somemodule import firstfunc, secondfunc, thirdfunc  
将某个模块中的全部函数导入，格式为： from somemodule import *  

py中的变量不需要申明，变量赋值后使用就行  c = 11 # 整型变量   d = 1.2 # 浮点型变量 e = "abc" # 字符串  
**骚操作**  a,b,c = 1,2.5,"abc"  

**标准数据类型**  对于数据 用type(x)可查看数据类型  
不可变数据（3个）：number（数字） string(字符串) tuple(元组)  数字类型在2中有long 3中只有int 截取字符串[ : ] 左闭右开  
可变数据（3个）：list(列表) dictionary（字典） set（集合）  

**数值运算**  只说特殊的  
>>> 2 / 4  # 除法，得到一个浮点数 0.5 **准确值**  
>>> 2 // 4 # 除法，得到一个整数 0 **去尾整数值**  
>>> 2 ** 5 # 乘方  

list 列表 里面放各种类型都可以 写在[]内 加号+直接列表连接 星号*重复操作 比如输出几次*   **列表内元素可以改变**    
list内置很多方法 例如append()添加元素 pop()删除元素 后期补充  

tuple 元组 写在（）中，可以不同类型 **但内容不可改变**    
  
集合 直接s = {a,b,c} 或者set(value) 创建空集合必须用set(),不能直接用{},这是创建空字典的   
  
列表是有序的对象集合，而字典是无序的对象集合，是一种映射关系，用键存取  无序的键值对集合  键(key)：值(value)对  同一个字典中 键(key)必须是唯一的      
**几个常用函数**  
eval() #除去最外侧的引号 在读入的数字为字符串时相当于直接转换成数字类型  
round(x,d) #对x四舍五入，d是小数截取位数   
divmod(x,y) #商余 divmod(10,3) 结果为(10,3)   
  
  
输出语句中多用"槽"来进行占位，然后format()依次填充，当然槽里可标记非顺序使得内容有跳跃  
print("nicai{}le".format("对" if true else "错")) **输出是一个点.format**    
  
python的class中的object是指这个类继承的最顶级的对象。python3.x 中已经可以省略object，可直接  
>class Sample():  
        pass  
    
**def里面的self代表的是类的实例。而self.class则指向类**  
**self在定义时不可以省略**  
**在继承时，传入的是哪个实例，就是那个传入的实例，而不是指定义了self的类的实例。**  
>class Parent:  
    def pprt(self):  
        print(self)  
class Child(Parent):  
    def cprt(self):  
        print(self)  
c = Child()  
c.cprt()  
c.pprt()  
p = Parent()  
p.pprt()  
  
执行结果：  
  
><__main__.Child object at 0x0057C3F0>  
<__main__.Child object at 0x0057C3F0>  
<__main__.Parent object at 0x0057CBD0>  
  
运行c.cprt()时应该没有理解问题，指的是Child类的实例。  
但是在运行c.pprt()时，等同于Child.pprt(c)，所以self指的依然是Child类的实例，由于self中没有定义pprt()方法，所以沿着继承树往上找，发现在父类Parent中定义了pprt()方法，所以就会成功调用。  
**在描述符类中，self指的是描述符类的实例**  
>class Desc:  
    def __get__(self, ins, cls):  
        print('self in Desc: %s ' % self )  
        print(self, ins, cls)  
class Test:  
    x = Desc()  
    def prt(self):  
        print('self in Test: %s' % self)  
t = Test()  
t.prt()  
t.x  
  
执行结果：  
>self in Test: <__main__.Test object at 0x0045C3B0>  
self in Desc: <__main__.Desc object at 0x0045C310>   
<__main__.Desc object at 0x0045C310> <__main__.Test object at 0x0045C3B0> <class '__main__.Test'>  
  
最后一句t.x，也就是Test类的实例t的属性x，由于实例t中并没有定义属性x，所以找到了类属性x，而该属性是描述符属性，为Desc类的实例而已，所以此处并没有顶用Test的任何方法。

而如果把t.x改为Test.x  

执行结果：  
>self in Test: <__main__.Test object at 0x0044C3B0>  
self in Desc: <__main__.Desc object at 0x0044C310>   
<__main__.Desc object at 0x0044C310> None <class '__main__.Test'>123  
  
由于在很多时候描述符类中仍然需要知道调用该描述符的实例是谁，所以在描述符类中存在第二个参数ins，用来表示调用它的类实例，所以t.x时可以看到第三行中的运行结果中第二项为  
<<main.Test object at 0x0000000002A570B8>  
而采用Test.x进行调用时，由于没有实例，所以返回None。  
  
  
**雪峰相关笔记**  
关于输出方式的不同，py2中用print value1 py3用print （value1）  多一个括号  
一行逗号里面只能赋值一句，多个等式要么共用一个=，要么用；分隔    
注意True,False,首字母大写,true不是关键字  
关键字None用来占位，不属于任何类型，变量解除绑定  
a//b地板除，结果向下取整（永远舍尾），a**b 幂运算  
  
与或非的表示 and,or,not  a and b 返回b  
  
类似于c中的三目运算符 ？ ： py中语法格式为：表达式1 if 真值表达式 else 表达式2  “优”  if score>90 else "差"  
  
列表l.sort()元素升序，再l.reverse() 降序  l.pop()函数不加参数，删除最后一个，加参数，删除指定位置  
  
**浅拷贝与深拷贝**   
l.copy()浅拷贝， 共享地址，一改全改，保证只读时用浅拷贝，不然用深拷贝   
深拷贝要import copy 再调用函数copy.deepcopy()  
  
**函数**  
函数定义：  
def 函数名(参数列表):  
    ["注释"](可选)  
    语言块(代码块)...  
    return [返回值](可选)  不写return返回None  
函数调用作为模块内部语句时，必须先定义后调用，没有申明的说法   
函数定义的结束并不是遇到return语句，而是遇到一个跟def同缩进(一般顶格)的语句  
函数的两种不定长参数：星号元组形参 双星号字典形参   
星号元组形参：语法格式为 
def 函数名(*元组形参名)：  
    语句块   
def func(a,*argc,b,c):
    body  
调用时  func(10,b=4,c=6)  #星号元组后面的参数赋值必须写明指示，然后中间的即为元组成员    
  
双星号字典形参：语法格式为：  
def 函数名(**元组形参名)：  
    语句块   
  
变量跳出作用域，使用global关键字  
   
函数可以当成变量直接赋值，f1 = f2  
map,reduce,filter,sorted函数  

lambda表达式(匿名函数)  
lambda的主体是一个表达式，而不是一个代码块，即只包含一个语句lambda [arg1 [,arg2,...argn]]:expression     sum = lambda arg1, arg2: arg1 + arg2 

**牢记py3的print要加括号()**  
迭代器是一个可以记住遍历的位置的对象。  
迭代器对象从集合的第一个元素开始访问，直到所有的元素被访问完结束。迭代器只能往前不会后退。  
迭代器有两个基本的方法：iter() 和 next()。  
字符串，列表或元组对象都可用于创建迭代器：  
it = iter(list) #创建迭代器对象  
在类的内部，使用def关键字来定义一个方法，与一般函数定义不同，类方法必须包含参数self，且为第一个参数，self代表的是类的实例  
继承的语句：  
**单继承**class zi_lei(fu_lei):  **注意冒号**  
方法支持调用并重载，支持覆写方法  
**多继承**class zi_lei(fu1_lei,fu2_lei):  
类的私有属性，是__student(两个下划线开头的)，类的私有方法，也是__study()(两个下划线开头的)  

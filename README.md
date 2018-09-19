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
r"dsfas\r\d\n"并不会发生转义，被那个r抓住不准跑  
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


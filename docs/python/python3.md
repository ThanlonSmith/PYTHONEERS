>@[toc]
##### 1. 编译器与解释器
###### 1.1 编译与解释
① 编译
将源程序翻译成可执行的目标代码，执行可执行程序文件，翻译与执行是分开的。编译程序跨平台性不好，不同操作系统，调用底层的机器指令不同，需为不同平台生成不同的机器码文件。编译程序每次修改源代码，都要重新编译，生成机器码文件。编译程序执行速度快，因为程序代码已经翻译成了是计算机可以理解的机器语言。

② 解释
解释：解释程序不产生目标代码，它逐条地取出源程序中的语句，边解释边执行，解释器把源代码文件边解释成机器语言边交给CPU执行。解释程序可跨平台使用，因为解释器已经做好了对不同平台的交互处理，用户写的源代码不需要再考虑差异性，源代码所有平台都可以直接执行。解释程序可以随时修改，立刻生效，改完源代码后，直接运行看效果。解释程序运行效率低，所有的代码均需经过解释器边解释变执行，速度比编译型慢很多。
###### 1.2 编译器与解释器
编程语言所写的代码想要运行，必须依赖自己语言的编译器或解释器。

① 编译器
把源程序的每一条语句都编译成机器语言码，并保存成二进制文件，运行时计算机可以直接识别并运行，例如：C、C++、C#、Java、Go等语言。

② 解释器
只在执行程序时，从上到下把写过的代码一行一行的解释成机器码并给计算机来执行（边解释边执行），例如：Python、PHP、JavaScript等语言。
###### 1.3 python解释器
windows/mac os系统运行python程序时使用`解释器 文件路径`，在linux系统中也可以这样来运行python程序。但是，在linux系统中存在一种特殊的执行方法。在给文件赋予可执行的权限后，使用`./py文件`。使用`./py文件`这种方式，执行的时候自动去找py文件的第一行代码。第一行代码`#!/usr/bin/env python`指定了解释器的路径，等价于`/usr/bin/env/python py文件`。
##### 2. 初识编码
###### 2.1 ASCII
American Standard Code for Information Interchange，美国标准信息交换代码的英文缩写，基于拉丁字母的一套电脑编码系统，主要用于显示现代英语和其他西欧语言，其最多只能用 8 位来表示(一个字节)，即：2<sup>8</sup> = 256，所以，ASCII码最多只能表示 256 个符号。
###### 2.2 Unicode
称为统一码或万国码或单一码，一种在计算机上使用的字符编码。Unicode 是为了解决传统的字符编码方案的局限而产生的，它为每种语言中的每个字符设定了统一并且唯一的二进制编码，规定虽有的字符和符号最少由 16 位来表示(2个字节)，即：2 <sup>16</sup> = 65536，注：此处说的的是最少2个字节，可能更多。
###### 2.3 UTF-8
对Unicode编码的压缩和优化，它不再最少使用2个字节，而是将所有的字符和符号进行分类：ASCII码中的内容用1个字节保存、欧洲的字符用2个字节保存，东亚的字符用3个字节保存。
##### 3. IDLE编辑器
ctrl+N：`启动IDLE`

ctrl+Q：`退出IDLE`

alt+3：`注释`

alt+4：`删除注释`

alt+Q：`格式化布局Python代码`

F5：`执行Python程序`
##### 4. 输入输出
###### 4.1 输入
`input('提示内容')`

input是固定格式，是输入的意思，括号里边的内容是给用户看的提示内容，用户输入的内容被input接收后可以赋值给字符串类型的变量。

需要注意的是：**在Python2 中使用raw_input获取的都是字符串，在Python3 中使用input获取的都是字符串**
###### 4.2 输出
使用`print`函数输出内容，Python2与Python3输出的语法是不一样的，Python2：`print 'thanlon'`，Python3：`print('thanlon')`，Python3中把print看作是一个函数的存在。
##### 5. 变量与常量
###### 5.1 变量
变量名只能包含：字母、数字和下划线，变量不能以数字开头，不能是python中的关键字。

变量命名的一个建议：见名知意；用下划线连接（不建议使用驼峰式命名）
>**Python中的关键字：and、as、asset、break、class、continue、def、del、elif、else、except、exec、finally、for、from、global、if、import、in、is、lambda、not、or、pass、print、raise、return、try、while、with、yield**
###### 5.2 常量
常量就是将变量名大写，尽量保持不更改的一种量，常量一经定义就不允许去改变。
##### 6. 注释
###### 6.1 单行注释
`# 单行注释`
###### 6.2 多行注释
```py
'''
多行注释1
'''
"""
多行注释2
"""
```
##### 7. 流程控制
###### 7.1 if
```py
name = input("输入姓名:")
if name == 'thanlon':
    print(name)
```
###### 7.2 if else
```py
name = input("输入姓名:")
if name == 'thanlon':
    print(name)
else:
    print('你自己的名字都不知道了吧！')
```
###### 7.2 if elif
```py
a = eval(input('请输入一个数字：'))
if a > 66:
    print('猜测的结果大了！')
elif a < 66:
    print('猜测的结果小了!')
elif a == 66:
    print('猜测结果正确')
```
##### 8. 循环结构
###### 8.1 while
如果条件为真，循环体执行；如果条件为假，循环体不执行：
```py
while 条件:
    # 循环体
```
简单的while循环：
```py
count = 0
while count < 10:
    count += 1
    print(count)
```
###### 8.2 for
for循环不可以做死循环，while循环可以做死循环。有穷尽优先使用for，无穷尽使用while。for循环示例：
```python
# coding:utf-8
name = 'thanlon'
for item in name:
    print(item)
print(item)
'''
t
h
a
n
l
o
n
n
'''
```
for循环练习，请打印1~10：
```py
for item in range(1, 11):  # range其实是列表
    print(item)
```
###### 8.3 break
break关键字可用来终止当前循环。当程序执行到break的时候就结束当前这个while循环，break以下的代码都不执行：
```py
count = 0
while count < 10:
    count += 1
    if count > 8:
        break
    print(count)  # 当count>8，print函数不会执行
```
```py
name = 'thanlon'
for item in name:
    if item == 'l':
        break
    print(item)
'''
t
h
a
n
'''
```
###### 8.4 continue
continue关键字用于退出当次循环，继续下一次循环：
```py
count = 0
while count < 10:
    count += 1
    if count == 9:
        continue
    print(count)
```
```py
name = 'thanlon'
for item in name:
    if item == 'l':
        continue
    print(item)
'''
t
h
a
n
o
n
'''
```
###### 8.5 while else
当满足while条件(while结构中的条件部分为False)后，执行else中的语句：
```py
count = 0
while count < 5:
    print(count)
    count += 1
else:
    print('stop')
'''
0
1
2
3
4
stop
'''
```
如果通过其它方式(如break语句)跳出while循环，则执行else中的语句：
```py
count = 0
while True:
    if count > 5:
        break
    print(count)
    count += 1
else:
    print('stop')
'''
0
1
2
3
4
5
'''
```
##### 7. 字符串格式化
###### 7.1 字符串格式化的意义
字符串格式化的意义是使用比较方便，下面的代码比较没有适合字符串格式化和使用字符串格式化的对比：
```py
# 没有使用字符串格式化
name = 'Thanlon'
print(name + ' is play basketball……')  # 写起来比较麻烦
# 使用字符串格式化
name = 'Thanlon'
print('%s is play basketball……' % (name,)) # 写起来计较方便
```
###### 7.2 %s与%d
%s与%d是占位符，s表示字符串，d表示数字。**一般%s可以来接收%d的数据**。
```python
template = '我是%s，年龄%d，职业时%s。' % ('thanlon', 22, '软件开发工程师',)
print(template)
```
###### 7.3 %%
如果在输出语句中使用了百分号，为了防止被认为是占位符，我们需要再使用一个百分号，用来转义单个%。下面是一个实例程序：
```py
name = 'Thanlon'
# 遇到%就认为是占位符
# template = '%s手机点电量是100%' % (name)
'''
ValueError: incomplete format
'''
template = '%s手机电量是100%%' % (name)
print(template)
'''
Thanlon手机电量是100%
'''
```
##### 8. 运算符
###### 8.1 算数运算符
|运算符|描述|
|-|-|
|+|加，两个对象相加(Python是面向对象的语言，万物皆是对象)|
|-|减|
|*|乘，两个数相乘或返回一个被重复若干次的字符串|
|/|除|
|%|取模，除法的余数|
|**|幂|
|//|取整数，商的取整部分|
###### 8.2 比较运算符
|运算符|描述|
|-|-|
|==|等于，比较对象是否相等|
|!=|不等于，比较对象是否不相等|
|>|大于|
|<|小于|
|>=|大于等于|
|<=|小于等于|
###### 8.3 赋值运算符
|运算符|描述|
|-|-|
|=|简单的赋值运算符|
|+=|加法赋值运算符|
|-=|减法赋值运算符|
|*=|乘法赋值运算符|
|/=|除法赋值运算符|
|%=|取模赋值运算符|
|**=|mi赋值运算符|
|//=|取整除赋值运算符|
###### 8.4 逻辑运算符
|运算符|描述|
|-|-|
|and|对于x and y，当x和y均为True时，x and y为True；x或y任何一个为False，x and y为False|
|or|对于x or y，x和y任何一个为True，结果为True；x和y都为False，结果才是False|
|not|取反，对于not x，x为True，not x为False；x为False，not x为True|
**在没有括号的情况下，not的优先级高于and，and优先级高于or。同一优先级哪个在前先计算哪个。**

**对于and，第一个值如果转换成布尔值是True，则value = 第二个值；如果第一个值换成布尔值是False，则value = 第一个值。如果有多个and条件，则从左到右依次进行上述流程。**

**对于or，第一个值如果是转换成布尔值是真，则value=第一个值；第一个值转换成布尔值如果是假，则value=第二个值。如果有多个or条件，则从左到右依次进行上述流程。**

###### 8.5 成员运算
使用到的运算符：in和not in，用来判断元素是否在原字符串、字典、列表、集合种
```python
print('t' in 'thanlon')
'''
True
'''
print('t' not in 'thanlon')
'''
False
'''
```
###### 8.6 运算符优先级
|运算符|描述（表格从上到下优先级依次降低）|
|-|-|
|**|指数|
|~ , + , -|按位取反，一元加号和减号|
|* , / , % , //|乘，除，取模和取整除|
|+ , -|加法，减法|
|>> , <<|右移，左移|
|<= , >= , > , <|比较运算符|
|== , !=|等于,不等于|
|= , %= , /= , //= , -= , += , *= , **=|赋值运算符|
|is , is not|身份运算符|
|in , not in|成员运算符|
|not , and , or|逻辑运算符|
##### 9. 编码补充
###### 9.1 ASCII
只表示英文，使用8位表示信息，有2的8次方种表示结果
###### 9.2 Unicode
使用32位表示信息，有2的32次方种表示结果。目前只使用了21位，Unicode一般用于计算机内存中做计算。
###### 9.3 UTF-8
压缩Unicode，使用8位，用尽量少的位数来表示信息，节省存储空间。UTF-8中一个中文占3个字节，UTF-8一般可用于网络传输和数据存储。
###### 9.4 UTF-16
Windows中将文件另存为Unicode，此处Unicode实际上是UTF-16，Unicode不能写在硬盘中。与UTF-8不同的是，UTF-16最多将Unicode压缩到16位。如果是ecs2则占用2个字节。如果是ecs4则占用4个字节(现在用的是这种)。
###### 9.5 GBK2312
亚洲地区使用的编码，一个中文占两个字节
###### 9.6 GBK
亚洲地区使用的编码，是GB2312的升级版，一个中文占两个字节
###### 9.7 如何选择编码
GBK中一个中文占用2个字节，UTF-8中一个中文占用3个字节，**GBK比UTF-8更节省空间，但是为了便于以后做项目扩展，强烈最好还是使用UTF-8的编码格式**。
##### 9. 单位转换
 8bit = 1B
1024B = 1KB
1024KB = 1MB
1024MB = 1GB
1024GB = 1TB
1024TB = 1PB
1024PB = 1EB
1024EB = 1ZB
1024ZB = 1YB
1024YB = 1NB
1024NB = 1DB
##### 10. Python主文件
###### 10.1 什么是主文件
运行的python文件就是主文件
###### 10.2 区分主文件与非主文件
每一个Python文件都有一个变量`__name__`，主文件中的`__name__`与 字符串`"__ main __ "` 相等，如果不是直接运行的主文件，`__name__`与`"__main__"`是不相等的，下面这个例子可以证明这一点：

`not_main.py：`
```py
print(__name__)
```
`main.py`:
```py
import not_main

print(__name__)
'''
not_main
__main__
'''
```
下面的这个是一个很常见的例子，可以判断当前运行的文件是不是主文件：

`not_main.py`:
```py
def func():
    print('no_main')
```
`main.py`:
```python
import not_main
if __name__ == '__main__':
    not_main.func()
    '''
    no_main
    '''
```
如果直接执行main.py，会执行func函数。
##### 11. 综合练习题
###### 11.1 猜数字游戏
设定一个理想数字如：66，让用户输入数字，如果比66大，则显示猜测的结果大了；如果比66小，则显示猜测的结果小了;只有等于66，显示猜测结果正确，然后退出循环。
```py
while True:
    a = eval(input('请输入一个数字：'))
    if a > 66:
        print('猜测的结果大了！')
    elif a < 66:
        print('猜测的结果小了!')
    elif a == 66:
        print('猜测结果正确')
        break
```
###### 11.2 猜数字限制猜测次数
```py
count = 0
while True:
    if count == 3:
        print('大笨蛋！')
        break
    a = eval(input('请输入一个数字：'))
    if a > 66:
        print('猜测的结果大了！')
        count += 1
    elif a < 66:
        print('猜测的结果小了!')
        count += 1
    elif a == 66:
        print('猜测结果正确')
        break
```
###### 11.3 使用循环输入1 2 3 4 5 6 8 9
```py
i = 0
while i < 9
    i += 1
    if i == 7:
        continue
    print(i)
```
###### 11.4 求1-100的所有数的和
```py
i = 0
sum_num = 0
while i < 100:
    i += 1
    sum_num += i
print(sum_num)
```
###### 11.5 输出1-100内的所有奇数
```py
i = 1
while i < 100:
    print(i)
    i += 2
```
```py
i = 1
while i <= 100:
    if i % 2 != 0:
        print(i)
    i += 1
```
###### 11.6 输出1-100内的所有偶数
```
# coding:utf-8
i = 1
while i <= 100:
    if i % 2 == 0:
        print(i)
    i += 1
```
###### 11.7 求1-2+3-4+5 ... 99的所有数的和
```py
'''
求1-2+3-4+5 ... 99的所有数的和
'''
sum_positive = 0  # 负数之和
sum_negative = 0  # 证数之和
i = 1
while i <= 99:
    if i % 2 == 0:
        sum_positive += i
    else:
        sum_negative += i
    i += 1
print(sum_negative - sum_positive)
'''
50
'''
```
###### 11.8 简述ascii、unicode与utf-8编码
ascii：只表示英文，使用8位表示信息
unicode：使用32位表示信息
utf-8：压缩Unicode编码，使用8位表示信息。在utf-8编码中一个中文占3个字节，一般可用于网络传输和数据存储。

###### 11.9 简述位和字节的关系
1字节 = 8位
###### 11.10 判断逻辑语句的真假
判断下列逻辑语句的真假：

① 1 > 1 or 3 < 4 or 4 > 5 and 2 > 1 and 9 > 8 or 7 < 6
=>False or True or False and True and True or False
=>False or True or False and True or False
=>False or True or False or False
=>True

② not 2 > 1 and 3 < 4 or 4 > 5 and 2 > 1 and 9 > 8 or 7 < 6
=>not True and True or False and True and True or False
=>False and True or False and True and True or False
=>False or False and True and True or False
=>False or False and True or False
=>False or False or False
=>False
###### 11.11 求出下列逻辑语句的值
① 8 or 3 and 4 or 2 and 0 or 9 and 7
=>8 or 4 or 0 or 7
=>8 or 0 or 7
=>8 oor 7
=>8

② 0 or 2 and 3 and 4 or 6 and 0 or 3
=>0 or 3 and 4 or 0 or 3
=>0 or 4 or 0 or 3
=>4 or 0 or 3
=>4 or 3
=>4

③ 6 or 2 > 1
=>6 or True
=>6

④ 3 or 2 > 1
=>3 or True
=>3

⑤ 0 or 5 < 4
=>0 or False
=>False

⑥ 5 < 4 or 3
=>False or 3
=>3

⑦ 2 > 1 or 6
=>True or 6
=>True

⑧ 3 and 2 > 1
=>3 and True
=>True

⑨ 0 and 3 > 1
=>0 and True
=>0

⑩ 2 > 1 and 3
=>True and 3
=>3

⑩ 3 > 1 and 0
=>True and 0
=>0

⑩ 3 > 1 and 2 or 2 < 3 and 3 and 4 or 3 > 2
=>True and 2 or True and 4 or True
=>2 or  4 or True
=>2 or True
=>2
```
```
>@[toc]
##### 1. 数字类型(整型)
###### 1.1 整数
可以用十进制、二进制、八进制、十六进制表示
###### 1.2 浮点数
浮点数必须带有小数部分，小数部分可以是0。浮点数有两种表示方式，一般形式：123.456；科学计数法：1.23456e2或1.23456e+2，相当于1.23456x10<sup>2</sup>。
##### 2. 布尔类型
<kbd>bool</kbd>关键字表示布尔类型，只有两个值：True/False。
##### 3. 字符串
###### 3.1 公共功能
① len：计算长度(字符串->计算字符串中字符的个数)
```python
# coding:utf-8
'''
公共的方法len:计算字符个数
'''
v = '你好！'
print(len(v))
'''
3
'''
```
② 索引：索引字符串中的元素
```python
# coding:utf-8
'''
字符串索引
'''
s = input('输入字符串：')
s_len = len(s)
index = 0
while True:
    v = s[index]
    print(v)
    if index == s_len - 1:
        break
    index += 1
```
③ 切片：获取字符串中的片段
```python
# coding:utf-8
'''
字符串切片
'''
v = 'thanlon'
print(v[1:3])  # 左开右闭
print(v[1:-1])
print(v[-2:-1])
print(v[1:])
print(v[:-1])
print(v[:])
'''
ha
hanlo
o
hanlon
thanlo
thanlon
'''
```
④ 步长
```python
# coding:utf-8
v = 'thanlon'
print(v[0:7:2])
'''
taln
'''
```
⑤ for循环
```python
# coding:utf-8
v = 'thanlon'
for i in v:
    print(i)
'''
t
h
a
n
l
o
n
'''
```
###### 3.2 字符串独有功能
① upper：将字符串转换为大写
```python
# coding:utf-8
v = 'Thanlon'
print(v.upper())
'''
THANLON
'''
```
② lower：将字符串转为小写
```python
# coding:utf-8
v = 'Thanlon'
print(v.lower())
'''
thanlon
'''
```
③ split、rsplit：切割
```python
# coding:utf-8
'''
split、rsplit方法：切割
'''
msg = '你是个笨蛋吗？你是个笨蛋吗？你是个笨蛋吗？'
print(msg.split('？'))  # 从左向右切割所有
print(msg.split('？', 1))  # 从左向右切割，从第一个？开始切割
print(msg.rsplit('？'))  # 从右向左切割所有，从最后一个？开始切割
print(msg.rsplit('？', 1))  # 从右向左切割
'''
['你是个笨蛋吗', '你是个笨蛋吗', '你是个笨蛋吗', '']
['你是个笨蛋吗', '你是个笨蛋吗？你是个笨蛋吗？']
['你是个笨蛋吗', '你是个笨蛋吗', '你是个笨蛋吗', '']
['你是个笨蛋吗？你是个笨蛋吗？你是个笨蛋吗', '']
'''
```
④ strip：去除字符串左右多余的空格
```python
'''
strip()删除左右的空白字符串
lstrip()删除左右的空白字符串
lstrip()删除的空白字符串
'''
name = input('请输入用户名：')
print('---->' + name + '<----')
print('---->' + name.strip() + '<----')
print('---->' + name.lstrip() + '<----')
print('---->' + name.rstrip() + '<----')
'''
请输入用户名： thanlon 
----> thanlon <----
---->thanlon<----
---->thanlon <----
----> thanlon<----
'''
```
⑤ replace：替换
```python
# coding:utf-8
'''
replace方法：替换
'''
msg = '你是个笨蛋吗？你是个笨蛋吗？你是个笨蛋吗？'
print(msg)
print(msg.replace('笨蛋', '**'))  # 替换所有''笨蛋'
print(msg.replace('笨蛋', '**', 1))  # 只替换第一个''笨蛋'
'''
你是个笨蛋吗？你是个笨蛋吗？你是个笨蛋吗？
你是个**吗？你是个**吗？你是个**吗？
你是个**吗？你是个笨蛋吗？你是个笨蛋吗？
'''
```
⑥ isdigit：判断是否是数字
```python
# coding:utf-8
# isdigit：方法判断是否是数字
while True:
    print('''
    1.余额查询
    2.业务办理
    ''')
    num = input('请选择服务:')
    if num.isdigit():
        print(int(num))
    else:
        print('请输入数字！')
```
⑦ startswith
```python
# coding:utf-8
'''
startswith
'''
name = 'thanlon'
v = name[0:2]
if v == 'th':
    print('是以%s开头！' % v)
else:
    print('不是以%s开头！' % v)
'''
True
'''
```
```python
# coding:utf-8
'''
startswith与endswith
'''
v = 'thanlon'
flag = v.startswith('th')
print(flag)
'''
True
'''
```
⑧ endswith
```python
# coding:utf-8
'''
endswith
'''
name = 'thanlon'
v = name[5:]
if v == 'on':
    print('是以%s结尾！' % v)
else:
    print('不是以%s结尾！' % v)
'''
True
'''
```
```python
# coding:utf-8
'''
endswith
'''
name = 'thanlon'
flag = name.endswith('on')
if flag:
    print('是以on结尾！')
else:
    print('不是以on结尾！')
'''
True
'''
```
⑨ format
```python
# coding:utf-8
'''
format
'''
print('wow,{}'.format('thanlon'))
'''
wow,thanlon
'''
```
⑩ join
```python
# coding:utf-8
'''
join
'''
name = 'thanlon'  # 解释器读取到内存后，按照unicode编码存储，占用7x4b=28b
r = '_'.join(name)
print(r)
'''
t_h_a_n_l_o_n
'''
```
⑩ encode
```python
# coding:utf-8
'''
encode
'''
name = 'thanlon'  # 解释器读取到内存后，按照unicode编码存储，占用7x4b=28b
v1 = name.encode('utf-8')
print(v1)
'''
b'thanlon'
'''
v2 = name.encode('gbk')
print(v2)
'''
b'thanlon
'''
```
###### 3.3 字符串练习
① 请将字符串反转（笔试题）
```python
# coding:utf-8
'''
方式1
'''
v = 'Thanlon'
index = len(v) - 1
while index >= 0:
    print(v[index])
    index -= 1
'''
方式2
'''
v = 'Thanlon'
print(v[::-1])  # 或print(v[-1::-1])
```
② 判断字符串中是否含有敏感字符？
```python
# coding:utf-8
info = 'thanlonkiku'
if 'kiku' in info:
    print('right!')
'''
right!
'''
```
###### 3.4 字符串与二进制相互转换
① 字符串转二进制
```python
# coding:utf-8
''''
字符串转二进制
'''
v = '一问奈何'
v2 = 'thanlon'
data = v.encode('utf-8')
data2 = v2.encode('utf-8')
print(data)
print(data2)
'''
b'\xe4\xb8\x80\xe9\x97\xae\xe5\xa5\x88\xe4\xbd\x95'
b'thanlon'
'''
```
② 二进制转字符串
```python
# coding:utf-8
''''
二进制转字符串
'''
v = b'\xe4\xb8\x80\xe9\x97\xae\xe5\xa5\x88\xe4\xbd\x95'
v2 = b'thanlon'
data = v.decode('utf-8')
data2 = v2.decode('utf-8')
print(data)
print(data2)
'''
一问奈何
thanlon
'''
```
##### 4. 列表
###### 4.1 公共功能
 ① len
```python
# coding:utf-8
users = ['Thanlon', 'Kiku']
print(len(users))
'''
2
'''
```
② 索引
```python
# coding:utf-8
users = ['Thanlon', 'Kiku']
print(users[1])
'''
Kiku
'''
```
③ 切片
```python
# coding:utf-8
users = ['Thanlon', 'Kiku']
print(users[0:1])
'''
['Thanlon']
'''
```
④ 步长
```python
# coding:utf-8
users = ['Thanlon', 'Kiku','Haha']
print(users[0::2])
'''
['Thanlon']
'''
```
⑤ for循环
```python
# coding:utf-8
users = ['Thanlon', 'Kiku', 'Haha']
for i in users:
    print(i)
'''
Thanlon
Kiku
Haha
'''
```
###### 4.2 列表独有功能
① append：在列表的最后追加一个元素
```python
# codeing:utf-8
users = []
users.append('Thanlon')
print(users)
'''
['Thanlon']
'''
```
② insert：在指定索引位置插入元素
```python
# codeing:utf-8
'''
在指定索引位置插入元素
'''
users = ['thanlon']
users.insert(0, 'Kiku')  # 在第0个元素的位置加入
print(users)
'''
['Kiku', 'thanlon']
'''
```
③ pop
```python
# codeing:utf-8
'''
删除指定索引的文件
'''
# codeing:utf-8
'''
删除指定索引的文件
'''
users = ['Kiku', 'thanlon', 'Kiku']
users.pop(0)
print(users)
users.pop()  # 删除最后一个元素
print(users)
'''
['thanlon', 'Kiku']
['thanlon']
'''
```
④ remove
```python
# codeing:utf-8
'''
删除指定元素
'''
users = ['Kiku', 'thanlon', 'Kiku']
users.remove('Kiku')  # 只能删除第一个'Kiku'
print(users)
'''
['thanlon', 'Kiku']
'''
```
⑤ clear
```python
# codeing:utf-8
'''
删除所有元素
'''
users = ['Kiku', 'thanlon', 'Kiku']
print(users)
users.clear()
print(users)
'''
['Kiku', 'thanlon', 'Kiku']
[]
'''
```
⑥ extend：在列表中追加一个列表/元组
```python
# coding:utf-8
users = ['Thanlon', 'Kiku']
ex = ['Haha', 1, 2]  # 或 ('Haha', 1, 2)
users.extend(ex)
print(users)
'''
['Thanlon', 'Kiku', 'Haha', 1, 2]
'''
```
⑦ del 列表[索引]：删除指定索引的元素(与pop方法不同的是必须得加索引)
```python
# codeing:utf-8
'''
del语法删除指定元素
'''
users = ['Kiku', 'thanlon', 'Kiku']
del users[0]
print(users)
'''
['thanlon', 'Kiku']
'''
```
⑧ 列表的修改
```python
# codeing:utf-8
users = ['thanlon', 'Kiku']
users[0] = 'T'
users[1] = 'K'
print(users)
'''
['T', 'K']
'''
```
⑨ join([字符串，字符串，，，])
```python
# coding:utf-8
'''
join([字符串,字符串,])
'''
name = [1, 2, 3, 4, 5, 6]
for item in range(0, len(name)):
    name[item] = str(name[item])
result = ''.join(name)
result2 = ','.join(name)
print(result)
print(result2)
'''
123456
1,2,3,4,5,6
'''
```
⑩ reverse：反转
```python
# coding:utf-8
'''
reverse
'''
info = ['thnalon', 'kiku']
print(info)
info.reverse()
print(info)
'''
['thnalon', 'kiku']
['kiku', 'thnalon']
'''
```
⑩ sort：排序（列表中需要是数字类型的数据）
```python
# coding:utf-8
'''
sort排序
'''
info = [4, 2, 5]
print(info)
info.sort(reverse=False)  # 从小到大排列（默认）
print(info)
info.sort(reverse=True)  # 从大到小排列（默认）
print(info)
'''
[4, 2, 5]
[2, 4, 5]
[5, 4, 2]
'''
```
###### 4.3 列表练习
① 列表的嵌套：
```python
# codeing:utf-8
users = ['thanlon', 'Kiku', [66, 'thanlon', 'Kiku', ['thanlon', 'Kiku']]]
print(users[-1])
print(users[-1][-1])
print(users[-1][-1][0])
print(users[-1][-1][0][0:-2])
'''
[66, 'thanlon', 'Kiku', ['thanlon', 'Kiku']]
['thanlon', 'Kiku']
thanlon
thanl
'''
```
② 判断列表中是否含有敏感元素？
```python
# coding:utf-8
info = [1, 2, 3, 4, 5, 'thanlon']
if 1 in info:
    print('right!')
'''
right!
'''
```
##### 5. 元组
###### 5.1 公共功能
① len
```python
# coding:utf-8
users = ('Thanlon', 'Kiku', 'Haha')
print(len(users))
'''
3
'''
```
② 索引
```python
# coding:utf-8
users = ('Thanlon', 'Kiku', 'Haha')
print(users[0])
'''
Thanlon
'''
```
③ 切片
```python
# coding:utf-8
users = ('Thanlon', 'Kiku', 'Haha')
print(users[0:3])
'''
('Thanlon', 'Kiku', 'Haha')
'''
```
④ 步长
```python
# coding:utf-8
users = ('Thanlon', 'Kiku', 'Haha')
print(users[0:3:2])
'''
('Thanlon', 'Haha')
'''
```
⑤ for循环
```python
# coding:utf-8
users = ('Thanlon', 'Kiku', 'Haha')
for i in users:
    print(i)
'''
Thanlon
Kiku
Haha
'''
```
###### 5.2 元组独有功能
###### 5.3 元组练习
① 判断元组中是否含有敏感元素？
```python
# coding:utf-8
info = (1, 2, 3, 4, 5, 'thanlon')
if 1 in info:
    print('right!')
'''
right!
'''
```
##### 6. 字典
###### 6.1 字典概述
帮助用户去表示一个事物的信息（事物有多个属性）。

<kbd>info = {'name': 'thanlon', 'age': 23, 'gender': '男'}  # 键值</kbd>
###### 6.2 字典的键值类型
任何数据类型都可以作为字典的值，但字典中键的数据类型不可以是可变类型，如列表、字典（这两种数据类型是不可hash的）。其它数据类型的值内部是不可被修改的，也即是不可变类型，这些都是可以的作为字典的键。
###### 6.3 字典基本格式
<kbd>info = {键:值,键:值,键:值,键:值,,,}</kbd>
###### 6.4 字典独有功能
① keys()：获取字典中的所有键
```python
# coding:utf-8
'''
keys()
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
for item in info:
    print(item)
print()
for item in info.keys():
    print(item)
'''
name
age
gender

name
age
gender
'''
```
② values()：获取字典中的所有值
```python
# coding:utf-8
'''
values()
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
for item in info.values():
    print(item)
print()
'''
thanlon
23
男
'''
```
③ items()：获取字典中的所有键值对
```python
# coding:utf-8
'''
values()
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
for key, value in info.items():
    print(key, value)
'''
name thanlon
age 23
gender 男
'''
```
```python
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
for item in info.items():
    print(item)
'''
('name', 'thanlon')
('age', 23)
('gender', '男')
'''
```
④ get：获取字典中的值（公司里基本上使用此方式获取字典中的值）
通过索引去取值，如果没有所取的键，就会报错。但是，如果通过get方法，不会报错。
```python
# coding:utf-8
'''
get方法，None表示什么都没有，转为bool类型是False
'''
d = {'name': 'thanlon', 'age': 23}
# v1 = d['gender']  # 不存在此键，会报错
v2 = d.get('gender')
v3 = d.get('gender', '没有这个键！')
print(v2)  # 如果没有取到值，默认返回None
print(v3)
'''
None
没有这个键！
'''
```
```python
# coding:utf-8
d = {'name': 'thanlon', 'age': 23}
result = d.get('gender')
# print(result)#None
if result == None:
    print('不存在！')
if result:
    print('存在！')
else:
    print('不存在！')
'''
不存在！
不存在！
'''
```
⑤ pop：删除键值，并返回删除的值
```python
# coding:utf-8
info = {'name': 'thanlon', 'age': 23}
result = info.pop('age')
print(info, result)
'''
{'name': 'thanlon'} 23
'''
```
⑥ update：不存在添加，存在就更新
```python
# coding:utf-8
info = {'name': 'thanlon', 'age': 23}
info.update({'name': 'kiku', 'gender': '男'})
print(info)
'''
{'name': 'kiku', 'age': 23, 'gender': '男'}
'''
```
⑦ 知识点补充
```python
# coding:utf-8
s = '1,2'
print(s.split(','))  # ['1', '2']
v1, v2 = s.split(',')
print(v1, v2)
'''
['1', '2']
1 2
'''
```
```python
# coding:utf-8
v1, v2 = ['1', '2']
print(v1, v2)
'''
1 2
'''
```
```python
# coding:utf-8
v1, v2 = ('1', '2')
print(v1, v2)
'''
1 2
'''
```
###### 6.5 公共功能
① len：获取字典长度
```python
# coding:utf-8
'''
len()
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
print(len(info))
'''
3
'''
```
② 索引
```python
# coding:utf-8
'''
len()
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
print(info['name'])
'''
thanlon
'''
```
③ 切片【无】
④ 步长【无】
⑤ for循环
```python
# coding:utf-8
'''
values()
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
for key, value in info.items():
    print(key, value)
'''
name thanlon
age 23
gender 男
'''
```
⑥ 修改：存在就修改，不存在就添加
```python
# coding:utf-8
'''
修改
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
info['name'] = 'Kiku'
info['age'] = 25
info['gender'] = '女'
print(info)
'''
{'name': 'Kiku', 'age': 25, 'gender': '女'}
'''
```
如果需要修改键，可以先删掉原来的键，再增加新的键，一般是不改键的。

⑦ 删除：删除键值
```python
# coding:utf-8
'''
删除
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
del info['name']
print(info)
'''
{'age': 23, 'gender': '男'}
'''
```
###### 6.6 字典练习
① 用户输入键，系统根据输入的键输出对应的值?
```python
# coding:utf-8
'''
用户输入键，系统根据输入的键输出对应的值
'''
info = {'name': 'thanlon', 'age': 23, 'gender': '男'}
for k, v in info.items():
    print(k, v)
while True:
    key = input('请输入key：')
    print(info[key])
'''
name thanlon
age 23
gender 男
请输入key：name
thanlon
请输入key：age
23
'''
```
② 给一个空字典，在空字典中添加数据
```python
# coding:utf-8
'''
给一个空字典，在空字典中添加数据
'''
info = {}
info['name'] = 'thanon'
info['age'] = 23
info['gender'] = '男'
print(info)
'''
{'name': 'thanon', 'age': 23, 'gender': '男'}
'''
```
③ 给一个空字典，输入key和value，将输入的key和value添加到字典中
```python
# coding:utf-8
'''
# coding:utf-8
'''
给一个空字典，输入key和value，将输入的key和value添加到字典中
'''
info = {}
k = input('Place input key：')
v = input('Place input value：')
info[k] = v
print(info)
'''
Place input key：name
Place input value：thanlon
{'name': 'thanlon'}
'''
```
④ 给一个空字典，让用户一直输入key和value，将输入的key和value添加到字典中，直到用户输入N，则表示不再输入。
```python
# coding:utf-8
'''
给一个空字典，让用户一直输入key和value，将输入的key和value添加到字典中，直到用户输入N，则表示不再输入。
'''
info = {}
while True:
    k = input('Please input key：')
    if k == 'N':
        break
    v = input('Please input Value：')
    info[k] = v
print(info)
'''
Please input key：name
Please input Value：thanlon
Please input key：age
Please input Value：23
Please input key：N
{'name': 'thanlon', 'age': '23'}
'''
```
⑤ 使用代码实现：将字符串'k1|v1,k2|v2,k3|v3,…'转换为字典{'k1':'v1','k2':'v2',……}
```python
# coding:utf-8
'''
使用代码实现：
将这样的字符串'k1|v1,k2|v2,k3|v3,…'转换为这样的字典{'k1':'v1','k2':'v2',……}
'''
msg = 'k1|v1,k2|v2,k3|v3'
info = {}
for item in msg.split(','):
    k, v = item.split('|')
    info[k] = v
print(info)
'''
{'k1': 'v1', 'k2': 'v2', 'k3': 'v3'}
'''
```
⑥ 数据类型的嵌套
元组、列表、字典可以相互嵌套：
```python
# coding:utf-8
'''
从[1, 2, {'k1': 1, 'k2': 2, 'k3': (1, 2, 3), 'k4': [1, (4, 5, 6), 2]}, 3]中取值，取出k4中的6
'''

data = [1, 2, {'k1': 1, 'k2': 2, 'k3': (1, 2, 3), 'k4': [1, (4, 5, 6), 2]}, 3]
print(data[2]['k4'][1][2])
'''
6
'''
```
⑦ 创建一个用户列表，然后让用户输入用户名和密码进行登录
```python
# coding:utf-8
'''
创建一个用户列表，然后让用户输入用户名和密码进行登录
'''
# 构建用户列表
user_list = []
while True:
    user = input('请输入用户名：')
    if user == 'N':
        break
    pwd = input('请输入密码：')
    '''
    构建列表方式1
    '''
    # user_info = {}
    # user_info['user'] = user
    # user_info['pwd'] = pwd
    # # print(user_info)  # {'user': 'thanlon', 'pwd': '123'}
    # user_list.append(user_info)
    '''
      构建列表方式2
    '''
    user_info = {'user': user, 'pwd': pwd}
    user_list.append(user_info)
username = input('请输入用户名：')
pwd = input('请输入密码：')
msg = '登录失败！'
for item in user_list:
    if username == item['user'] and pwd == item['pwd']:
        print('登录成功！')
        break
print(msg)
```
⑦ 判断键、值、键值是否在字典中
```python
# coding:utf-8

'''

'''
v = {'k1': 'v1', 'k2': 'v2', 'k3': 'v3'}
if 'x' in v:  # 默认按照键来判断：判断x是否是字典的键
    pass

# 请判断：k1是否是字典中的键
if 'k1' in v:
    pass

'''
请判断：v1是否是字典中的值
方式1：循环判断
'''
# flag = '不存在'
# for v in v.values():
#     if v == 'v1':
#         flag = '存在！'
# print(flag)
'''
请判断：v1是否是字典中的值
方式1：强制转换成列表
'''
if 'v1' in list(v.values()):  # 迁至转换成列表：['v1', 'v2', 'v3']
    pass

'''
判断'k1':'v1'是否在字典中
'''
value = v.get('k1')
if value == 'v1':
    print('存在')
else:
    print('不存在')
```
⑨ 让用户输入任意字符串，判断此字符串是否包含指定的敏感字符
```python
# coding:utf-8
'''
让用户输入任意字符串，判断此字符串是否包含指定的敏感字符
'''
char_list = ['thanlon', 'kiku', 'haha']
content = input('请输入内容：')
success = True
for v in char_list:
    if v in content:
        success = False
        break
if success:
    print(content)
else:
    print('包含敏感字符！')
'''
请输入内容：thanlonthanlon
包含敏感字符！
'''
```
##### 7. None
None数据类型，该类型表示空，无任何功能，专用于提供空值。比空字符串、空列表等更节省内存。
##### 8. 集合
###### 8.1 集合概述
集合是无序的且不重复的。
###### 8.2 空集合与其它空数据类型
```python
# coding:utf-8
None
# int
v1 = 123
v1 = int()  # 0
# bool
v2 = True  # v3 = False
v2 = bool()  # False
# str
v3 = ''
v3 = str()
# list
v4 = []
v4 = list()
# tuple
v5 = ()
v5 = tuple()
# dict
v6 = {}
v6 = dict()
# set
v7 = set()
```
###### 8.3 独有功能
① add：添加
```python
# coding:utf-8
'''
add方法
'''
v = {1, 2}
v.add('thanlon')
v.add('thanlon')  # 不重复，所以不被添加
print(v)
'''
{1, 2, 'thanlon'}
'''
```
② discard
```python
# coding:utf-8
'''
discard方法
'''
v = {1, 2, 'thanlon'}
v.discard('thanlon')
print(v)
'''
{1, 2}
'''
```
③ update
```python
# coding:utf-8
'''
update方法
'''
v = {1, 2, 'thanlon'}
v.update({'kiku'})
v.update(['haha'])
print(v)
'''
{1, 2, 'thanlon', 'haha', 'kiku'}
'''
```
④ intersection：交集
```python
# coding:utf-8
'''
intersection方法:产生交集
'''
v = {1, 2, 'thanlon'}
result = v.intersection({1, 2, 'kiku'})
result2 = v.intersection([1, 2, 'kiku'])
print(result)
print(result2)
'''
{1, 2}
{1, 2}
'''
```
⑤ union：并集
```python
# coding:utf-8
'''
union:并集
'''
v = {1, 2, 'thanlon'}
result = v.union({1, 'kiku'})
result2 = v.union([1, 'kiku'])
print(result)
print(result2)
'''
{1, 2, 'thanlon', 'kiku'}
{1, 2, 'thanlon', 'kiku'}
'''
```
⑥ difference：差集
```python
# coding:utf-8
'''
difference:产生差集
'''
v = {1, 2, 'thanlon'}
result = v.difference({1, 2})
result2 = v.difference([1, 2])
print(result)
print(result2)
'''
{'thanlon'}
{'thanlon'}
'''
```
⑦ symmetric_difference：对称差集
```python
# coding:utf-8
'''
difference:对称差集
'''
v = {1, 2, 'thanlon'}
result = v.symmetric_difference({1, 'kiku'})
result2 = v.symmetric_difference([1, 'kiku'])
print(result)
print(result2)
'''
{2, 'kiku', 'thanlon'}
{2, 'kiku', 'thanlon'}
'''
```
###### 8.4 公共功能
① len：获取集合元素的长度
```python
# coding:utf-8
v = {'thanlon', 'kiku'}
print(len(v))
'''
2
'''
```
② for循环
```python
# coding:utf-8
v = {'thanlon', 'kiku'}
for i in v:
    print(i)
'''
kiku
thanlon
'''
```
③ 索引【无】
④ 步长【无】
⑤ 切片【无】
⑥ 删除【无】
⑦ 修改【无】
###### 8.5 集合的嵌套
可变类型不可以放在集合中，列表、字典、集合均不能放在集合中，这三种数据类型是不可hash的，并且不能作为字典的key。
```python
info = {1,2,True,'thanlon',None,(1,2,3)}
```
在列表查找元素比较慢，在集合和字典中查找元素比较快。字典中会把key进行hash转换，查找元素的时候，直接根据k1，找到v1。而不是一个元素一个元素去找。集合和字典要比列表、元组查找速度快得多。
```python
# coding:utf-8
v = {
    1: 'thanlon',
    True: 'kiku'  # True还是1，值发生改变
}
print(v)
'''
{1: 'kiku'}
'''
```
##### 9. 有无序性
元组和列表是有序的，集合和字典是无序的，但是Python3.6之后字典是有序的。可以这样说，元组、列表和字典都是有序的，只有集合是无序的。
##### 10. 字节类型
对于字符串v = '奈何'，内部使用unicode编码，“奈”与“何”分别占4个字节。如果对它的字节进行编码，达到压缩的效果：v2 = v.encode('utf-8')，得到的v2是字节。将字符串通过某种编码方式进行编码，编码后的叫做字节。字节类型显示一般有个特点：前面有个“b”。写入文件、网络传输时，字符串（unicode编码）需要进行压缩，也就是编码成utf-8的类型，才能让用户进行文件操作和网络传输。
```python
# coding:utf-8
f = open('log.txt', mode='wb')
v = '奈何'
data = v.encode('utf-8')
print(type(data), data)  # <class 'bytes'> b'\xe5\xa5\x88\xe4\xbd\x95'
f.write(data)
f.close()
```
```python
# coding:utf-8
f = open('log.txt', mode='w', encoding='utf-8')  # 内部将unicode编码的字符串转换为utf-8的编码方便文件操作
data = '奈何'
f.write(data)  # data是字符串类型就可以
f.close()
```
pickle与json的dumps方法会得到不同的类型：
```python
# coding:utf-8
import json, pickle

v = ['thanlon', '奈何']
val = pickle.dumps(v)
print(type(val), val)
'''
<class 'bytes'> b'\x80\x03]q\x00(X\x07\x00\x00\x00thanlonq\x01X\x06\x00\x00\x00\xe5\xa5\x88\xe4\xbd\x95q\x02e.'
'''
val2 = json.dumps(v)
print(type(val2), val2)
'''
<class 'str'> ["thanlon", "\u5948\u4f55"]
'''
```
如果是一个字符串，就说明是unicode编码的二进制。如果是字节，可能是utf-8，可能是gbk，也可能是其它编码的二进制。
##### 11. 数据类型内存相关
注意：是内部修改了，还是重新赋值

① 示例一（内部修改）
```python
# coding:utf-8
'''
练习：v1和v2指向同一存储空间
'''
v1 = [1, 2, 3]
v2 = v1
v1.append(4)
print(v1)
print(v2)
'''
[1, 2, 3, 4]
[1, 2, 3, 4]
'''
```
② 示例二（重新赋值）
```python
# coding:utf-8
'''
练习：v1和v2指向同一存储空间
'''
v1 = [1, 2, 3]
v2 = v1
# v1.append(4)
v1 = [4, 5, 6]
print(v1)
print(v2)
'''
[4, 5, 6]
[1, 2, 3]
'''
```
③ 示例三（重新赋值）
```python
# coding:utf-8
'''
字符串内部是不可以修改的
'''
v1 = 'thanlon'
v2 = v1
v1 = 'kiku'
print(v2)
'''
thanlon
'''
```
④ 示例四
- 练习1（内部修改）
```python
# coding:utf-8
v = [1, 2, 3]
v2 = [1, 2, 3, v]
v.append('4')
print(v2)
'''
[1, 2, 3, [1, 2, 3, '4']]
'''
```
⑤ 练习2（内部修改）
```python
# coding:utf-8
v = [1, 2, 3]
v2 = [1, 2, 3, v]
v2[3].append(4)
print(v2)
'''
[1, 2, 3, [1, 2, 3, '4']]
'''
```
⑥ 练习3（重新赋值）
```python
# coding:utf-8
'''
重新赋值
'''
v = [1, 2, 3]
v2 = [1, 2, 3, v]
v = [4, 5, 6]
print(v2)
'''
[1, 2, 3, [1, 2, 3]]
'''
```
⑦ 练习五
```python
# coding:utf-8
v = [1, 2, 3]
v2 = [1, 2, 3, v]
v2[3] = 4
print(v)
'''
[1, 2, 3]
'''
```
⑧ 查看内存地址

修改内部元素：
```python
# coding:utf-8
v = [1, 2, 3]
v2 = v
print(id(v), id(v2))  # 指向同一地址
v.append(4)
print(id(v), id(v2))
'''
2375633494664 2375633494664
2375633494664 2375633494664
'''
```
重新赋值：
```python
# coding:utf-8
v = [1, 2, 3]
v2 = v
print(id(v), id(v2))  # 指向同一地址
v = [4, 5, 6]
print(id(v), id(v2))
'''
2398328087176 2398328087176
2398328087240 2398328087176
'''
```
⑨ 内存地址特殊情况
```python
'''
v1 = [1, 2, 3]
v2 = [1, 2, 3]

v3 = [1, 2, 3]
v4 = [4, 5, 6]

v5 = [1, 2, 3]
v6 = v4
'''
```
按理说上面的v1与v2，v3与v4，v5与v6的内存地址是不同的，但特殊情况下有：
- 整型：-5~256
- 字符串：简单的字符串，如'thanlon'，做缓存，不开辟内存。复杂点的如'a_*~'*大于1的数，一般都会开辟内存。

这其实是python为了提高性能，做的一些优化的方案。

⑩ == 和is的区别（面试题）

 ==：用于比较值是否相等
 is：用于比较内存地址是否相等
```python
# coding:utf-8
v1 = [1, 2, 3]
v2 = [1, 2, 3, 4]
print(v1 == v2)
print(v1 is v2)
'''
False
False
'''
```
```python
# coding:utf-8
v1 = [1, 2, 3]
v2 = [1, 2, 3]
print(v1 == v2)
print(v1 is v2)
'''
True
False
'''
```
```python
# coding:utf-8
v1 = [1, 2, 3]
v2 = v1
print(v1 == v2)
print(v1 is v2)
'''
True
True
'''
```
##### 12. 数据类型转换
###### 12.1 其它类型转换为数字类型
```py
# 字符串转数字类型
a = int('123')
print(type(a),a)
b = float('123.456')
print(type(b),b)
# 布尔类型转数字类型
c = int(True)
d = float(True)
print(type(c),c)
print(type(d),d)
```
`执行记录：`
```js
<class 'int'> 123
<class 'float'> 123.456
<class 'int'> 1
<class 'float'> 1.0
```
###### 12.2 其它类型转字符串
```py
# 数字类型转换为字符串类型
str1 = str(123)
str2 = str(123.456)
print(str1)
print(str2)
# 布尔类型转换为字符串类型
str3 = str(True)
str4 = str(False)
print(str3)
print(str4)
# 列表转字符串
str5 = str(["Thanlon","Kiku"])
print(type(str5),str5)
str6 = ''.join(['Thanlon','kiku']) # 将列表中元素通过join连接必须是字符串才可以
print(type(str6),str6)
# 元组转字符串
str7 = str((1,2,3,4,5,6))
print(type(str7),str7)
```
`执行记录：`
```js
123
123.456
True
False
<class 'str'> ['Thanlon', 'Kiku']
<class 'str'> Thanlonkiku
<class 'str'> (1, 2, 3, 4, 5, 6)
```
###### 12.3 其它类型转换为列表
```py
# 字符串转换为列表
str = 'thanlon'
print(list(str)) # ['t', 'h', 'a', 'n', 'l', 'o', 'n']
# 元组转换为列表
tuple1 = (1,2,3,4,5,6)
print(list(tuple1)) # [1, 2, 3, 4, 5, 6]
```
`执行记录：`
```js
['t', 'h', 'a', 'n', 'l', 'o', 'n']
[1, 2, 3, 4, 5, 6]
```
###### 12.4 其它类型转换为元组
```py
# 字符串转元组
str = 'thanlon' # ('t', 'h', 'a', 'n', 'l', 'o', 'n')
print(tuple(str))
# 列表转元组
lst = [123,'thanlon']
print(tuple(lst)) # (123, 'thanlon')
```
`执行记录：`
```js
('t', 'h', 'a', 'n', 'l', 'o', 'n')
(123, 'thanlon')
```
###### 12.5 其它类型转换为布尔
```py
# 只有数字0、空字符串，空列表，空元组转换为布尔是False，其它类型转布尔为True
print(bool(0)) # print(bool(0)),(0)就是数字0
print(bool(''))
print(bool([]))
print(bool(()))
```
`执行记录：`
```js
False
False
False
False
```
>**常见的类型转换：`字符串转数字`，`数字转字符串`，`列表转元组`，`元组转列表`，`其它转布尔`**
>@[toc]
##### 1. 三元运算
###### 1.1 语法结构
```python
v = 前面 if 条件 else 后面
等价于：
if 条件:
    v = 前面
else:
    v = 后面
```
###### 1.2 三元运算示例
① 让用户输入一个值，如果值是整数，则转换成整数，否则赋值为None
```python
# coding:utf-8
'''
让用户输入一个值，如果值是整数，则转换成整数，否则赋值为None
'''
data = input('请输入一个值：')
if data.isdigit():
    value = int(data)
else:
    value = None
print(value)
'''
请输入一个值：666
666
'''
```
##### 2. 面向过程与函数式编程
###### 2.1 面向过程
```python
# coding:utf-8
role_name = input('请输入你的角色：')
if role_name == '管理员':
    pass
if role_name == '业务员':
    pass
if role_name == '……':
    pass
if role_name == '……':
    pass
```
pass部分是实现发送邮件的一系列逻辑代码，不管是管理员、业务员还是其他角色的人均需要使用到这样重复代码的功能。这种面向过程的编程方式，导致代码的可读性差、可重用性降低。

###### 2.2 函数式编程
使用面向函数编程，会在一定程度上使代码可读性好、可重用性增加。
```python
def send():
	pass
role_name = input('请输入你的角色：')
if role_name == '管理员':
    send()
if role_name == '业务员':
    send()
if role_name == '……':
    send()
if role_name == '……':
    send()
```
代码重复重复执行、代码量特别多超过一屏，可以选择使用函数进行代码的分割。
##### 3. 函数
###### 3.1 函数的结构
```python
# coding:utf-8
# 函数的定义
def 函数名():
    pass
```
###### 3.2 函数的执行(重要)
函数执行时，会创建一块内存保存自己函数执行的信息（可由此引出闭包）。函数每被执行一次就会开辟新的内存，每一次执行的函数之间互不干扰。

###### 3.3 函数面试相关
函数如果不被调用，则内部代码永远不会被执行
```python
# 函数的执行
函数名()
```
函数如果不被调用示例：
```python
func_list = []
for i in range(10):
    func_list.append(lambda: x)  # 函数不被调用，内部永远不执行

print(func_list)
'''
[<function <lambda> at 0x0000026298C1C1E0>, <function <lambda> at 0x0000026298DCC7B8>, <function <lambda> at 0x0000026298DCC8C8>, <function <lambda> at 0x0000026298DCC840>, <function <lambda> at 0x0000026298DCC950>, <function <lambda> at 0x0000026298DCC9D8>, <function <lambda> at 0x0000026298DCCA60>, <function <lambda> at 0x0000026298DCCAE8>, <function <lambda> at 0x0000026298DCCB70>, <function <lambda> at 0x0000026298DCCBF8>]
'''
```
函数如果被调用示例：
```python
func_list = []
for i in range(10):
    func_list.append(lambda: i)  # 函数不被调用，内部永远不执行

func_list[0]()
func_list[1]()
func_list[2]()
func_list[3]()
func_list[4]()
func_list[5]()
func_list[6]()
func_list[7]()
func_list[9]()
```
##### 4. 函数的参数
###### 4.1 函数的参数
```python
# coding:utf-8
def get_list_data(data): # data是形式参数（形参）
    lst = ['thanlon', 'kiku']
    print(lst[data])
    
print(get_list_data(0)) # 0是实际参数（实参）
print(get_list_data(1)) # 1是实际参数（实参）
```
练习1：写一个函数，函数计算指定列表[11,22,33,44,55]中所有元素的和
```python
# coding:utf-8
'''
写一个函数，函数计算指定列表[11,22,33,44,55]中所有元素的和
'''
def sum_list_item():
    lst = [11, 22, 33, 44, 55]
    sum = 0
    for item in lst:
        sum += item
    print(sum)

sum_list_item()
'''
165
'''
```
练习2：写一个函数，函数计算制定列表种所有元素的和
```python
# coding:utf-8
'''
写一个函数，函数计算制定列表种所有元素的和
'''
def sum_list_item(lst):
    sum = 0
    for item in lst:
        sum += item
    print(sum)

sum_list_item([11, 22, 33, 44, 55])
'''
165
'''
```
练习3：写一个函数，函数将两个列表拼接起来
```python
# coding:utf-8
'''
写一个函数，函数将两个列表拼接起来
'''
def sum_list_item(lst1, lst2):
    lst = []
    lst.extend(lst1)
    lst.extend(lst2)
    print(lst)

sum_list_item([11, 22, 33, 44, 55], [66, 77, 88, 99])
'''
[11, 22, 33, 44, 55, 66, 77, 88, 99]
'''
```
练习4：计算一个列表的长度
```python
# coding:utf-8
'''
计算一个列表的长度
'''
def my_lenth(arg):
    count = 0
    for item in arg:
        count += 1
    print(count)
my_lenth([11, 22, 33, 44, 55])
'''
5
'''
```
###### 4.2 面试题:函数的参数传递的是什么
函数的参数传递的是什么？
```python
'''
函数的参数传递的是什么？
函数的参数传递的是内存地址
'''
v = [1, 2, 3]

def fun(args): # args也指向v的地址，说引用
    print(id(args))  # 列表的内存地址

fun(v)
print(id(v))  # 列表的内存地址
'''
1602601902664
1602601902664
'''
```
###### 4.3 函数参数的传递
① 参数传递概念
参数可以传任意个数，可以是任意类型。实际参数要与形式参数个数一致，不能多，也不能少。函数

② 位置传参(执行)
实参与形参按照位置顺序一次对应
```python
def func(a1, a2):
    pass
func(1, 2)
```
③ 关键字传参(执行)
采用关键字传参，参数位置可以调整，根据关键字名
```python
def func(a1, a2):
    pass
func(a1=1, a2=2)
```
④ 位置参数与关键字参数混合使用(执行)
关键字参数可以和位置参数混合使用，但是传入的顺序是位置参数在前，关键字参数在后。
```python
def func(a1, a2, a3):
    pass

func(1, 2, a3=3)
func(1, a2=2, a3=3)
func(a1=1, a2=2, a3=3)
'''
func(a1=1, 2, 3)  # 错误
func(a1=1, 2, a3=3)  # 错误
func(a1=1, a2=2, 3)  # 错误
'''
```
⑤ 默认参数(定义)
默认参数，可传可不传。如果传参，覆盖掉原来的值，否则使用默认值。
```python
def func(a1, a2, a3=3, a4=4):
    pass
func(1, 2)
func(1, 2, 3)
func(1, 2, 3, 4)
func(1, 2, 3, a4=44)
```
⑥ 万能参数(参数打散)
不确定可以传入多少参数时可以使用。*args参数不支持关键字传参，只支持位置传参，可以接收任意个数的位置参数，并将参数转换成元组。
- *args
```python
# coding:utf-8
'''
不确定可以传入多少参数，接收任意数量的参数，*args不支持关键字传参，只支持位置传参
'''
def func(*args):  # 一般情况下写args：参数
    print(args)

func(1)  # args = (1,)
func(1, 2)  # args=(1, 2)
func(1, 2, 'thanlon', [1, 2])  # args =(1, 2, 'thanlon', [1, 2])
func((1, 2, 3))  # args =((1, 2, 3),)
func(*(1, 2, 3))  # args =(1, 2, 3)
'''
'''
```
```python
def func2(a1, *args):  # 一般情况下写args：参数
    print(a1)

func2(a1=1)
# func2(a1=1,1)#违反位置参数在关键字参数后
```
```python
def func2(*args, a1):  # 一般情况下写args：参数
    print(a1)

func2(1, 2, 3, a1=4)
```
```python
def func(a1=1, *args, a2):  # 一般情况下写args：参数
    print(a1, args, a2)
    
func(11, 2, 3, a2=4)
'''
11 (2, 3) 4
'''
```
- **kwargs
可以接收任意个数的关键字参数，并将参数转换成字典。
```python
# coding:utf-8
def fun(**kwargs):  # kwargs：键值参数
    print(kwargs)
    
fun(k1=1, k2='thanlon')  # kwargs = {'k1':1,'k2':'thanlon'}
fun(**{'k1': 'v1'})  # kwargs ={'k1': 'v1'}
```
- *args与**kwargs的综合使用
```python
# coding:utf-8
def fun(*args, **kwargs):
    print(args, kwargs)

fun(1, 2, 3, k1=1, k2=2)  # (1, 2, 3) {'k1': 1, 'k2': 2}
# fun(k3=3, 1, 2, 3, k1=1, k2=2)  #错误
fun(*[1, 2, 3], 2, 3, k1=1, k2=2)  # (1, 2, 3, 2, 3) {'k1': 1, 'k2': 2}
# fun(**[1, 2, 3], 2, 3, k1=1, k2=2)  # 错误
fun(*[1, 2, 3], **{'k1': 1, 'k2': 2})  # (1, 2, 3) {'k1': 1, 'k2': 2}
fun(1, 2, 3 * [1, 2, 3], **{'k1': 1, 'k2': 2})  # (1, 2, [1, 2, 3, 1, 2, 3, 1, 2, 3]) {'k1': 1, 'k2': 2}
fun(1, 2, 3 * [1, 2, 3], k3=3,**{'k1': 1, 'k2': 2})  # (1, 2, [1, 2, 3, 1, 2, 3, 1, 2, 3]) {'k3': 3, 'k1': 1, 'k2': 2} ，特殊情况:违背位置参数在前面
```
⑦ 参数的重点(工作常用到的)
定义函数：
```python
def func1(a,b):
	pass
def func2(a,b=None):
	pass
def func3(*args,**kwargs):
	pass
```
调用函数：位置参数在关键字参数之前

⑧ 面试题（概率高）
<kbd>对于函数参数的默认值慎用可变类型，理解下面的例子，你就知道这个坑了……</kbd>
```python
# coding:utf-8
'''
问题1：def func(a,b=[])有什么陷阱？
如果第二个参数没有传入，在函数作用域会使用空列表，空列表会一直存在；如果传入，在列表作用域中会使用传入的列表。
问题2：看代码写结果？
'''
def func(a, b=[]):
    b.append(a)
    return b

lst01 = func(1)  # 此时b=[1]
lst02 = func(1, [1, 2, 3])  # 传递的参数是列表
lst03 = func(2)  # 此时b = [1,2]

print(lst01)
print(lst02)
print(lst03)
'''
[1, 2]
[1, 2, 3, 1]
[1, 2]
'''
```
为加深理解，再给一个例子：
```python
def func(a, b=[]):
    b.append(a)
    print(b)

func(1)
func(1, [1, 2, 3])
func(2)
'''
[1]
[1, 2, 3, 1]
[1, 2]
'''
```
##### 5. 函数的返回值
注意：无返回的函数实际返回None

###### 5.1 无参数无返回值
```python
# coding:utf-8
# 情况1：无参数、无返回值
def f1():
    pass
f1()
```
###### 5.2 有参数无返回值
```python
# 情况2：有参数、无返回值
def f1(arg):
    pass
    
f1(123)
```
###### 5.3 无参数有返回值
```python
# 情况3：无参数、有返回值
def f1():
    return 1
    
v1 = f1()
```
###### 5.3 有参数有返回值
```python
# 情况4:有返回值有参数的
def f1(arg):
    return 1
    
v2 = f1(123)
```
###### 5.4 特殊情况:返回元组
```python
# coding:utf-8
'''
特殊：返回元组
'''
def func():
    return 1, 2, 3, 'thanlon'

v = func()
print(v)
'''
(1, 2, 3, 'thanlon')
'''
```
###### 5.2 参数传递练习题
① 用户输入一段字符串，计算字符串中有多少个A字符？将这些A字符写入A.txt文件中
```python
# coding:utf-8
'''
用户输入一段字符串，计算字符串中有多少个A字符？将这些A字符写入A.txt文件中
'''
def get_str_count(arg):
    count = 0
    for item in arg:
        if item == 'A':
            count += 1
    return count

def write_str(data):
    if data == False:  # 或者len(data)==0
        return False  # 函数执行过程中，一旦遇到return，则停止函数的执行
    with open('A.txt', 'w', encoding='utf-8') as f:
        f.write(data)
    return True

content = input('请输入一段字符串：')
counter = get_str_count(content)
data = 'A' * counter
status = write_str(data)
if status:
    print('写入成功！')
else:
    print('写入失败！')
```
① 写一个函数，计算列表中有多少个数字，并打印出列表中数字的个？
```python
# coding:utf-8
'''
问题：写一个函数，计算列表中有多少个数字，并打印出列表中数字的个
'''
def count_list_num(args):
    count = 0
    for item in args:
        if type(item) == int:
            count += 1
    print('列表中有%d个数字' % count)

count_list_num([1, 2, 3, 'thanlon'])
'''
列表中有3个数字
'''
```
③ 写一个函数，将一个列表中偶数索引位置的数据构造成另外一个列表
```python
# coding:utf-8
'''
写一个函数，将一个列表中偶数索引位置的数据构造成另外一个列表
方法1
'''
def get_data_list(arg):
    lst = []
    for i in range(len(arg)):
        if i % 2 == 0:
            lst.append(arg[i])
    return lst

data = get_data_list([1, 2, 3])
print(data)
'''
[1, 3]
'''
```
```python
# coding:utf-8
'''
写一个函数，将一个列表中偶数索引位置的数据构造成另外一个列表
方法2
'''
def get_data_list(arg):
    v = arg[::2]
    return v

data = get_data_list([1, 2, 3])
print(data)
'''
[1, 3]
'''
```
##### 7. 函数的作用域
###### 7.1 作用域分类
作用域分为全局作用域和部分作用域，函数的作用域属于局部作用域。在python中，python文件是一个全局的作用域，函数是局部作用域。局部作用域可以用自己的数据，还可以用全局作用域中的。但是，全局作用只能用自己的数据。

###### 7.2 全局作用域与局部作用域
① 全局变量以后必须大写
② 一个函数就是一个作用域（其它语言不是，如：java是以代码块）
③ 作用域中查找数据规则：优先在自己的作用域中找数据，自己没有就去“父级”，还没有就去“父级”的“父级”，直到全局作用域。

全局作用只能用自己的数据，不能使用局部作用域的数据：
```python
# coding:utf-8
a = 1
def f():
    b = 2
print(b)  # NameError: name 'b' is not defined
```
局部作用域找数据优先在自己内部找，如没有到全局中找：
```pthon
# coding:utf-8
x = 10

def f1():
    x = 1
    print(x)

f1()
'''
1
'''
```
```python
# coding:utf-8
x = 1

def func():
    x = 2
    print(x)
    def func2():
        x = 3
        print(x)

    print(x)
    func2()
func()
'''
2
2
3
'''
```
```python
# coding:utf-8
x = 1

def func():
    x = 2
    print(x)
    def func2():
        print(x)
    x = 3
    func2()
    x = 10
    print(x)

func()
'''
2
3
10
'''
```
```python
# coding:utf-8
item = 4
for item in range(10):  # 这个item在全局也可以使用
    pass
print(item)  # 9
```
```python
# coding:utf-8
item = 10

def func():
    item = 8
    for item in range(10):  # 这个item在全局也可以使用
        pass
    print(item)

func()
print(item)
'''
9
10
'''
```
```python
# coding:utf-8
item = 10

def func():
    item = 8

    def inner():
        print(item)

    for item in range(10):  # 这个item在全局也可以使用
        pass
    inner()

func()
'''
9
'''
```
局部作用域既可以用自己的变量，也可以用全部作用域中的（自己没有的数据到全局作用域中找）：
```python
# coding:utf-8
a = 1
def f():
    print(c)
c = 2
f()
```
但是，当函数的局部作用域使用全局作用域中的数据，而全局作用域中的数据在调用函数的后面。这种情况局部作用域是不能使用全局作用域中的数据，如：
```python
# coding:utf-8
a = 1
def f():
    print(c)
f()
c = 2
```
函数之间可以调用，但是一个函数调用的函数只能是全局中有的函数：
```python
# coding:utf-8
def f1():
    def f3():
        pass

def f2():
    f1()
    f3()  # 不能调用f3函数
```
子作用域只能找到父级中的值，默认无法重新为父级的变量进行赋值：
```python
# coding:utf-8
'''
在自己的作用域再创建一个这样的值
'''
name = 'thanlon'

def func():
    name = '奈何'  # 在自己的作用域再创建一个这样的值
    print(name)

func()
print(name)
'''
奈何
thanlon
'''
```
全局变量可以读，但是修改时，变量需要是可变类型：
```python
# coding:utf-8
name = [1, 2, 3]

def func():
    name.append(4)#不是重新赋值，是修改可变类型变量的值
    print(name)

func()
print(name)
'''
[1, 2, 3, 4]
[1, 2, 3, 4]
'''
```
如果非要对全局的变量进行赋值，可使用global与nolocal关键字。

###### 7.3 global与nolocal关键字
① global关键字：找到全局的变量，方便修改变量
```python
# coding:utf-8
name = 'thanlon'

def func():
    global name
    name = 'kiku'
    print(name)

func()
print(name)
'''
kiku
kiku
'''
```
```python
# coding:utf-8
name = ['thanlon', 'kiku']

def func():
    global name
    name = [] # 想赋什么值赋什么值
    print(name)
    name = 'thanlon'

func()
print(name)
'''
[]
thanlon
'''
```
```python
# coding:utf-8
'''
global关键字的应用
'''
name = 'thanlon'

def func():
    name = 'kiku'
    def inner():
        global name
        name = 'haha'
    inner()
    print(name)

func()
print(name)
'''
kiku
haha
'''
```
###### 7.4 nolocal关键字
找到上一级的变量，方便进行修改。
```python
# coding:utf-8
'''
nonlocal
'''
name = 'thanlon'

def func():
    name = 'kiku'
    def inner():
        nonlocal name  # 找到上一级（父级）变量name
        name = 'haha'
    inner()
    print(name)

func()
print(name)
'''
haha
thanlon
'''
```
###### 7.4  函数作用域练习(面试题)
看代码写结果：
```python
def func():
	for num in range(10):
		pass
	v4 = [lambda:num+10,lambda:num+100,lambda:num+100]
	result1 = v4[1]()
	result2 = v4[2]()
	print(result1,result2)
func()
```
【答案】：109 109（比较简单）

引申：
```python
# coding:utf-8
def func():
    for num in range(10):
        pass
    v4 = [lambda: num + 10, lambda: num + 100, lambda: num + 100]
    result1 = v4[1]()
    num = 100
    result2 = v4[2]()
    print(result1, result2)

func()
'''
109 200
'''
```
##### 8. 函数初级
###### 8.1 函数名当作变量传递
```python
# coding:utf-8
# 将函数名赋值给一个变量
def func():
    print('func')

func2 = func
func2()
'''
func
'''
```
```python
# coding:utf-8
'''
函数可以当作列表中的元素
'''
def func():
    print('func')

func_list = [func, func, func]
func_list[0]()
func_list[1]()
func_list[2]()
'''
func
func
func
'''
```
```python
# coding:utf-8
'''
函数放集合中
'''
def func():
    print('func')

func_set = {func, func, func}
for item in func_set:
    item()
'''
func
'''
```
```python
# coding:utf-8
'''
函数放在字典中
'''
def func():
    print('func')

def bar():
    print('func')

func_dict = {'k1': func, 'k2': bar}
func_dict['k1']()
func_dict['k2']()

'''
func
func
'''
```
```python
# coding:utf-8
'''
函数也可以当作字典的key，但一般是当作v
'''
def func():
    print('func')
func_dict = {func: 'func()'}
```
```python
# coding:utf-8
def func():
    pass

func_list = [func, func, func]  # 函数的地址
func_list2 = [func(), func(), func()]  # 执行函数，列表中放函数的返回值
print(func_list)
print(func_list2)
'''
[<function func at 0x0000026D8E65C1E0>, <function func at 0x0000026D8E65C1E0>, <function func at 0x0000026D8E65C1E0>]
[None, None, None]
'''
```
```python
# coding:utf-8
def func():
    pass

info = {
    'k1': func,
    'k2': func()
}
print(info)
'''
{'k1': <function func at 0x000001A182EBC1E0>, 'k2': None}
'''
```
###### 8.2 函数名当作参数传递
```python
# coding:utf-8
def func(arg):
    print(arg)
def show():
    pass
func(show)  # 将函数地址传入
func(show())  # 首先执行函数，然后把函数的返回值传入
'''
<function show at 0x000001BEA551B7B8>
None
'''
```
```python
# coding:utf-8
def func(arg):
    print(arg())

def show():
    print(666)

func(show)
'''
666
None
'''
```
```python
# coding:utf-8
def func(arg):
    print(arg())

def show():
    print(666)

res = func(show)
print(res)
'''
666
None
None
'''
```
###### 8.3 函数初级练习题(面试题)
```python
# coding:utf-8
'''
根据用户选择编号执行对应的函数
'''
def func1():
    print('func1')

def func2():
    print('func1')

def func3():
    print('func1')

def func4():
    print('func1')

while True:
    choice = input('请输入要执行的函数名：')
    func_dict = {
        'func1': func1,
        'func2': func2,
        'func3': func3,
        'func4': func4
    }
    func_name = func_dict.get(choice)  # 找到返回value，找不到返回None
    if func_name:
        func_name()
    else:
        print('没有找到这个key!')
```
##### 9. lambda表达式
###### 9.1 lambda表达式结构
<kbd>函数名 = lambda 参数:函数返回值 </kbd>

###### 9.2 三元运算与lambda
① 三元运算：为了解决简单的if else的情况，如：
```python
# coding:utf-8
if 1 == 1:
    a = 123
else:
    a = 456
    
a = 123 if 1 == 1 else 456
```
② lambda表达式：为了解决简单函数的情况，如：
```python
# coding:utf-8
def func(a1, a2):
    return a1 + a2

func1 = lambda a1, a2: a1 + a2
print(func1)
print(func1(1, 2))
'''
<function <lambda> at 0x0000027F4BB5C7B8>
3
'''
```
###### 9.3 lambda几种写法
```python
# coding:utf-8
func = lambda: 100
print(func())
'''
100
'''
```
```python
# coding:utf-8

func = lambda x1: x1 ** 2
print(func)
print(func(10))
'''
<function <lambda> at 0x0000026AAD7EC1E0>
100
'''
```
```python
# coding:utf-8

func = lambda *args, **kwargs: len(args) + len(kwargs)
print(func)
print(func(10, 20, 'thanlon', {'k1': 'v1'}, {'k2': 'v2'}))
'''
<function <lambda> at 0x000001F1FF71C1E0>
5
'''
```
```python
# coding:utf-8

DATA = 100
func = lambda a1: a1 + DATA
print(func(100))
'''
200
'''
```
```python
# coding:utf-8
DATA = 10

def func():
    DATA = 100
    func2 = lambda a1: a1 + DATA
    v = func2(100)
    print(v)

func()
'''
200
'''
```
```python
# coding:utf-8

func = lambda n1, n2: n1 if n1 > n2 else n2
v = func(12, 13)
print(v)
'''
13
'''
```
###### 9.3 lambda练习题
练习一：
```python
# coding:utf-8
USER_LIST = []

def func(x):
    v = USER_LIST.append(x)  # 返回None，一般列表不返回新值
    return v

res = func('thanlon')
print(res)
'''
None
'''
```
练习二：
```python
# coding:utf-8
def func(x):
    v = x.strip()
    return v

res = func('thanlon ')
print(res)
'''
thanlon
'''
```
练习三：
```python
# coding:utf-8
USER_LIST = []

func = lambda x: USER_LIST.append(x)

res = func('thanlon')
print(res)
print(USER_LIST)
'''
None
['thanlon']
'''
```
练习四：
```python
# coding:utf-8
func = lambda x: x.split('l')
v = func('thanlon')
print(v)
'''
['than', 'on']
'''
```
练习五：
```python
# coding:utf-8
func_list = [lambda x: x.strip(), lambda y: y + 199, lambda x, y: x + y]
v1 = func_list[0]('thanlon')
v2 = func_list[1](1)
v3 = func_list[2](1, 2)
print(v1, v2, v3)
'''
thanlon 200 3
'''
```
###### 9.3 匿名函数(面试)
什么是匿名函数？
lamda表达式也称为匿名函数，<kbd>v = [lambda x:x+100,lambda x:x+100,]</kbd>。
下面不是匿名函数：
```python
def func():
	pass
```
##### 10. 内置函数
以上都是自定义函数，这里详细谈内置函数。
###### 10.1 数学相关的内置函数
- abs()：取绝对值
```python
# coding:utf-8
'''
abs()：取绝对值
'''
v = abs(-1)
print(v) # 1
```
- float()：转换成浮点型（小数）
```python
# coding:utf-8
'''
float()：转换成浮点型（小数）
'''
v = float(55)
print(v)  # 55.0
```
- max()/min()：找到最大值/最小值
```python
# coding:utf-8
'''
max():找到最大值
min():找到最小值
'''
lst = [1, 2, 3]
print(max(lst))
print(min(lst))
'''
3
1
'''
```
- sum()：求和
```python
# coding:utf-8
lst = [1, 2, 3]
print(sum(lst))
'''
6
'''
```
- divmod()：两数相除的商和余
```python
# coding:utf-8
'''
求商和余数
'''
res = divmod(1001, 3)
print(res)  # (200, 0)
a, b = divmod(1001, 3)
print(a, b)  # 333 2
```
- pow(a,b)：求a的b次方
```python
# coding:utf-8
print(pow(2, 3))
```
- round(a,n)：保留小数（四舍五入）
```python
# coding:utf-8
print(round(1.205020, 2))  # 1.21
```
练习题：内置函数应用(分页)
```python
# coding:utf-8
'''
每页显示10页数据，用户根据输入的页面找到对应的数据
'''
every_data_count= 10
user_list = []
for i in range(0,105):
    temp = {
        'email':'20190801%s@sina.com'%i
    }
    user_list.append(temp)

sum_data = len(user_list)
max_page_num,a = divmod(sum_data,every_data_count)

if a>0:
    max_page_num +=1

page = int(input('您需要查看第几页：'))
if page>max_page_num or page<1:
    print('页码不合法，必须是1~%s'%max_page_num)
else:
    #第一页：[0,10]
    #第一页：[10,20]
    #第一页：[20,40]
    start = (page-1)*10
    end = page*10
    # print(user_list[start:end])
    for item in user_list[start:end]:
        print(item)
```
###### 10.2 输入输出的内置函数
- input()
- print()

###### 10.3 强制转换的内置函数
- dict()
- list()
- tuple()
- int()
- str()
- bool()
- set()

###### 10.4 进制转换的内置函数
- bin：将十进制转换为二进制
```python
# coding:utf-8
# 将十进制转换成二进制
v = 10
result = bin(v)
print(result) # 0b1010
```
- oct：将十进制转换成八进制
```python
# coding:utf-8
# 将十进制转换成八进制
v = 10
result = oct(v)
print(result)  # 0o12
```
- hex：将十进制转换成十六进制
```python
# coding:utf-8
# 将十进制转换成十六进制
v = 10
result = hex(v)
print(result)  # 0xa
```
- int：将其它进制转换成十进制
```python
'''
默认转换成10进制
'''
# coding:utf-8
v = '123456'
result = int(v)  # 默认转换成10进制
print(result)  # 123456
```

```python
# coding:utf-8
# 将二进制转换为十进制
v = '0b1010'
result = int(v, 2)
print(result)  # 10
```
```python
# coding:utf-8
# 将八进制转换为十进制
v = '0o12'
result = int(v, 8)
print(result)  # 10
```
```python
# coding:utf-8
# 十六进制转换成十进制
v = '0xa'
result = int(v, 16)
print(result)  # 10
```
###### 10.5 编码相关的内置函数
① 将十进制转换成unicode编码中的对应字符[chr(int)]
unicode包括ASCII码，chr函数在python3之后才是unicode，之前只能表示ASCII码。
```python
# coding:utf-8
v = chr(99)
print(v)  # c
```
② 根据字符转换成unicode编码中对应的十进制[ord()]
```python
# coding:utf-8
'''
ord：根据字符在unicode编码中找到其对应的十进制
'''
v = ord('中')
print(v)  # 20013
```
```python
# coding:utf-8
'''
ord：根据字符在unicode编码中找到其对应的十进制
'''
v = '奈何'
for item in v:
    val = ord(item)
    print(val)  # 20013
'''
22856
20309
'''
```
③ 应用:随机验证码

<kbd>import random</kbd>：导入一个random模块

<kbd>v = random.randint(start,end)</kbd>：得到一个随机数
```python
# coding:utf-8
import random

def get_random_code(lenth=4):
    data_list = []
    for i in range(0, lenth):
        v = random.randint(65, 90)
        data_list.append(chr(v))
    # print(data_list)
    return ''.join(data_list)

print(get_random_code())
```
###### 10.5 其它
- len()
- open()
- range(0
- id()
- type()

⑥ 内置函数相关应用:ip地址转换（面试题）
- 面试热身（非面试题）
请将 ip = “192.168.0.1”中的每一个十进制数转换为二进制，并通过“,”（逗号）将二进制连接起来组成一个新的字符串（0b11000000,0b10101000,0b0,0b1）。
```python
# coding:utf-8
'''
ip = '192.168.0.1'------>'0b11000000,0b10101000,0b0,0b1'
'''
ip = '192.168.0.1'
ip_list = ip.split('.')
result = []
for item in ip_list:
    result.append(bin(int(item)))
print(','.join(result))
'''
0b11000000,0b10101000,0b0,0b1
'''
```
- 面试题
请将 ip = “192.168.0.1”中的每一个十进制数转换位二进制，将得到的二进制（去掉中间的点）转换成十进制数。
```python
# coding:utf-8
'''
ip = '192.168.0.1'------>'11000000101010000000000000000001'->3232235521
'''
ip = '192.168.0.1'
ip_list = ip.split('.')
result = []
result_bin = ''
for item in ip_list:
    item_bin = bin(int(item))[2:]
    # print(item_bin)
    '''
    11000000
    10101000
    0
    1
    '''
    if len(item_bin) < 8:
        item_bin = '0' * (8 - len(item_bin)) + item_bin
    # print(item_bin)
    '''
    11000000
    10101000
    00000000
    00000001
    '''
    result_bin += item_bin
print('0b' + result_bin)  # 0b11000000101010000000000000000001（其实不加0b也是可以的）
print(int(result_bin, base=2))
'''
3232235521
'''
```
上面使用的是字符串，下面使用列表，当然使用列表还是使用字符串在这里不是重点：
```python
# coding:utf-8
'''
ip = '192.168.0.1'------>'0b11000000,0b10101000,0b0,0b1'
'''
ip = '192.168.0.1'
ip_list = ip.split('.')
result = []
result_bin = ''
for item in ip_list:
    item_bin = bin(int(item))[2:]
    # print(item_bin)
    '''
    11000000
    10101000
    0
    1
    '''
    if len(item_bin) < 8:
        item_bin = '0' * (8 - len(item_bin)) + item_bin
    # print(item_bin)
    '''
    11000000
    10101000
    00000000
    00000001
    '''
    result.append(item_bin)
print(result)  # ['11000000', '10101000', '00000000', '00000001']
result = '0b' + ''.join(result)
print(result)  # 0b11000000101010000000000000000001
print(int(result, base=2))
'''
3232235521
'''
```
##### 11. 函数中级
###### 11.1 函数可以做返回值
```python
def func1():
    print(123)
def func2():
    return func1
v = func2()
v()
```
```python
name = 'thnalon'
def func1():
    print(name)
def func2():
    return func1
v = func2()
v()  # thnalon
```
```python
name = 'thnalon'

def func():
    def inner():
        print(123)
    return inner

v = func()
v()
'''
123
'''
```
```python
name = 'thnalon'

def func():
    name = 'kiku'

    def inner():
        print(name)
    return inner

v = func()
v()
'''
kiku
'''
```
```python
name = 'thnalon'

def func(name):
    def inner():
        print(name)
    return inner

v = func('kiku')
v()
'''
kiku
'''
```
###### 11.2 闭包
闭包：为函数创建一块区域为其维护自己的数据，以后执行时方便调用。
闭包应用场景：装饰器/SQLALchemy源码
补充：只要函数名加()，就会在内存空间开辟一块内存。
```python
name = 'haha'

def func(name):
    def inner():
        print(name)
    return inner

v = func('kiku')  # 开辟内存，内存中{name = kiku，inner}为函数创建一块区域（内部变量供自己使用），为它以后执行提供数据。
v2 = func('thanlon')  # 开辟内存，内存中{name = thanlon，inner}
v() # 函数执行后，函数中的数据在内存中被销毁
v2() # 函数执行后，函数中的数据在内存中被销毁
'''
kiku
thanlon
'''
```
关于闭包可以记下面的例子：
```python
# coding:utf-8
'''
函数嵌套函数，并且第一层函数返回嵌套函数的函数名
'''
def func(name):
    def inner():
        print(name)
    return inner

print(func('th'))
'''
thanlon
'''
```
看下面一个例子，真正区分什么是闭包。封装了值，并且还要用，这样才是闭包。
```python
# 不是闭包，封装了name值，但是在内层函数中没有使用
def func(name):
    def inner():
        return 123

    return inner
```
```python
# 是闭包，封装了值，还需要在内层函数中使用
def func2(name):
    def inner():
        print(name)
        return 123

    return inner
```
###### 11.3 内置高阶函数
 - 对函数进行赋值
 - 把函数当作返回值

 注意：可以对函数进行赋值
###### 11.4  函数练习题
自己没有函数，执行父类中的函数:
```python
name = 'thanlon'

def base():
    print(name)

def func():
    name = 'kiku'
    base() # 自己没有base函数，执行父类中的base函数

func()
'''
thanlon
'''
```
```python
name = 'thanlon'

def func():
    name = 'kiku'
    def base():
        print(name)
    base()  # 自己没有base函数，执行父类中的base函数

func()
'''
kiku
'''
```
###### 11.5 函数面试题
```python
# coding:utf-8
info = []

def func():
    print(item)

for item in range(10):
    info.append(func)
info[0]()
'''
9
'''
```
理解下面这个题，差不多就彻底明白了：
```python
# coding:utf-8
info = []

def func(i):
    def inner():
        print(i)
    return inner

for item in range(10):
    info.append(func(item))
info[0]()
info[1]()
info[2]()
'''
0
1
2
'''
```
###### 11.6 总结
```python

def func(arg):
    def inner():
        return arg
    return inner

base_list = []
func_list = []
for i in range(10):
    base_list.append(base)
    func_list.append(func(i))
# print(base_list)
# print(func_list)
'''
base_list与func_list中分别保存什么？
base_list中存储的都是base函数
func_list中存储的都是inner函数，但是每个inner是在不同的地址创建的
'''
'''
如果循环打印什么？
'''
for data in base_list:
    v = data()
    print(v)  # 9 9 9 9...9
for data in func_list:
    v = data()
    print(v)  # 0 1 2 3 ... 9
```
- 传参：位置参数在前，关键字参数在后、
- 函数不被调用，内部代码永远不执行
- 每次调用函数时，都会为此次调用开辟一块内存，内存中保存自己以后以后想要用的值
- 函数是作用域，如果自己作用域中没有，则往上级作用域找

##### 13. 函数高级
###### 13.1 常用的内置函数(面试)
常见的内置函数：open、id、type、len、range
###### 13.2 filter/map/reduce(面试)
- filter
对序列中的元素进行筛选，最终获取符合条件的序列
```python
# coding:utf-8
v = [1, 2, 3, 'thanlon', 'kiku']

def func(x):
    return True
'''
如果函数返回True，将v中的元素添加到空列表中
'''
result = filter(func, v)
print(result)  # <filter object at 0x0000027D637CAC18>
print(list(result))  # [1, 2, 3, 'thanlon', 'kiku']
```
```python
# coding:utf-8
v = [1, 2, 3, 'thanlon', 'kiku']

def func(x):
    if type(x) == int:
        return True
    return False

'''
如果函数返回True，将v中的对应的元素添加到空列表中
'''
result = filter(func, v)
# print(result)  # <filter object at 0x0000027D637CAC18>
print(list(result))  # [1, 2, 3]
'''
[1, 2, 3]
'''
```
使用lambda表达式简化： 
```python
# coding:utf-8
v = [1, 2, 3, 'thanlon', 'kiku']

def func(x):
    # if type(x) == int:
    #     return True
    # return False
    # return type(x) == int
    return True if type(x) == int else False
'''
如果函数返回True，将v中的对应的元素添加到空列表中
'''
# result = filter(func, v)
# result = filter(lambda x:type(x) == int, v)
result = filter(lambda x: True if type(x) == int else False, v)
print(list(result))
'''
[1, 2, 3]
'''
```
- map
循环每个元素（第二个参数），然后让每个元素执行函数（第一个参数），将每个函数执行的结果保存到新的列表中并返回。
```py
'''
每个元素增加100
'''
v = [1, 2, 3]
for i in range(0, len(v)):
    v[i] += 100
print(v)
'''
[101, 102, 103]
'''
```
```py
'''
每个元素增加100
map一执行会循环终端中每一个元素，会将返回值添加到空列表中[]。
'''
v = [1, 2, 3]

def func(args):
    print(args)
    return args + 100

# 第一个参数：必须是一个函数
# map第二个值：必须是可迭代类型（可迭代类型就是可以被for循环的，字符串、列表、字典、集合）

result = map(func, v)
# print(result)  # <map object at 0x000001C6EB12E908>
print(list(result))
'''
1
2
3
[101, 102, 103]
'''
```
使用lambda表达式简化： 
```python
# coding:utf-8
v = [1, 2, 3]

def func(args):
    return args + 100

# result = map(func, v)
result = map(lambda args: args + 100, v)
# print(result)  # 在python2中，是[101, 102, 103]
# print(result)  # 在python3中返回的是map对象，节省内存不展示，<map object at 0x00000225348DF908>
# 如果想拿到result中的值，转换成列表
print(list(result))
'''
[101, 102, 103]
'''
```
- reduce
对序列内所有元素进行累计操作
```python
# coding:utf-8
import functools
v = [1, 2, 3]
def func(x, y):  # 需要有两个参数
    print(x, y)

result = functools.reduce(func, v)
print(result)
'''
1 2
None 3
None
'''
```
```python
# coding:utf-8
import functools

v = [1, 2, 3]

# 第一次函数参数是1和2
# 第二次函数参数是3和3
# 第一次函数返回什么，第二次函数中第一个参数就是什么
def func(x, y):  # 需要有两个参数
    return x + y

result = functools.reduce(func, v)
print(result)
'''
6
'''
```
```python
# coding:utf-8
import functools
v = ['I', 'Love', 'Kiku']

def func(x, y):  # 需要有两个参数
    return x + ' ' + y

result = functools.reduce(func, v)
print(result)
'''
I Love Kiku
'''
```
使用lambda表达式简化:
```python
# coding:utf-8
import functools

v = ['I', 'Love', 'Kiku']

result = functools.reduce(lambda x, y: x + ' ' + y, v)
print(result)
'''
I Love Kiku
'''
```
##### 14. 递归
###### 14.1 什么是递归
函数自己调用自己。函数的递归效率低，因为每次调用函数，都要新开辟一块内存，也就是说内存不断在消耗。递归可以用，但是不到非用不可就不用，尽量通过循环来做。

###### 14.2 默认递归限制的最大次数(面试题)
<kbd>In [1]: import sys</kbd>

<kbd>In [2]: dir(sys)</kbd>

<kbd>In [3]: sys.getrecursionlimit()</kbd>-><kbd>Out[3]: 1000</kbd>

python中默认递归限制的最大次数是1000次。

###### 14.3 递归例子
- 例1
```python
def func(i):
    print(i)
    func(i+1)
func(1)
```
- 例2
```python
# coding:utf-8
'''
使用递归产生斐波那契数列
'''
def func(a, b):
    print(b)
    func(b, a + b)

func(0, 1)
```
- 例3
```python
# coding:utf-8
def func(a):
    if a == 5:
        return 100
    result = func(a + 1) + 10
    return result

val = func(1)
print(val)  # 140=100+10*4
'''
140
'''
```
##### 15. python常见内置函数
|调用语法|描述  |
|--|--|
| **abs(x)** | 返回数字的绝对值 |
|**all(iterable)**|对于迭代对象iterable中的每一个元素e，如果bool(e)为True,那么返回True|
|**any(iterable)**|对于迭代对象iterable中至少存在一个元素e，使bool(e)为True，那么返回True|
|**chr(integer)**|返回给定Unicode编码的字符|
|**divmod(x,y)**|如果x和y都是整数，返回元祖(x//y,x%y)|
|**hash(obj)**|对于对象obj返回一个整数的散列值|
|**id(obj)**|返回作为对象身份标识的唯一整数|
|**input(prompt)**|返回标准输入的字符串，prompt是可选的|
|**isinstance(obj,cls)**|确定对象是类的一个实例（或子类），如果是则返回True|
|**iter(iterable)**|为参数返回一个新的迭代对象|
|**len(iterable)**|返回给定迭代对象的元素个数|
|**map(f,iter1,iter2,……)**|返回迭代器产生的函数调用f(e1,e2,……)的结果，其中元素e1属于iter1，e2属于iter2，……|
|**max(iterable)**|返回给定迭代对象中的最大元素|
|**max(a,b,c,……)**|返回给定参数中最大的元素|
|**min(iterable)**|返回给定迭代对象中的最小元素|
|**min(a,b,c,……)**|返回给定参数中最小的元素|
|**next(iterable)**|通过迭代器返回下一个元素|
|**open(filename,mode)**|通过给定的模式和存储模式打开文件|
|**ord(char)**|返回给定字符的Unicode编码值|
|**pow(x,y)**|返回x^y的值(当x和y的类型为整型时值为整型)，等价于x**y|
|**pow(x,y,z)**|返回整型值（x^y mod z）|
|**print(obj1,obj2,……)**|打印参数，参数之间以空格分隔，打印完毕后换行|
|**range(stop)**|构造关于值0,1,……，stop-1的迭代|
|**range(start,stop)**|构造关于值start,start+1,……，stop-1的迭代|
|**range(start,stop,step)**|构造关于值start,start+step,start+2step,……,stop的迭代|
|**reversed(sequence)**|反向逆置序列|
|**round(x)**|返回最接近的int型值（省去小数点后面的数向偶数值靠近）|
|**round(x,k)**|返回最接近10^-k的近似值（返回类型匹配x）|
|**sorted(iterable)**|返回一个列表，它包含的元素是以顺序排序的iterable中的元素|
|**sum(iterable)**|返回iterable中元素的和(必须是数字)|
|**type(obj)**|返回实例obj所属的类|
> **iterable**：表示可迭代类型的实例
> **sequence**：str、list、tuple
> **迭代类型**：如str、list、tuple、set、dict
##### 16. 偏函数
偏函数可以帮助我们自动传参。
```py
import functools

def index(a, b):
    return a + b

# 原来的调用方式
# ret = index(1, 2)
# print(ret)
#偏函数：自动传递参数
new_func = functools.partial(index, 1)  # “1”会被当作第一个参数传递进来
ret = new_func(2)  # “2”会被当作第二个参数传递进来
print(ret)
```
>@[toc]
##### 1. 装饰器
###### 1.1 装饰器的引入(一)
① 装饰器引入过程
```python
def func():
    pass
v = 10
v = func
print(v)
```
```python
def base():
    print('base')

def bar():
    print('bar')

bar = base
bar()
'''
base
'''
```
```python
def func():
    def inner():
        pass
    return inner
v = func()
print(v)
```
```python
def func(arg):
    def inner():
        print(arg)
    return inner
v1 = func(1)
v2 = func(2)
```
```python
def func(arg):
    def inner():
        arg()
    return inner

def f1():
    print(123)
    
v = func(f1)
v()
'''
123
'''
```
```python
def func(arg):
    def inner():
        arg()
    return inner

def f1():
    print(123)
    return 456

v = func(f1)
result = v()
print(result)
'''
123
None
'''
```
```python
def func(arg):
    def inner():
        return arg()
    return inner

def f1():
    print(123)
    return 456

v = func(f1)
result = v()
print(result)
'''
123
456
'''
```
```python
def func():
    print(123)
    
v = func
func = 456  # 修改func，但是v还是执行func函数的地址
```
###### 1.2 装饰器的引入(二)
① 引入装饰器
```python
def func(arg):
    def inner():
        return arg()
    return inner

def index():
    print(123)
    return 456

v = index()
```
```python
def func(arg):
    def inner():
        return arg()
    return inner

def index():
    print(123)
    return 456

v2 = func(index)  # v2是inner函数
index = 789
v3 = v2()
```
```python
def func(arg):
    def inner():
        return arg()
    return inner

def index():
    print(123)
    return 456

v4 = func(index)
```
```python
def func(arg):
    def inner():
        return arg()
    return inner

def index():
    print(123)
    return 456

index = func(index)
index()
```
```python
def func(arg):
    def inner():
        print('before')
        v = arg()
        print('after')
        return v
    return inner

def index():
    print(123)
    return 456

index = func(index)
index()
```
```python
def func(arg):
    def inner():
        print('before')
        v = arg()
        print('after')
        return v
    return inner
'''
def index():
    print(123)
    return 456
index = func(index)
index()
'''
# 第一步：执行func函数并将下面的函数当作参数传递，相当于func(index)
# 第二部：将func(index)的返回值重新赋值给下面的函数名，相当于index = func(index)
def index():
    print(123)
    return 456

print(index)
v = index()
print(v)
print()

@func
def index():
    print(123)
    return 456

print(index)
v = index()
print(v)
'''
<function index at 0x0000022A5490C7B8>
123
456

<function func.<locals>.inner at 0x0000022A5490C840>
before
123
after
456
'''
```
② 装饰器的目的

装饰器：在不过改变原函数内部代码的基础上，在函数执行前后自定义功能（在原函数执行之前和之后自动执行某个功能）。装饰器本质上是一个函数，而且使一个而双层函数。

③ 如何写装饰器
```python
def x(fun):  # 必须有一个参数
    def y():
        ret = fun()
        return ret
    return y
@x
def index():
    '''
    被装饰的函数
    :return: 
    '''
    pass
# 执行函数自动触发装饰器，函数返回值也能拿到
index()
v = index()
print(v)
```
④ 装饰器编写格式
```python
def 外层函数(参数):
	def 内层函数():
		return 参数()
	return 内层函数
```
⑤ 装饰器应用格式
```python
@外层函数
def 需要加装饰器的函数():
	pass
需要加装饰器的函数()
```
⑥ 为什么要加入*args和**wargs
原函数中有参数的情况下，需要在内部函数中加入*args和**wargs，可以接收任意参数，
```python
def 外层函数(参数):
	def 内层函数(*args,**kwargs):
		return 参数(*args,**kwargs)
	return 内层函数
@外层函数
def index(1,['thanlon'],{'k1':'v1','k2':'v2'}):
	pass
```
###### 1.3 装饰器需要注意的
① 统一参数
统一参数的目的是为了给原函数（加装饰器的函数）传参，没有统一参数：
```python
def x(func):
    '''
    :param func: index()
    :return:inner
    '''
    def inner(a,b):
        data = func()
        return data
    return inner

@x
def index():
    pass

index(1, 2)
```
统一参数：
```python
def x(func):
    '''
    :param func: index()
    :return:inner
    '''
    def inner(a, b):
        data = func(a, b)
        return data
    return inner

@x
def index(a, b):
    return a + b

v = index(1, 2)
print(v)
```
如果给不同参数的函数统一装饰器，如何做？
```python
def x(func):
    '''
    :param func: index()
    :return:inner
    '''

    def inner(*args, **kwargs):
        data = func(*args, **kwargs)
        return data

    return inner
    
@x
def index():
    pass

print(index())

@x
def index(a, b):
    return a + b
    
print(index(1, 2))

@x
def index(a, b, c):
    return a * b * c

print(index(1, 2, 3))
'''
None
3
6
'''
```
② 原函数执行前后执行其它操作
- 基本格式：
```python
def x(func):
    def inner(*args, **kwargs):
        print('调用原函数之前的操作')
        data = func(*args, **kwargs)  # 执行原函数并且获取返回值
        print('调用原函数之后的操作')
        return data
    return inner
@x
def index():
    return 'thanlon'
```
- 在原函数执行之前
练习1：请为以下函数编写装饰器，添加上装饰器后可以实现：执行read_ userinfo函数时，先检查文件路径是否存在，如果不存在则输入文件路径不存在，并且不再执行read_userinfo函数体中的内容，再将content变量赋值None，
```python
def read_userinfo(path):
    file_obj = open(path, mode='r', encoding='utf-8')
    data = file_obj.read()
    file_obj.close()
    return data
     
content = read_userinfo('E:\pycharmProjects\practice\log.txt')
```
为代码加装饰器：
```python
import os

def wrapper(func):
    def inner(*args, **kwargs):
        # 检查路径是否存在
        if not os.path.exists(args[0]):
            print('文件路径不存在')
            return None
        result = func(*args, **kwargs)

        return result

    return inner
@wrapper
def read_userinfo(path):
    file_obj = open(path, mode='r', encoding='utf-8')
    data = file_obj.read()
    file_obj.close()
    return data
    
content = read_userinfo('E:\pycharmProjects\practice\log.txt')
print(content)
```
- 在原函数执行之后
练习2：请为以下函数编写一个装饰器，添加装饰器后可以实现：将被执行的函数执行5次，将每次执行函数的结果按照顺序放在列表中，最终返回列表：
```python
import random

def wrapper(func):
    def inner(*args, **kwargs):
        lst = []
        for i in range(5):
            data = func(*args, **kwargs)
            lst.append(data)
        return lst
    return inner
    
@wrapper
def func():
    return random.randint(1, 4)

result = func()
print(result)
'''
[2, 3, 3, 3, 4]
'''
```
③ 装饰器的建议写法(重要)
```python
def x(func):
    def inner(*args, **kwargs):
        data = func(*args, **kwargs)
        return data

    return inner
```
###### 1.4 装饰器的应用
① 计算函数执行时间
 - 不适用装饰器：代码量大
```python
# coding:utf-8
'''
没有使用装饰器
'''
import time

def func():
    time.sleep(3)

def func2():
    time.sleep(3)

def func3():
    time.sleep(3)

start_time = time.time()
func()
end_time = time.time()
print(end_time - start_time)

start_time = time.time()
func2()
end_time = time.time()
print(end_time - start_time)

start_time = time.time()
func3()
end_time = time.time()
print(end_time - start_time)
'''
3.0121190547943115
3.0035953521728516
3.010974407196045
'''
```
② 使用装饰器：统一批量在函数之前和函数之后做操作
```python
# coding:utf-8
'''
没有使用装饰器
'''
import time

def wrapper(args):
    def inner():
        start_time = time.time()
        v = args()
        end_time = time.time()
        print(end_time - start_time)
        return v
    return inner

@wrapper
def func():
    time.sleep(3)

@wrapper
def func2():
    time.sleep(3)

@wrapper
def func3():
    time.sleep(3)

func()
func2()
func3()
```
###### 1.5 带参数的装饰器（没有普通装饰器重要）
① 带参数的装饰器应用
flask框架、django缓存、写装饰器实现被装饰的函数要执行N次。

② 带参数的装饰器示例
```python
'''
带参数的装饰器
'''
def x(name):
    print(name)
    
    def wrapper(func):
        print('wrapper')
        def inner(*args, **kwargs):
            data = func(*args, **kwargs)  # 执行原函数并获取返回值
            return data
        return inner
    return wrapper
    
'''
1. 执行x(9)，得到返回值wrapper
2. 把index函数当作参数传入wrapper函数[wrapper(index)]，并执行wrapper函数得到inner,然后index = inner
'''
@x('thanlon')  # index = x(9)(index)
def index():
    pass
# index() # 执行inner函数，也就是执行原函数index
# v = index() # 获取index函数的返回值
'''
thanlon
wrapper
'''
```
③ 带参数的装饰器练习（面试题用笔写）
练习1：写一个带参数的装饰器，实现参数是多少被装饰的函数就要执行多少次，把每次执行的结果添加到列表中，最终返回列表。
```python
'''
练习：写一个带参数的装饰器，实现参数是多少被装饰的函数就要执行多少次，把每次执行的结果添加到列表中，最终返回列表。
'''
def x(counter):
    def wrapper(func):
        def inner(*args, **kwargs):
            lst = []
            for i in range(counter):
                data = func(*args, **kwargs)
                lst.append(data)
            return lst

        return inner

    return wrapper

@x(6)
def index():
    return 666

v = index()
print(v)
'''
[666, 666, 666, 666, 666, 666]
'''
```
练习2：写一个带参数的装饰器，实现参数是多少被装饰的函数就要执行多少次，并返回最后依次执行的结果。(面试题)
```python
'''
练习：写一个带参数的装饰器，实现参数是多少被装饰的函数就要执行多少次，并返回最后依次执行的结果。
'''
def x(counter):
    def wrapper(func):
        def inner(*args, **kwargs):
            for i in range(counter):
                data = func(*args, **kwargs)
            return data

        return inner

    return wrapper
    
@x(6)
def index():
    return 666

v = index()
print(v)
'''
666
'''
```
##### 2. 推导式
###### 2.1 列表推导式
① 列表推导式的作用
方便生成一个列表

② 基本格式

<kbd>v = [i for in 可迭代对象]</kbd>

<kbd>v = [i for in 可迭代对象 if 条件]</kbd>（条件为True才进行append）

③ 列表推导式例子

<kbd>v = [i for i in 'thanlon']</kbd>
```python
# coding:utf-8
v = [i for i in 'thanlon']
print(v)
'''
['t', 'h', 'a', 'n', 'l', 'o', 'n']
'''
```
<kbd>v = [i+100 for i in range(10)]</kbd>
```python
# coding:utf-8
v = [i+100 for i in range(10)]
print(v)
'''
[100, 101, 102, 103, 104, 105, 106, 107, 108, 109]
'''
```
<kbd>v = ['thanlon' if i > 5 else 'kiku' for i in range(10)]</kbd>
```python
# coding:utf-8
v = ['thanlon' if i > 5 else 'kiku' for i in range(10)]
print(v)
'''
['kiku', 'kiku', 'kiku', 'kiku', 'kiku', 'kiku', 'thanlon', 'thanlon', 'thanlon', 'thanlon']
'''
```
```python
# coding:utf-8
def func():
    return 1

v = [func for i in range(10)]
print(v)
'''
[<function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>, <function func at 0x000001976013C1E0>]
'''
```
```python
# coding:utf-8
v = [lambda: 100 for i in range(10)]
ret = v[3]()
print(ret)
'''
100
'''
```
```python
# coding:utf-8
def func():
    return i

v = [func for i in range(10)]
ret = v[4]()
print(ret)
'''
9
'''
```
```python
# coding:utf-8
v = [lambda :i for i in range(10)]
ret = v[4]()
print(ret)
'''
9
'''
```
④ 列表推导式筛选
```python
# coding:utf-8
v = [i for i in range(10) if i > 5]
print(v)
'''
[6, 7, 8, 9]
'''
```
⑤ 面试题一（新浪微博面试题）
```python
# coding:utf-8
'''
新浪面试题：v是什么？v[0](2)的结果是什么？
'''
v = [lambda x: x + i for i in range(10)]  # 新浪面试题
# v是什么？一个包含对象的列表
print(v)
'''
[<function <listcomp>.<lambda> at 0x00000217B0BCC7B8>, <function <listcomp>.<lambda> at 0x00000217B0BCC8C8>, <function <listcomp>.<lambda> at 0x00000217B0BCC840>, <function <listcomp>.<lambda> at 0x00000217B0BCC950>, <function <listcomp>.<lambda> at 0x00000217B0BCC9D8>, <function <listcomp>.<lambda> at 0x00000217B0BCCA60>, <function <listcomp>.<lambda> at 0x00000217B0BCCAE8>, <function <listcomp>.<lambda> at 0x00000217B0BCCB70>, <function <listcomp>.<lambda> at 0x00000217B0BCCBF8>, <function <listcomp>.<lambda> at 0x00000217B0BCCC80>]
'''
print(v[0](2))  # 9+11
```
⑥ 面试题二
```python
# coding:utf-8
def num():
    return [lambda x: i * x for i in range(4)]

print(num())  # [函数,函数,函数,函数]
print([m(2) for m in num()])
'''
[<function num.<locals>.<listcomp>.<lambda> at 0x00000274ECEFC8C8>, <function num.<locals>.<listcomp>.<lambda> at 0x00000274ECEFC840>, <function num.<locals>.<listcomp>.<lambda> at 0x00000274ECEFC950>, <function num.<locals>.<listcomp>.<lambda> at 0x00000274ECEFC9D8>]
[6, 6, 6, 6]
'''
```
###### 2.2 集合推导式
集合推导式与列表推导式相似，将 [ ] 号换成 { }。

<kbd>v = { i for i in 'thanlon'}
print(v)</kbd>
###### 2.3 字典推导式
<kbd>v = {'k' + str(i): i for i in range(10)}
print(v)
</kbd>
###### 2.4 生成器推导式(面试题)
对于列表：<kbd>v = [i for i in range(10)]  # 列表推导式，立即循环创建所有元素</kbd>，等价于：
```python
# v = [i for i in range(10)]  # 列表推导式，立即循环创建所有元素
def func():
    result = []
    for i in range(10):
        result.append(i)
    return result
v = func()
```
对于生成器：
```python
v = (i for i in range(10))
print(v)
'''
<generator object <genexpr> at 0x0000027472A85570>
'''
```
<kbd>v = (i for i in range(10)) # 生成器推导式，创建一个生成器，循环生成器一个一个创建元素</kbd>，等价于：
```python
def func():
    for i in range(10):
        yield i
v = func()
print(v)
'''
<generator object <genexpr> at 0x0000027472A85570>
'''
for item in v:
	print(item)
```
**面试题：** 请比较[i for i in range(10)]和(i for i in range(10))的区别？

<kbd>[i for i in range(10)]是列表推导式，内部生成列表；(i for i in range(10))是生成器推导式，一个生成生成器。</kbd>

① 示例1
```python
# v = [lambda: i for i in range(10)]
# for item in v:
#     print(item())
'''
等价于下面的
'''
def func():
    result = []
    for i in range(10):
        def f():
            return i
        result.append(f)
    return result

v = func()  # for循环执行完毕，但f函数没有执行，f执行时，自己没有i向上一级找i，i = 9
for item in v:
    print(item())
```
② 示例2
```python
# v = (lambda: i for i in range(10))
# for item in v:
#     print(item())
'''
等价于下面的
'''
def func():
    for i in range(10):
        def f():
            return i
        yield f

v = func()  # 生成器，内部代码没有执行
for item in v:  # 生成器执行循环的时候才执行
    print(item())
'''0
1
2
3
4
5
6
7
8
9
'''
```
###### 2.5 推导式总结
 列表推导式常用一些，注意字典推导式写法。
 >@[toc]
##### 1. 迭代器
我们以后不会自己去写迭代器，只要学会使用迭代器就可以了。
###### 1.1 迭代器的作用
如果有这样的需求，展示列表中的所有数据。实现方法有：① while+索引+计数器；② 迭代器

`迭代器`：对可迭代对象（序列类型，如str、list、tuple、dict、set）中的元素进行逐一获取。表象：具有__next__方法且每次调用都获取可迭代对象中的元素（从前到后一个一个获取）。
###### 1.2 迭代器的使用
列表转换成迭代器方法一：`v = [1, 2, 3, 4, 5, 6]`，`val = iter(v)`[使用内置函数iter]
```py
# coding:utf-8
v = iter([1, 2, 3, 4, 5, 6])
print(v, type(v))
'''
<list_iterator object at 0x000001EF6A0E95F8> <class 'list_iterator'>
'''
```
列表转换成迭代器方法二：`v = [1, 2, 3, 4, 5, 6]`，`val = v.__ iter__ ()`[使用__ iter__ 方法]
```py
# coding:utf-8
v = [1, 2, 3, 4, 5, 6]
# val = iter(v)#内部会调用__iter__方法
v2 = v.__iter__()
while True:
    val = v2.__next__()
    print(val)
```
迭代器获取每个值：反复调用`val.__ next __()`[val是迭代器对象]
```py
# coding:utf-8
v = iter([1, 2, 3, 4, 5, 6])
val1 = v.__next__()
val2 = v.__next__()
val3 = v.__next__()
val4 = v.__next__()
val5 = v.__next__()
val6 = v.__next__()
print(val1, val2, val3, val4, val5, val6)
'''
1 2 3 4 5 6
'''
```
```py
# coding:utf-8
v = iter([1, 2, 3, 4, 5, 6])
while True:
    try:
        val = v.__next__()
        print(val)
    except Exception as e:
        break
```
直到报StopIteration错误
```python
# coding:utf-8
v = iter([1, 2, 3, 4, 5, 6])
while True:
    val = v.__next__()
    print(val)
'''
1
2
3
4
5
6
StopIteration
'''
```
###### 1.3 for循环与迭代器
for循环的内部使用的是迭代器：
```python
# coding:utf-8
v = ['thanlon', 'kiku']
'''
1. for循环内部会将v1转换成迭代器
2. 内部反复执行“迭代器.__next__()”方法,一个个取值
3. 取完值不报错
'''
for item in v:
    print(item)
'''
thanlon
kiku
'''
```
###### 1.4 可迭代对象
可以被for循环且对象中具有__iter__()方法，还要返回一个迭代器（或生成器），
```python
v = [1, 2, 3]
result = v.__iter__()  # 有__iter__方法，且返回迭代器对象（result），所以v是迭代器对象
print(result)  # result = <list_iterator object at 0x000001E11CB795C0>
```
###### 1.5 可迭代对象与迭代器之间关系
可迭代对象可以转换成迭代器，迭代器可以转换为可迭代对象。
###### 1.6 写一个迭代器
```py
class Iterator(object):
    def __init__(self,data=[]):
        if data:
            self.data = data
        else:
            self.data = []
        self.num = 0
    def __iter__(self):
        return self
    def __next__(self):
        if self.num < len(self.data):
            ret = self.data[self.num]
            self.num += 1
            return ret
        else:
            raise StopIteration
iterator = Iterator([1,2,3,4,5])
print(iterator.__iter__())
print(iterator.__next__())
print(iterator.__next__())
print(iterator.__next__())
print(iterator.__next__())
print(iterator.__next__())
# for i in iterator:
#    print(i)
```
```js
<__main__.Iterator object at 0x7fba70d8e610>
1
2
3
4
5
```
##### 2. 生成器
###### 2.1 生成器函数
函数：
```python
def func():
    return 'thanlon'
func()
```
生成器函数（函数内部是否包含yield来判断是否是生成器函数）：
```python
# 生成器函数（内部是否包含yield）
def func():
    print('f1')
    yield 1
    print('f2')
    print('f2')
    yield 2
    print('f3')
    print('f3')
    print('f3')
    yield 3
    print('f4')
    print('f4')
    print('f4')
    print('f4')
    print('f4')
    
# 函数内部代码不会被执行，返回一个生成器对象
v = func()
print(v, type(v))
'''
<generator object func at 0x0000021BC91F5570> <class 'generator'>
'''
```
生成器是可以被for循环的，一旦开始循环内部代码就会开始执行：
```python
# 生成器函数（内部是否包含yield）
def func():
    print('f1')
    yield 1
    print('f2')
    print('f2')
    yield 2
    print('f3')
    print('f3')
    print('f3')
    yield 3
    print('f4')
    print('f4')
    print('f4')
    print('f4')
    print('f4')

v = func()
for item in v:
    print(item)
'''
f1
1
f2
f2
2
f3
f3
f3
3
f4
f4
f4
f4
f4
'''
```
###### 2.2 yield from
yield from是从当前生成器跳到另一个生成器。
```python
# coding:utf-8
def func():
    yield 3
    yield 4

def func2():
    yield 1
    yield 2
    yield from func()
    yield 5

result = func2()
for item in result:
    print(item)
```
```python
# coding:utf-8
def func():
    return 3

def func2():
    yield 1
    yield 2
    yield from func()
    yield 5

result = func2()
for item in result:
    print(item)
'''
TypeError: 'int' object is not iterable
'''
```
```python
# coding:utf-8
# 使用可迭代的列表类型
def func():
    return [3, 4]

def func2():
    yield 1
    yield 2
    yield func()
    yield 5

result = func2()
for item in result:
    print(item)
'''
1
2
[3, 4]
5
'''
```
```python
# coding:utf-8
def func():
    return [3, 4]

def func2():
    yield 1
    yield 2
    # yield func()  # 把[3, 4]当作整体拿过来
    yield from func()  # 把[3,4]拆开拿过来
    yield 5

result = func2()
for item in result:
    print(item)
'''
1
2
3
4
5
'''
```
###### 2.3 生成器例子
```python
# coding:utf-8
def func():
    return 1
    if 1 != 1:
        yield 2
        yield 3

v = func()
print(v, type(v))
'''
<generator object func at 0x000001D3974F5570> <class 'generator'>
'''
```
```python
# coding:utf-8
def func():
    while True:
        yield 1

val = func()
print(val)  # <generator object func at 0x000002CC842C5570>
for item in val:
    print(item)
```
```python
# coding:utf-8
def func():
    count = 1
    while True:
        yield count
        count += 1

val = func()
print(val)
for item in val:
    print(item)
```
```python
# coding:utf-8
def func():
    return 1
    yield 2
    yield 3

val = func()
for item in val:
    print(item)  # 由于return的作用，无内容
```
```python
# coding:utf-8
def func():
    yield 2
    return 111
    yield 3

val = func()
for item in val:
    print(item)
'''
2
'''
```
```python
# coding:utf-8
def func():
    count = 1
    while True:
        yield count
        count += 1
        if count == 101:
            return
           
val = func()
for item in val:
    print(item)
'''
打印1~100
'''
```
###### 2.4 生成器总结
函数中如果存在yield（注意与return无关），那么这个函数就是一个生成器函数。调用一个生成器函数会返回一个生成器对象，生成器只有被for循环时，生成器函数内部的代码才会被执行，生成器每次循环都会获取yield返回的值。
###### 2.5 生成器应用示例
示例1：读取文件的案例，分批读取文件，将文件的内容返回给调用者
```python
# coding:utf-8
def func():
    cursor = 0
    while True:
        f = open('log.txt', 'r', encoding='utf-8')
        f.seek(cursor)
        data_list = []
        for i in range(5):  # 每次读5条
            line = f.readline()
            if not line:
                return
            data_list.append(line)
        cursor = f.tell()  # 获取当前游标位置
        f.close()
        for row in data_list:
            yield row

for item in func():
    print(item)
```
示例二：Redis源码：
安装第三方模块Redis：`pip install redis`
```python
import redis

conn = redis.Redis(host='……')
# scan_iter()是一个生成器函数
conn.scan_iter()
```
```python
def scan_iter(self, match=None, count=None):
    """
    Make an iterator using the SCAN command so that the client doesn't
    need to remember the cursor position.

    ``match`` allows for filtering the keys by pattern

    ``count`` allows for hint the minimum number of returns
    """
    cursor = '0'
    while cursor != 0:
        # 每次取100条数据
        # cursor：取完之后的游标位置
        # data：本次取出来的100条数据
        cursor, data = self.scan(cursor=cursor, match=match, count=count)
        for item in data:
            yield item
```
###### 2.6 生成器补充
生成器的两个作用：
- 生成数据
- 迭代

生成器是特殊的迭代器，生成器有__next__方法：
```python
# coding:utf-8
def func():
    yield 1
    yield 2
    yield 3

v = func()  # v是生成器（对象）
# print(v, type(v))  # <generator object func at 0x0000023986405570> <class 'generator'>
# print(dir(v))  # 查看生成器v中都有哪些方法，dir(v)返回列表
for i in dir(v):
    print(i)
'''
__class__
__del__
__delattr__
__dir__
__doc__
__eq__
__format__
__ge__
__getattribute__
__gt__
__hash__
__init__
__init_subclass__
__iter__
__le__
__lt__
__name__
__ne__
__new__
__next__
__qualname__
__reduce__
__reduce_ex__
__repr__
__setattr__
__sizeof__
__str__
__subclasshook__
close
gi_code
gi_frame
gi_running
gi_yieldfrom
send
throw
'''
```
且每次调用都获取生成器对象中的元素：
```python
# coding:utf-8
def func():
    yield 1
    yield 2
    yield 3

v = func()  # v是生成器（对象）,也是特殊的迭代器对象
result = v.__next__()
print(result)
result = v.__next__()
print(result)
result = v.__next__()
print(result)
'''
1
2
3
'''
```
生成器是特殊的可迭代对象：生成器中有__iter__方法
```python
# coding:utf-8
'''
把v当做可迭代对象
'''
def func():
    yield 1
    yield 2
    yield 3

v = func()
result = v.__iter__()
print(result)
'''<generator object func at 0x00000237F7135570>'''
```
如果一个对象有__iter__方法且返回一个迭代器称这个对象是可迭代对象。如果一个对象，它有__iter__方法，它返回一个生成器，它也是可迭代对象。
>@[toc]
##### 1. 文件操作
###### 1.1 文件操作基础知识
- 文件以什么编码写的，打开的时候就要以什么编码打开，否则会乱码。例如，使用utf-8编码写的文件，就不能以gbk编码方式打开。因为在utf-8中一个中文字符占用3位，而在gbk中占2位，如果以gbk方式打开，就会出现乱码。

- 打开utf-8编码存储的文件后，读取文件时把二进制0101…拿到内存中，在内存中系统自动转换成unicode编码。

- 如果要想修改unicode编码的文件，需要以utf-8格式打开
###### 1.2 文件打开模式
- r：只读
- w：只写，会先清空文件（一般w用于新建文件）
- a：只追加
- r+：
读：默认从0光标开始读，也可通过seek调整光标的位置
写：从光标所在的位置写，也可以通过seek调整光标的位置
- w+：
读：默认光标在写入的最后或0，也可通过seek调整光标的位置
写：先清空文件再写
- a+：
读：默认光标最后，读可通过移动光标，需要通过seek调整光标位置
写：写的时候光标自动移动到最后，方便追加内容
- rb：二进制方式读，无需设置编码
- wb：二进制方式写，无需设置编码
- ab：二进制方式追加，无需设置编码
注意：这六种模式中使用最多的就是r和w。
###### 1.3 文件操作
- 文件操作格式
```py
# coding:utf-8
# 打开文件
f = open('到打开文件的路径', mode='r/w/a/r+/w+/a+……', encoding='文件原来写入时的编码')
# 操作
data = f.read()  # 读取文件的所有内容到内存
f.write('要写入文件的内容!')
# 关闭文件
f.close()
```
- 文件读操作
```py
'''
读取文件所有内容到内存
'''
# coding:utf-8
fo = open('log.txt', mode='r', encoding='utf-8')
data = fo.read()
fo.close()
```
```py
# coding:utf-8
'''
从当前光标所在位置向后读取文件两个字符
'''
fo = open('log.txt', mode='r', encoding='utf-8')
data = fo.read(2)
print(data)
fo.close()
```
```py
# coding:utf-8
'''
读取文件的所有内容到内存，并按照文件内容的每一行分割到列表中
'''
fo = open('log.txt', mode='r', encoding='utf-8')
# data = fo.readline()  # 只读第一行
data_list = fo.readlines()  # 读取文件的所有内容到内存，并按照每一行进行分割到列表中
print(data_list)
fo.close()
'''
['奈何\n', '奈何']
'''
```
```py
# coding:utf-8
'''
读取一个特别大的文件，需要使用一行一行的读入内存
'''
fo = open('log.txt', mode='r', encoding='utf-8')
for line in fo:
    print([line])
    line = line.strip()
    print(line)
fo.close()
'''
['奈何\n']
奈何
['奈何']
奈何
'''
```
内部操作：读取硬盘文件中的二进制编码的内容，将二进制按照encoding指定的utf-8编码，转换成字符串：
```python
# coding:utf-8
f = open('test.txt', mode='r', encoding='utf-8')
# 内部操作：读取硬盘文件中的二进制编码的内容，将二进制按照encoding指定的utf-8编码，转换成字符串
data = f.read()
f.close()
```
直接读取到的是二进制数据：
```python
# coding:utf-8
f = open('test.txt', mode='rb')
# 直接读取到的是二进制数据
data = f.read()
print(data)
f.close()
'''
b'\xe5\xa5\x88\xe4\xbd\x95\r\n\xe5\xa5\x88\xe4\xbd\x95'
'''
```
- 文件写操作
```python
# coding:utf-8
''''
写操作
'''
fo = open('log.txt', mode='w', encoding='utf-8')
fo.write('奈何\n')
fo.write('奈何')
```
文件打开后，修改文件操作不是直接修改。先把要修改的文件读到内存，在内存中做修改，保存之后向硬盘重新写一份。

示例1：文字的写入
```python
# coding:utf-8
''''
示例1：一般用于文字的写入
'''
f = open('test.txt', mode='w', encoding='utf-8')
'''
1. 将“你好”根据encoding指定的编码(utf-8)转换成二进制->“你好”占用6个字节，48位二进制数字
2. 将二进制写入到文件中
'''
f.write('你好')  # w打开文件，write传入的是字符串
f.close()
```
示例2：图片、音频、视频、未知编码的写入
```python
# coding:utf-8
''''
示例1：一般用于图片、音频、视频、未知编码的写入
'''
f = open('test.txt', mode='wb')
# 1.把要写入的字符串转换成二进制
data = '你好'
content = data.encode('utf-8')  # 将字符串按照utf-8编码转换成二进制
# 2.在将二进制写入文件中
f.write(content)  # wb打开文件，write传入的是二进制
f.close()
```
###### 1.4 文件操作例题
练习1：将列表中的元素用下划线“_”连接，并写入文件中
```python
# coding:utf-8
'''
练习1：将列表中的元素用下划线“_”连接，并写入文件中
'''
user = ['thanlon', 'kuki']
data = '_'.join(user)
fo = open('user.txt', mode='w', encoding='utf-8')
fo.write(data)
fo.close()
```
练习2：将列表中嵌套的字典的值通过下划线“_”连接，并写入到文件中
```python
# coding:utf-8
'''
练习2：将列表中嵌套的字典的值通过下划线“_”连接，并写入到文件中
'''
user = [
    {'name': 'Thanlon', 'age': 23},
    {'name': 'Kiku', 'age': 25}
]
fo = open('user.txt', 'w', encoding='utf-8')
for item in user:
    line = '%s_%s\n' % (item['name'], item['age'])
    fo.write(line)
fo.close()
```
练习3：将练习2中文件内容读取出来，并添加到一个列表中
```python
# coding:utf-8
'''
练习3：将练习2中文件内容读取出来，并添加到一个列表中
'''
fo = open('user.txt', mode='r', encoding='utf-8')
content = fo.read()
# print([content])  # ['Thanlon_23\nKiku_25\n']
content = content.strip()  # 去掉量表的换行符
# print([content])
data = content.split('\n')
print(data)  # ['Thanlon_23', 'Kiku_25']
fo.close()
```
```python
# coding:utf-8
'''
练习3：将练习2中文件内容读取出来，并添加到一个列表中
'''
usr_list = []
fo = open('user.txt', mode='r', encoding='utf-8')
for line in fo:
    line = line.strip()
    usr_list.append(line)
fo.close()
print(usr_list)
```
###### 1.5 with as用法
有些任务，可能事先设置，任务结束后做清理工作，如下面一段程序：
```py
f = open('tmp.txt')
data = f.read()
print(data)
```
很明显忘记关闭文件句柄，并且对文件读取可能发生的异常在程序中没有做任何处理。下面使用异常处理，
```py
f = open('tmp.txt')
try:
    data = f.read()
    print(data)
except BaseException as msg:
    print(msg)
finally:
    f.close()
```
虽然这段代码运行良好，但太过冗长，这里使用 with as 来写：
```py
with open('tmp.txt') as f:
    data = f.read()
    print(data)
```
##### 2. 深浅拷贝
遇到不可变类型，深浅拷贝都不会拷贝一份（重新开辟内存），用的都会是原来的那份。
遇到可变类型，浅拷贝只拷贝第一层，里面的值都来自原来的那份。而深拷贝拷贝嵌套层次中的所有可变类型，里面的值来自原来的那份。

###### 2.1 不可变类型的拷贝
对于不可变类型，如数字、字符串、布尔类型、元组（无嵌套或嵌套不可变类型），不论浅拷贝还是深拷贝，拷贝的值都会是原来的那份（其实不应该是原来的那份，是由于python中小数据池的缘故）。如果被拷贝的值被修改，也就是原值指向其它地址，但拷贝的值不变，还是指向那个地址。
```python
# coding:utf-8
v1 = 123456 # 数字
# v1 = 'thanlon' # 字符串
# v1 = True # 布尔
# v1 = (1, 2, 3) # 无嵌套
# v1 = (1, 2, 3,(4,5,6)) # 嵌套不可变类型
import copy

# 浅拷贝
v2 = copy.copy(v1)
print(id(v1), id(v2))
# 深拷贝
v2 = copy.deepcopy(v1)
print(id(v1), id(v2))
'''
2765969462752 2765969462752
2765969462752 2765969462752
'''
```
###### 2.2 可变类型的拷贝
对于可变类型，如list、set和dict，如果只有一层时，也就是里面没有嵌套，如[1,2,3]、{1，2，3}、{'name':'thanlon'}，浅拷贝与深拷贝都会将外层的列表（集合/字典）拷贝一份，里面的值是通过指向被拷贝值的地址。
```python
import copy

v1 = [1, 2, 3]
v2 = copy.copy(v1)
print(id(v1), id(v2))

v3 = copy.deepcopy(v1)
print(id(v1), id(v3))
'''
2983039081288 2983039159496
2983039081288 2983039299464
'''
```
对于可变类型中有嵌套时，如果嵌套的是不可变类型，浅拷贝和深拷贝都会将外层的列（集合/字典）拷贝一份，里面的值通过指向被拷贝值的地址。但是，如果嵌套的是可变类型，如列表里面嵌套列表。浅拷贝只拷贝一层，里面不管可变不可变，均不拷贝，通过地址指向。深拷贝会拷贝列表外层，不可变类型不会拷贝。但是会拷贝一份嵌套的列表（可变类型），列表里面的值指向被拷贝嵌套的列表的值。
```python
# coding:utf-8
v1 = [1, 2, 3, [4, 5, 6]]
import copy

# 浅拷贝:外层的列表拷贝一份，里面的所有值不拷贝，都指向被拷贝同一地址
v2 = copy.copy(v1)
print(id(v1), id(v2))
print(id(v1[3]), id(v2[3]), '\n')
# 深拷贝:外层的列表拷贝一份，里面的值是不可变类型指向，是可变类型的拷贝可变类型外层，拷贝后的可变类型里的值指向原可变类型里的值
v2 = copy.deepcopy(v1)
print(id(v1), id(v2))
print(id(v1[3]), id(v2[3]))
'''
2074813293256 2074815389000
2074813293192 2074813293192 

2074813293256 2074815516552
2074813293192 2074815387784
'''
```
特殊情况：如果元组中嵌套有可变类型的数据，浅拷贝不拷贝里面的值，用原来那份。但是深拷贝会把这个元组重新拷贝一份。
```python
import copy

v1 = (1, 2, 3, [4, 5, 6])
v2 = copy.copy(v1)
print(id(v1[3]), id(v2[3]))

v3 = copy.deepcopy(v1)
print(id(v1[3]), id(v3[3]))
'''
1659756292872 1659756292872
1659756292872 1659756367176
'''
```
>@[toc]
##### 1. 面向过程和面向函数编程
###### 1.1 面向过程编程
```python
# coding:utf-8
'''
面向过程实现：计算字符串与列表中元素的个数
'''
count_str = 0
str = 'Thanlon'
for i in str:
    count_str += 1

count_list = 0
lst = ['I', 'am', 'Thanlon']
for j in lst:
    count_list += 1
print(count_str, count_list)
'''
7 3
'''
```
② 面向函数编程
```python
# coding:utf-8
'''
面向函数实现计算字符串与列表中元素的个数
'''
def count(param):
    count = 0
    for i in param:
        count += 1
    return count

str = 'Thanlon'
lst = ['I', 'am', 'Thanlon']
print(count(str), count(lst))
'''
7 3
'''
```
###### 1.2 面向对象中的类和对象
① 什么是类
类是具有相同属性和功能的一类事物。

② 什么是对象 
对象是类的具体表现形式。
##### 2. 面向函数编程与面向对象编程
###### 2.1 面向函数
```python
# coding:utf-8
'''
 用户认证相关
'''
def login():
    pass
def regisgter():
    pass
# 统计相关
def count(param):
    count = 0
    for i in param:
        count += 1
    return count
```
###### 2.2 面向对象
```python
# coding:utf-8
'''
 用户认证相关
'''
class Foo(object):
    def login(self):
        pass
    def regisgter(self):
        pass
# 统计相关
class Foo2(object):
    def count(self, param):
        count = 0
        for i in param:
            count += 1
        return count
```
对比两种方式，不难发现：面向对象把相似的功能函数进行了划分，代码就显得更加清晰明了。

###### 2.3 面向对象编程的优点
面向对象中的类就是一个公共模板，对象就是从具体的模板实例化出来的；面向对象编程是一类相似功能函数的集合，使代码更清晰化，更合理化；
##### 3. 何编写面向对象程序
###### 3.1 面向对象基本格式
```python
# 定义类
class 类名:  # 首字母大写
    def 方法名(self, name):
        print(name)
        return name
    def 方法名(self, name):
        print(name)
        return name
        ……
# 调用类中方法
# 1.创建该类的对象
obj = 类名()
# 2.通过对象调用方法
result = obj.方法名('Thanlon')
print(result)
```
###### 3.2 面向对象的应用场景(什么时候使用面向对象)
调用很多函数，需要给函数进行归类和划分。对于函数特别少、功能特别少，用函数就能实现，不用面向对象。

###### 3.3 对象的作用
存储一些值，以后方便自己使用。
##### 4. 封装
###### 4.1 封装的优点
把函数封装在类中，把数据封装到对象，方便使用。

###### 4.2 封装的形式
一种是将函数封装在类中，一种是把一些值封装到对象中

###### 4.3 封装示例
```python
class Person:
    def show(self):
        tmp = "My name is %s，my age is %s,my gender is %s" % (self.name, self.age, self.gender)
        print(tmp)
p1 = Person()
p1.name = 'Thanlon'
p1.gender = '男'
p1.age = 23
p1.show()
p2 = Person()
p2.name = 'KiKu'
p2.gender = '女'
p2.age = 25
p2.show()
```
对封装示例改进
```python
class Person:
    def __init__(self):# 初始化方法，说构造方法是不准确的
        self.name = 'Thanlon'
        self.gender = '男'
        self.age = 23

    def show(self):
        tmp = "My name is %s，my age is %s,my gender is %s" % (self.name, self.age, self.gender)
        print(tmp)

# 类()实例化对象，自动执行此类的__init__方法
p1 = Person()
print(p1.name, p1.gender, p1.age)
p1.show()
p2 = Person()
p2.show()
```
为了能让不同对象封装不一样的值，需要对封装示例进一步改进：
```python
class Person:
    def __init__(self, name, gender, age):  # init方法是可以加参数的
        self.name = name
        self.gender = gender
        self.age = age

    def show(self):
        tmp = "My name is %s，my age is %s,my gender is %s" % (self.name, self.age, self.gender)
        print(tmp)

# 类()实例化对象，自动执行此类的__init__方法
p1 = Person('Thanlon', '男', '23')
p1.show()
p2 = Person('KiKu', '女', '25')
```
##### 5. 继承
###### 5.1 什么是继承
继承是面向对象软件技术当中的一个概念。如果一个类别A“继承”另一个类别B，就把这个A称为B的“子类别”，而把B称为“A的父类别”也可以称“B是A的超类”。继承可以使得子类别具有父类别的各种属性和方法，而不需要再次编写相同的代码。在令子类别继承父类别的同时，可以重新定义某些属性，并重写某些方法，即覆盖父类别的原有属性和方法，使其获得与父类别不同的功能。一般静态的面向对象编程语言，继承属于静态的，意即在子类别的行为在编译期就已经决定，无法在执行期扩充。

###### 5.2 为什么要使用继承
实现代码的复用，增加了类的耦合性，使得代码更加规范化、合理化。

###### 5.3 单继承
子类可以只继承一个(父)类。子类的实例化对象调用类中的变量或方法的顺序是：先调用子类中的再调用父类中的。
```python
class Superbase:
    def fun01(self):
        pass
class Base(Superbase):  # 父类/基类
    def fun02(self):
        pass
class Foo(Base):  # 字类/派生类
    def func03(self):
        pass
foo = Foo()
foo.func03()
foo.fun02()
foo.fun01()
```
###### 5.4 多继承
子类可以同时继承多个(父)类。如果继承的这些类中有相同的方法或变量，当子类不存在此方法或变量，而需要调用父类中的这个方法或变量时，最先继承的类中的方法或变量会先被调用。如class Foo(Base01, Base02)，先调用类Base01中的方法。
```python
class Base01():  # 父类/基类
    def show(self):
        print('Base01.show()')
class Base02():  # 父类/基类
    def show(self):
        print('Base-2.show()')
class Foo(Base01, Base02):  # 字类/派生类
    def func03(self):
        pass
foo = Foo()
foo.show() # Base01.show()
```
###### 5.5 继承练习题
① 继承练习1
注意：self是哪个类的对象，就从哪个类开始找（自己如果没有就去找父类）
```python
class Base:
    def f1(self):
        print('Base.f1')
    def f3(self):
        self.f1()
        print('Base.f3')
class Foo(Base):
    def f1(self):
        print('Foo.f1')
    def f2(self):
        print('Foo.f2')
        self.f3()
obj = Foo()
obj.f2()
# Foo.f2
# Foo.f1
# Base.f3
obj2 = Base()
obj2.f3()
# Base.f1
# Base.f3
```
② 继承练习2
注意：继承的父类的先后顺序
```python
class Base01:
    def f1(self):
        print('Base01.f1')
class Base02:
    def f1(self):
        print('Base02.f2')
    def f3(self):
        print('Base02.f3')
        self.f1()
class Foo(Base01, Base02):
    def f0(self):
        print('Foo.f0')
        self.f3()
obj = Foo()
obj.f0()
# Foo.f0
# Base02.f3
# Base01.f1
```
##### 6. 多态
python中多态无处不在，同一个变量可以有多种状态，同一个对象也可以有多种状态。在java和CSharp语言中，定义变量和给变量赋值就必须定义数据类型，而类似于python这种弱定义类的语言，变量可以是任意形态。比如，创建一个变量tmp，给tmp赋值10，那么tmp就是整型的。再将tmp赋值'thanlon'，那么它就是字符串类型。这就体现出多态性，同一个变量可以是多种形态。
##### 7. 成员变量
###### 7.1 成员变量分类
类变量与实例变量
###### 7.2 类变量
类变量，也称为静态字段。类变量是在类中定义的变量，如示例程序中的sex = 'man'。类变量（静态字段）的访问，可以使用类访问，也可以使用对象访问。单优先使用类访问，实在不方便，才使用对象访问。
###### 7.3 实例变量
实例变量，也称为字段。实例变量是在 _ _ init _ _方法中定义的变量，如示例程序中的 self.name = name，实例变量（字段）访问时使用是对象访问。

###### 7.4 成员变量示例程序
```python
class Foo:
    # 定义类变量（静态字段）
    sex = 'man'
    def __init__(self, name):
        # 定义实例变量(字段)
        self.name = name  # 实例变量/字段
# 对象obj1和对象obj2各自维护自己的实例变量，修改obj1的实例变量，不影响obj2的实例变量值
# obj1 = Foo('Thanlon')  # Foo的对象/Foo类的实例
# obj2 = Foo('Kiku')
# obj1.name = 'Thanlon Smith'
# print(obj1.name)  # Thanlon Smith
# print(obj2.name)  #Kiku

# 可以使用对象调用类变量,但是不能修改类变量的值
obj1 = Foo('Thanlon')
obj2 = Foo('Kiku')
print(obj1.sex)  # man
print(obj2.sex)  # man
obj1.sex = 'woman'  # obj1定义了自己的变量sex，obj1.sex访问sex时，先访问自己中的变量sex
print(obj1.sex)  # 'woman''
print(obj2.sex)  # man
print(Foo.sex)  # man
```
##### 8. 私有变量
###### 8.1 私有变量分类
私有类变量、私有实例变量

###### 8.2 私有类变量	
内部可以访问私有类变量（self.私有变量名、类名.私有变量名），外部不可以访问私有变量，但可以借助类中的方法间接访问私有变量。
```python
class Foo:
    __age = 12

    def f1(self):
        # 内部调用
        print(self.__age)
        print(Foo.__age)  # 推荐
obj = Foo()
# 外部无法调用私有类变量
# print(Foo.__age)
# print(obj.__age)
# 外部通过类中的方法间接访问私有类变量
obj.f1()
```
其实外部还可以强制访问私有类变量：
```python
class Foo:
    __age = 12
    
obj = Foo()
# 外部强制访问
print(obj._Foo__age)
```
###### 8.3 私有实例变量
内部可以访问私有实例变量，外部不可以访问私有变量，但可以借助类中的方法间接访问私有变量。
```python
class Foo:
    def __init__(self, name):
        self.__name = name
    def f1(self):
        # 内部可以访问__name
        print(self.__name)
obj = Foo('Thanlon')
# obj.__name  # 访问失败
obj.f1()  # 间接可以访问
```
##### 9. 成员方法
###### 9.1 实例方法
需要使用对象中封装的变量，如name，就可以使用实例方法
```python
class Foo:
    def __init__(self, name):
        self.name = name
    # 实例化方法（一般方法）
    def f1(self):
        print(self.name)
obj = Foo('Thanlon')
obj.f1()
```
静态方法调用时，可以使用类.方法名，也可以使用对象.方法名，但推荐类来调用（调用字段的时候也是）。

① 静态方法
如果方法无需使用对象中封装的值，那么就可以使用静态方法。写静态方法时，方法上方需要写@staticmethod，方法中参数可有可无，参数中不可以用self会出错，解释器执行时也不会将self自动传入参数列表。
```python
class Foo:
    def __init__(self, name):
        self.name = name

    # 静态方法，如果方法无需使用对象中封装的值，那么就可以使用静态方法
    @staticmethod
    def f2():
        print('静态方法')  # 没有使用对象封装的值

Foo.f2()  # 可以通过类调用静态方法

obj = Foo('Thanlon')
obj.f2()  # 也可以通过对象调用方法
```
静态方法调用时，可以使用类.方法名，也可以使用对象.方法名，但推荐类来调用（调用字段的时候也是）。

③ 类方法
如果在方法中会使用到当前类，那么就可以使用类方法。定义类方法时，方法上方写@classmethod，方法中至少有一个参数cls。
```python
class Foo:
    def __init__(self, name):
        self.name = name
    @classmethod
    def show(cls):  # 和实例方法一样至少有一个参数，自动传递当前类
        print(cls)
Foo.show()
f = Foo('')
f.show()
'''
类方法！ <class '__main__.Foo'>
'''
```
类方法和静态方法一样，可以使用类.方法名，也可以使用对象.方法名，但推荐类来调用。
###### 9.2 私有方法
① 私有实例方法
对于私有实例方法可以通过非私有实例方法可以间接访问私有实例方法。	
```python
# 私有实例方法
class Foo:
    def __init__(self, name):
        self.name = name
    def __f(self):
        print(self.name)
    def getF(self):
        self.__f()
f = Foo('Thanlon')
# f.__f()  # 调用失败
f.getF()
'''
Thanlon
'''
```
① 私有静态方法
对于私有静态方法，我们可以通过非私有实例方法可以间接访问私有静态实例方法。
```python
# 私有静态方法
class Foo:
    def __init__(self, name):
        self.name = name
    @staticmethod
    def __f():
        print('私有静态方法！')
    def get_f(self):
        self.__f()
        # Foo.__f()
# 类.静态方法调用失败
# Foo.__f()
# 通过非私有静态方法
obj = Foo('Thanlon')
obj.get_f()
'''
私有静态方法！
'''
```
通过非私有静态方法也可以间接访问私有静态实例方法：
```python
# 私有静态方法
class Foo:
    def __init__(self, name):
        self.name = name
    @staticmethod
    def __f():
        print('通过非私有静态方法调用私有静态实例方法！')
    @staticmethod
    def get_f():
        Foo.__f()
# 类.静态方法调用失败
# Foo.__f()
# 类通过调用非私有静态方法间接调用私有静态实例方法！
Foo.get_f()
# 对象通过调用非私有静态方法间接调用私有静态实例方法
obj = Foo('Thanlon')
obj.get_f()
'''
私有静态方法！
'''
```
③ 私有类方法
通过非私有实例方法可以间接访问私有类方法。
```python
# 私有类方法
class Foo:
    def __init__(self, name):
        self.name = name
    @classmethod
    def __f(cls):
        print(cls)
    def get_f(self):
        self.__f()
        # Foo.__f()
obj = Foo('Thanlon')
obj.get_f()
'''
<class '__main__.Foo'>
'''
```
通过非私有静态方法也可以间接访问私有类方法：
```python
# 私有类方法
class Foo:
    def __init__(self, name):
        self.name = name

    # 私有静态方法
    @classmethod
    def __f(cls):
        print(cls)

    def get_f(self):
        self.__f()
        # Foo.__f()

    # 静态方法
    @staticmethod
    def reget_f():
        Foo.__f()
        
# 类调用静态方法reget_f
Foo.reget_f()

# 对象调用静态方法reget_f
obj = Foo('Thanlon')
obj.get_f()

'''
<class '__main__.Foo'>
<class '__main__.Foo'>
'''
```
##### 10. 属性
###### 10.1 属性的概念
属性是通过方法改造胡的，属性代码编写时需要方法的上面加上@property，方法的参数只有一个self。属性在调用时，无需加括号，使用对象.方法。属性的应用场景是对于简单的方法，当不需要传参且有返回值时，可以使用。

###### 10.2 属性与私有属性
```python
class Foo:
    def __init__(self):
        pass

    @property
    def start(self):
        return 'start'

    @property
    def stop(self):
        return 'stop'
        
f_obj = Foo()
print(f_obj.start, f_obj.stop)
'''
start stop
'''
```
当然，属性有公有和私有之分，私有属性的定义可以在方法的前面加上双下划线。私有属性可以通过使用类中的其它方法访问：
```python
class Foo:
    def __init__(self):
        pass
    # 私有属性__start
    @property
    def __start(self):
        return 'start!'
        
    # 私有属性__stop
    @property
    def __stop(self):
        return 'stop!'
        
    # 通过方法访问私有属性
    def get_start_stop(self):
        print(self.__start)
        print(self.__stop)
        
f_obj = Foo()
f_obj.get_start_stop()
'''
start!
stop!
'''
```
###### 10.3 练习题
实现分页：
```python
# coding:utf-8
class Pagination:
    '''
    处理分页的类
    '''
    def __init__(self, lst, page_num, per_page_num=10):
        '''
        initialize
        :param lst:所有数据
        :param page_num:查看的页码
        :param per_page_num:每页显示的数据记录数
        '''
        self.lst = lst
        self.page_num = page_num
        self.per_page_num = per_page_num

    @property
    def start(self):
        '''
        计算索引的起始位置
        :return:self.per_page_num * (self.page_num - 1)
        '''
        return self.per_page_num * (self.page_num - 1)

    @property
    def end(self):
        '''
        计算索引的结束位置
        :return:self.per_page_num * self.page_num
        '''
        return self.per_page_num * self.page_num

    def show(self):
        print(self.lst[self.start:self.end])

lst = []
for items in range(0, 1000):
    lst.append(items)

while True:
    # 查看的页码
    page_num = int(input('请输入页码：'))
    # 每页显示10条数据
    obj = Pagination(lst, page_num)
    obj.show()
```
>请输入页码：1
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
请输入页码：2
[10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
请输入页码：3
[20, 21, 22, 23, 24, 25, 26, 27, 28, 29]
请输入页码：
##### 11. 组合
组合：将一个类的对象封装到另一个类的对象的属性中，就叫组合。
```python
# 将教师类对象封装到学校类对象的属性中
class School(object):
    def __init__(self, sch_name, sch_addr, sch_postcode):
        self.sch_name = sch_name
        self.sch_addr = sch_addr
        self.sch_postcode = sch_postcode

    def teach_stu(self):
        pass


class Teacher(object):
    def __init__(self, name, age, salary):
        self.name = name
        self.age = age
        self.__salary = salary
        self.school = None


# 实例化School
school1 = School('华东理工大学', '中国上海', '200237')
school2 = School('华东师范大学', '中国上海', '200062')
# 实例化Teacher
teacher1 = Teacher('Thanlon', 23, 200000)
teacher2 = Teacher('Kiku', 25, 500000)
#为教师分配校区
teacher1.school = school1
teacher2.school = school2
#查看教师所在学校的相关信息
print(teacher1.school.sch_name)
print(teacher1.school.sch_addr)
print(teacher1.school.teach_stu())

print(teacher2.school.sch_name)
print(teacher2.school.sch_addr)
print(teacher2.school.teach_stu())
'''
华东理工大学
中国上海
None
华东师范大学
中国上海
None
'''
```
##### 12. 主动调用其他类的成员
① 方式一
```python
class Base(object):
    def f1(self):
        print('Base.f1()')
        pass

class Foo(object):
    def f1(self):
        Base.f1(self)

obj = Foo()
obj.f1()
```
通过对象调用实例方法：
```python
obj = Base()
obj.f1()
```
等价于用类这样调用实例方法（不常用）：
```python
obj = Base()
Base.f1(obj)
```
总结：实例方法的调用可以不通过对象去调用，可以通过类调用实例方法，但是需要手动传入对象，Base.实例方法(自己传入self)。

②  方式二
```python
# coding:utf-8
class Base(object):
    def f1(self):
        print('Base.f1()')
        pass

class Foo(Base):
    def f1(self):
        super().f1()

obj = Foo()
obj.f1()
'''
Base.f1()
'''
```
```python
# coding:utf-8
class Base(object):
    def f1(self):
        print('Base.f1()')
        pass

class Foo1(object):
    def f1(self):
        super().f1()

class Foo2(object):
    def f1(self):
        print('Foo2.f1()')

class Info(Foo1, Foo2):
    pass

obj = Info()
obj.f1()
'''
先找Info类中有无f1方法，Info类中没有按照继承顺序，找下一个类Foo1。
Foo1中找到f1方法，即Info类执行Foo1中的f1方法。
Foo1中的f1方法执行super().f1()，super().f1()即按照Info类的继承顺序找下一个类，
执行Foo2类中的f1方法
'''
```
##### 13. 特殊成员
① _ _ init _ _
类名()：自动执行该方法
```python
# coding:utf-8
class Foo(object):
    def __init__(self):
        print('__init__')
f = Foo()
'''
__init__
'''
```
② _ _ call _ _
对象()：自动执行 _ _ call _ _ 方法
```python
# coding:utf-8
class Foo(object):
    def __init__(self, name):
        self.name = name

    def __call__(self, *args, **kwargs):
        print(args, kwargs)

f = Foo('Thanlon')
# 对象()自动执行__call__方法：无返回值，返回None
f(1, 2, 3, k1=123)
```
③ _ _ getitem _ _
对象[]：自动执行_ _ getitem _ _ 方法
```python
# coding:utf-8
class Foo(object):
    def __init__(self, name):
        self.name = name

    def __getitem__(self, item):
        print(item)
        return 'kiku'
        
f = Foo('Thanlon')
# 对象[]自动执行_ _getitem_ _ 方法
print(f['Love']) # 
'''
Love
kiku
'''
```
④ _ _ setitem_ _
对象[]：自动执行_ _ getitem _ _ 方法
```python
# coding:utf-8
class Foo(object):
    def __init__(self, name):
        self.name = name

    def __getitem__(self, item):
        print(item)
        return 'kiku'
        
f = Foo('Thanlon')
# 对象[]自动执行_ _getitem_ _ 方法
print(f['Love']) # 
'''
Love
kiku
'''
```
age传给key，23传给value，如：f['age'] = 23。

⑤ _ _ delitem_ _
del 对象[xxx]：自动执行_ _ delitem_ _方法
```python
# coding:utf-8
class Foo(object):
    def __init__(self, name):
        self.name = name

    def __delitem__(self, key):
        print(key)
        
f = Foo('Thanlon')
del f['Thanlon'] # # 这种方式的写法是没有返回值的
'''
Thanlon
'''
```
⑥ _ _ add _ _
对象+对象：自动执行_ _ add_ _方法
```python
# coding:utf-8
class Foo(object):
    def __init__(self, x):
        self.x = x

    def __add__(self, other):
        return (self.x + other.x)  # f1.x+f2.x

f1 = Foo(1)
f2 = Foo(2)
print(f1 + f2)
'''
3
'''
```
⑦ _ _ enter _ _ 与_ _ exit _ _
with 对象：自动执行 _ _ enter _ _ 和 _ _ exit _ _方法
```python
# coding:utf-8
class Foo(object):
    def __init__(self, x):
        self.x = x

    def __enter__(self):
        print('__enter__')

    def __exit__(self, exc_type, exc_val, exc_tb):
        print('__exit__')

f1 = Foo(1)
with f1:
    print('with中的code!')
```
as接收_ _ enter _ _方法的返回值：
```python
# coding:utf-8
class Foo(object):
    def __init__(self, x):
        self.x = x

    def __enter__(self):
        print('__enter__')
        return 'return value '

    def __exit__(self, exc_type, exc_val, exc_tb):
        print('__exit__')

f1 = Foo(1)
with f1 as f:
    print(f)
    print('with中的code!')
'''
__enter__
return value 
with中的code!
__exit__
'''
```
⑧ _ _ new _ _

类()：其实先执行_ _ new _ _ 方法，再执行 _ _ init _ _ 方法。在_ _ new _ _ 中创建类的对象并返回，这样__init__中就有了对象。**`__new__返回哪个类执行哪个类的构造方法。`**
```python
# coding:utf-8
class Foo(object):
    def __init__(self):
        print('__init__')

    def __new__(cls, *args, **kwargs):
        print('__new__')

f1 = Foo()

'''
_ _new_ _
'''
```
>**`如果没有自定义__new__方法打印f1，则得到的是f1对象！`**

程序执行了_ _ new_ _ 方法，打印了“_ _ new_ _ ”。但是，没有执行 _ _ new _ _ 方法中的print('init')语句，说明：先执行的是 _ _ new _ _ 方法，后执行 _ _ init _ _ 方法。
```python
# coding:utf-8
class Foo(object):
    def __init__(self, name):  # 初始化方法
        '''
        初始化空的对象(__new__方法返回的空对象)或者说为空对象进行数据初始化
        :param name:
        '''
        self.name = name
        print('__init__')

    def __new__(cls, *args, **kwargs):  # 构造方法
        '''
        创建一个当前类的空对象
        :param args:
        :param kwargs:
        :return:
        '''
        print('_ _new_ _')
        # 所有的对象都是object创建的
        return object.__new__(cls)  # Python内部创建一个当前类的空对象（该对象的内部是空的）

f1 = Foo('Thanlon')  # 这个对象实际上是由以上两个方法创建的

'''
_ _new_ _
__init__
'''
```
_ _ init _ _ 方法只有在_ _ new _ _方法有返回值且返回值是当前类创建的对象时才能被调用。
特定（相应）的语法会触发（对应）面向对象中的特殊方法。
##### 14. isinstance、type、issubclass
###### 14.1 isinstance
isinstance函数：检查第一个参数（子类）是否是第二个参数（父类及父类的父类……）的子类。
```python
# coding:utf-8
class Base(object):
    pass

class Foo(Base):
    pass

class Foo2(Foo):
    pass

print(issubclass(Foo, Base))
print(issubclass(Foo2, Base))
'''
True
True
'''
```
###### 14.2 type
type函数：返回对象的类型，获取对象是由哪个类创建的。
```python
# coding:utf-8
class Base(object):
    pass

b = Base()
print(b, type(b))
'''
<__main__.Base object at 0x000002337B1E9630> <class '__main__.Base'>
'''
if type(b) == Base:
   print('b是Base类型！')
```
type类的应用：计算类的数量
```python
# coding:utf-8
'''
计算类的数量
'''
class Foo1(object):
    pass

class Foo2(object):
    pass

def f(*args):
    foo1_count = 0
    foo2_count = 0
    for item in args:
        if type(item) == Foo1:
            foo1_count += 1
        else:
            foo2_count += 1
    return foo1_count, foo2_count  # 返回一个元组，等价于 return (foo1_count, foo2_count)

print(f(Foo1(), Foo2(), Foo1(), Foo2, Foo1()))
'''
(3, 2)
'''
ret1, ret2 = f(Foo1(), Foo2(), Foo1(), Foo2, Foo1())
print(ret1, ret2)
'''
3 2
'''
```
###### 14.3 issubclass
isinstance函数：判断第对象是否是某一个指定类或其及父类的实例。
```python
# coding:utf-8
'''
isinstance函数判断第一个参数（对象）是否是第二个参数（类及所有父类）的实例
'''

class Base(object):
    pass

class Foo(Base):
    pass

foo = Foo()
print(isinstance(foo, Foo))
print(isinstance(foo, Base))
'''
True
True
'''
b = Base()
print(isinstance(b, Base))
print(isinstance(b, Foo))  # 对象b不是Foo类的实例
'''
True
False
'''
```
##### 15. 区分函数和方法
一般我们认为写在类中的是方法，写在外面的是函数。但这样说并不准确，下面将深入探讨方法和函数的区分：
在外部定义的是函数：
```python
def func():
    pass
    
print(func)
'''
<function func at 0x000001AC2340C1E0>
'''
```
在类内部定义的可以是方法：
```python
# coding:utf-8
class Foo(object):
    def f(self):
        pass
        
obj = Foo()
print(obj.f)
'''
<bound method Foo.f of <__main__.Foo object at 0x00000254215AB1D0>>
'''
```
类调用静态方法，会把静态方法当作函数。所以，在类中定义的不一定是方法，还可以是函数：
```python
# coding:utf-8
'''
定义在类中的还可以是函数
'''
class Foo(object):
    def f(self):
        pass

    @staticmethod
    def f2():
        pass

obj = Foo()
print(Foo.f2)  # 函数
print(obj.f2)  # 函数
'''
<function Foo.f2 at 0x000001AF9471C7B8>
<bound method Foo.f of <__main__.Foo object at 0x000001AF9467B198>>
'''
```
再次探讨：使用类调用实例方法，会把实例方法当作函数，需要手动传self。所以，类中定义的也不一定是方法：
```python
# coding:utf-8
class Foo(object):
    def f1(self):
        pass

    @staticmethod
    def f2():
        pass

obj = Foo()
Foo.f1(obj)  # obj需要自己传参
print(Foo.f1)  # 把f1当作函数

obj = Foo()
obj.f1()  # 不需要自己传参
print(obj.f1)  # 把f1当作方法
'''
<function Foo.f1 at 0x000001F67119C730>
<bound method Foo.f1 of <__main__.Foo object at 0x000001F671193588>>
'''
```
准确判断是方法还是函数？
```python
# coding:utf-8
from types import MethodType, FunctionType

def check(param):
    if isinstance(param, MethodType):
        print(param, 'is a method!')
    elif isinstance(param, FunctionType):
        print(param, 'is a function!')
    else:
        print('Others!')

class Foo(object):
    def f1(self):
        pass

    @staticmethod
    def f2():
        pass

obj = Foo()
check(obj.f1)  # 方法
check(Foo.f2)  # 函数
check(obj.f2)  # 函数
'''
<bound method Foo.f1 of <__main__.Foo object at 0x000001F62C49C198>> is a method!
<function Foo.f2 at 0x000001F62C4A1510> is a function!
<function Foo.f2 at 0x000001F62C4A1510> is a function!
'''
```
新的发现，对象调用的是方法，类调用的是函数，且函数需要手动传参：
```python
# coding:utf-8
class Foo(object):
    def f1(self):
        pass

    def f2(self):
        pass

    def f3(self):
        pass

    lst = [f1, f2]

obj = Foo()
obj.lst.append(obj.f3)
for item in Foo.lst:
    print(item)
'''
<function Foo.f1 at 0x000001E53675C730>
<function Foo.f2 at 0x000001E53675C7B8>
<bound method Foo.f3 of <__main__.Foo object at 0x000001E536753588>>
'''
```
总结：一般我们认为在类中是方法，写在外面的是函数。其实，这样判断是函数还是方法是不精准的。方法和函数的区分，不仅和定义的位置有关系，还和方法或函数的调用者有关系。如果通过对象.xxx调用，那么xxx就是方法；如果通过类.xxx调用或者直接执行xxx，那么xxx就是个函数。面向对象中，方法中self不需要自己传参，而函数中每个参数都需要自己传参。
##### 16. 反射
###### 16.1 初识反射
① 什么是反射
python面向对象中的反射就是通过字符串获取模块、对象或类的属性，进行操作。
② 为什么使用反射
有这样的一种场景：用户输入函数序号来执行函数。当没有使用反射时，可以这样设计程序：
```python
# coding:utf-8
def func01():
    print('func01')

def func02():
    print('func02')

def func03():
    print('func03')
```
```python
# coding:utf-8
import deal

while True:
    print('''
    系统支持的函数：
    1、f1
    2、f2
    3、f3
    4、f4
    ''')
    func_name = input(' 请输入您要执行的函数序号：')
    if func_name == '1':
        deal.func01()
    elif func_name == '2':
        deal.func02()
    elif func_name == '3':
        deal.func03()
```
如果在函数很多的情况下，就需要写很多判断条件。下面你来看使用反射实现相同功能的程序代码：
```python
# coding:utf-8
import deal
from types import FunctionType

while True:
    print('''
    系统支持的函数：
    1、f1
    2、f2
    3、f3
    4、f4
    ''')
    func_name = input(' 请输入您要执行的函数序号：')
    # 使用反射：
    if hasattr(deal, func_name):
        func_or_value = getattr(deal, func_name)  # func_name是字符串，根据字符串去模块中找与之同名的成员
        if isinstance(func_or_value, FunctionType):  # 可能是值，也可能是函数，所以在这里需要去判断
            func_or_value()
        else:
            print(func_or_value)
    else:
        print('deal模块中不存在输入的函数名！')
```
如果不断增加函数，不使用反射会写很多判断条件。而使用反射，很明显程序中可以少写很多代码。
###### 16.2 反射在面向对象中的应用
③ getattr
getattr：根据字符串为参数去对象（对象、类、模块）中寻找与之同名的成员。根据字符串为参数去模块中寻找与之同名的成员：
```python
# coding:utf-8
name = 'Thanlon'
def f1(arg):
    print(arg, 'is good!')
```
```python
# coding:utf-8
import module
v =  getattr(module,'name')
print(v)
func_name = getattr(module,'f1')
func_name('Thanlon')
'''
Thanlon
Thanlon is good!
''
```
根据字符串为参数去类和对象中寻找与之同名的成员：
```python
# coding:utf-8
class Foo(object):
    country = 'China'

    def f1(self0):
        print('f1')

value_name = getattr(Foo, 'country') # 静态字段
print(value_name)

obj = Foo()
value_name = getattr(obj, 'country')# 实例变量
print(value_name)

func_name = getattr(Foo, 'f1') # 函数
print(func_name)

func_name = getattr(obj, 'f1') # 方法
print(func_name)
'''
China
China
<function Foo.f1 at 0x000001EAF1D9D7B8>
<bound method Foo.f1 of <__main__.Foo object at 0x000001EAF1DAD240>>
'''
```
练习：在用户对象中找到登录和注册方法
```python
# coding:utf-8
class User(object):
    func_lst = ['register', 'login']

    def register(self):
        print('register')

    def login(self):
        print('login')

    def run(self):
        print('''
            系统支持的函数：
            1、注册
            2、登录
            ''')
        choice = int(input('请输入要执行序号(序号对应相应的方法)：'))
        func_name = User.func_lst[choice - 1]  # 类变量优先通过类去调用，这里用User;当然也可以用对象self
        # func = getattr(User, func_name)  # User.register、User.login；类.函数
        # func(self)
        func = getattr(self, func_name)  # self.register、self.login；对象.方法
        func()

obj = User()
obj.run()
obj2 = User()
obj2.run()
```
② hasattr
hasattr：根据字符串形式，去判断对象中是否有成员
```python
# coding:utf-8
import module
v_ret = hasattr(module,'name')
func_ret = hasattr(module,'f1')
print(v_ret,func_ret)
'''
True True
'''
```
③ setattr
setattr：根据字符串形式，动态去设置一个成员（内存）
```python
# coding:utf-8
import module
setattr(module,'lover','Kiku')
v = getattr(module,'lover')
print(v)
    
setattr(module,'f2',lambda x:x*2)
func_name = getattr(module,'f2')
print(func_name)
print(func_name(1996))
'''
Kiku
<function <lambda> at 0x0000020189A3C1E0>
3992
'''
```
注意：如果设置属性，为让大家明白，需要在清楚写明类中有哪些设置的成员，如在 _ _ init _ _方中self.age = None。不建议使用setattr方法。
```python
# coding:utf-8
import module

class Foo(object):
    def __init__(self, name):
        self.name = name
        self.age = None  # 等待setattr

obj = Foo('Thanlon')
setattr(obj, 'age', '23')
setattr(Foo, 'age', '23')
print(getattr(Foo,'age'))
```
④ delattr
delattr：根据字符串形式，动态删除一个成员（内存）
```python
# coding:utf-8
import module
setattr(module,'lover','Kiku')
v = getattr(module,'lover')
print(v)

setattr(module,'f2',lambda x:x*2)
func_name = getattr(module,'f2')
print(func_name)
print(func_name(1996))

delattr(module,'lover')
v = getattr(module,'lover')
delattr(module,'f2')
func_name = getattr(module,'f2')
```
##### 17. 约束
###### 17.1 约束的实现
Foo类继承了父类Base，Base中存在f方法，f方法中抛出一个NotImplementedError的异常。在Foo中没有重写Base中的f方法时，调用f方法，抛出异常，表示Foo方法中必须重写f方法。通过这种做法，强制类中必须重写父类中的方法，进而可以实现约束。
```python
# coding:utf-8
class Base(object):
    def f(self):
        raise NotImplementedError('f方法必须被重写！')

class Foo(Base):
    pass

obj = Foo()
obj.f()
'''
NotImplementedError: f方法必须被重写！
'''
···
重写父类中的f方法自然就没有异常信息。
```python
# coding:utf-8
class Base(object):
    def f(self):
        raise NotImplementedError('f方法必须被重写！')

class Foo(Base):
    def f(self):
        pass

obj = Foo()
obj.f()
```
###### 17.2 约束的应用场景
多个类，内部都必须有某些方法时，需要使用基类+异常进行约束。

###### 17.3 抽象类与抽象方法实现约束
定义抽象类和抽象方法，如果某类继承了抽象类，必须重写抽象方法，否则会报错
```python
from abc import ABCMeta, abstractmethod

class Base(object, metaclass=ABCMeta):  # 定义一个抽象类

    def f1(self):
        print('f1')

    @abstractmethod
    def f2(self):
        '''
        抽象方法
        :return:
        '''
        pass

class Foo(Base):
    pass

obj = Foo()
'''
如果没有重写抽象方法，不能实例化类
Can't instantiate abstract class Foo with abstract methods f2
'''
```
需要重写了抽象类的f2方法：
```python
from abc import ABCMeta, abstractmethod

class Base(object, metaclass=ABCMeta):  # 定义一个抽象类

    def f1(self):
        print('f1')

    @abstractmethod
    def f2(self):
        '''
        抽象方法
        :return:
        '''
        pass

class Foo(Base):
    def f2(self):
        pass

obj = Foo()
```
###### 18. super和执行类的区别
实例化对象时会执行构造方法，如果没有写，会执行父类的构造方法:
```py
# coding:utf-8
class Foo(object):
    pass

obj = Foo()  # 会执行构造方法，如果没有写，会执行父类的构造方法
```
① 根据mro的顺序执行方法：<kbd>super(Foo, self).func()</kbd>
```py
# coding:utf-8
class Base(object):
    def func(self):
        print('Base.func')

class Foo(Base):
    def func(self):
        # 方式一：根据mro的顺序执行方法
        super(Foo, self).func()
        print('Foo.func')

obj = Foo()
obj.func()
'''
Base.func
Foo.func
'''
```
```py
# coding:utf-8
class Base(object):
    def func(self):
        super(Base, self).func()
        print('Base.func')

class Bar(object):
    def func(self):
        print('Bar.func')

class Foo(Base, Bar):
    pass

obj = Foo()
obj.func()
'''
Base.func
Foo.func
'''
```
```py
# coding:utf-8
class Base(object):
    def func(self):
        super(Base, self).func()
        print('Base.func')

class Bar(object):
    def func(self):
        print('Bar.func')

class Foo(Base, Bar):
    pass

# obj = Foo()
# obj.func()
print(Foo.__mro__)
'''
(<class '__main__.Foo'>, <class '__main__.Base'>, <class '__main__.Bar'>, <class 'object'>)
'''
```
② 主动执行Base类的方法：<kbd>Base.func(self)</kbd>
```py
# coding:utf-8
class Base(object):
    def func(self):
        print('Base.func')

class Foo(Base):
    def func(self):
        # 方式一：根据mro的顺序执行方法
        # super(Foo, self).func()
        # 方式二：主动执行Base类的方法
        Base.func(self)  # 如果是对象.func(),self会自动传进来
        print('Foo.func')

obj = Foo()
obj.func()
'''
Base.func
Foo.func
'''
```
```py
# coding:utf-8
class Base(object):
    def func(self):
        super(Base, self).func()
        print('Base.func')

class Bar(object):
    def func(self):
        print('Bar.func')

class Foo(Base, Bar):
    pass

obj = Base()
obj.func()
'''
AttributeError: 'super' object has no attribute 'func'
'''
```
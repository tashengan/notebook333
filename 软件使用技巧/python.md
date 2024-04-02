1991年，第一个python解释器由龟叔开发，直译过来是蟒蛇

解释器：将python代码转为二进制，让计算机能读懂

### 1.基础知识

##### （1）字面量

int

float

字符串：用""包含

##### （2）注释

```python
#
'''
注释内容
'''
```

##### （3）变量

作用：在程序运行时，记录数据

```
# 变量名 = 变量值
money = 50
money = money - 10
```

##### （4）数据类型

```python
# 查看数据类型
type()
type(666)  # 输出<class 'int'>
# 三种常用数据类型
int # 整数型
float # 浮点数
string # 字符串
```

##### （5）数据类型转换

```python
# 常见转换语句
int(x)  # 字符串转整数，需要保证字符串里全为数字，浮点数转整数小数部分会被舍弃
float(x)  # 
str(x)
```

##### （6）标识符

```
# 标识符：变量的名字、方法的名字、类的名字等
# 英文、数字、下划线 （数字不可用于开头）
# 不可使用关键字
# 大小写区分
```

##### （7）运算符

```
+ - * /
//  # 取模运算
%  # 取余运算
**  # 指数
```

```python
# 赋值运算符
=  #将等号右边的结果赋值给左边的变量
+=  -=  *=  /=  %=  **=  //=  
c+=a  # 等效于c = c+a
```

##### （8）字符串

```python
# 单引号  可内含双引号
name = '"字符串"'
# 双引号  可内含单引号  可使用转义字符(\)将引号解除效用，变为普通字符串
name = "\"字符串\""
# 三引号
''''''
```

```python
# 字符串拼接  只能字符串相拼接
"hello"+"world"  # 通过+直接拼接
```

```python
# 字符串格式化
%s  # 将内容转换为字符串，放入占位位置
%d  # 转为整数...
%f  # 转为浮点数类型...
"hello %s" % "world" # 将%后的内容放入到%s位置上
score1 = 86
score2 = 98
score = "张三：%s 李四：%s" % (score1,score2) 
```

```python
# 字符串数字精度控制
m，控制宽度，要求是数字（很少使用）,设置的宽度小于数字自身，不生效
.n，控制小数点精度，要求是数字，会进行小数的四舍五入

%5d：表示将整数的宽度控制在5位，如数字11，被设置为5d，就会变成：[空格[空格[空格]11，用三个空格补足宽度。
%5.2f：表示将宽度控制为5，将小数点精度设置为2
	小数点和小数部分也算入宽度计算。如，对11.345设置了%7.2f后，结果是：[空格[空格]11.35。2个空格补足宽度，小数部分限制2位精度后，四舍五入为.35
%.2f：表示不限制宽度，只设置小数点精度为2，如11.345设置%.2f后，结果是11.35

```

```python
# 字符串快速格式化  没有数据类型限制，没有精度控制
语法：f"内容[变量}"的格式来快速格式化
name = "传智播客"
set_up_year = 2006
stock_price = 19.99
# f: format(格式化)
print(f"我是{name},成立于：{set_up_year}年，今天的股价是：{stock_price}")

# 表达式直接放到{}里面，结果直接会输出结果。{}里面不一定要写变量
print(f"2*4的结果是：{2*4}")  # 结果会直接输出8
```

##### （9）数据输入

```
# 用于获取键盘输入数据
input()  #输入数据类型均为字符串

name = input("请告诉我你是谁？")
print("我知道了，你是：%s" % name)  #键盘输入name
```



### 2.逻辑判断结构

##### （1）布尔类型和比较运算符

```python
# 比较运算符  返回值为True或False
==  #等于
！=  #不等于
>  <  >=  <=
```

##### （2）if else语句

```python
if 要判断的条件：
	条件成立时，执行体1
else:
    条件不成立时，执行体2
```

##### （3）if elif else语句

```python
if 条件1：
	条件1满足时，执行体1
elif 条件2:
	条件2满足时，执行体2
elif 条件3:
	条件3满足时，执行体3
	...
else:
    条件都不满足时，执行体n
```

##### （4）嵌套语句

```python
# if else
if 条件1：
	条件执行体1
    if 条件2：
    	条件执行体2
        ...
```

##### （6）continue和break

```python
# continue:中断本次循环，直接进入下一次循环
for i in range(1, 100)：
	语句1
	continue
	语句2
```

```python
# break: 直接结束所在循环

```



### 3.循环结构

##### （1）while循环语句

```python
while 循环条件
	循环体
i = 0
while i < 100
	print(1)
    i += 1
```

```python
import random
num = random.randint(1, 100)
count = 0

flag = True
while flag:
    guess_num = int(input("请输入猜想的数字"))
    count += 1
    if guess_num == num:
        print("恭喜您猜中了")
        flag = False
    else:
        if guess_num > num:
            print("您猜大了，请再猜一次")
        else:
            print("您猜小了，请再猜一次")

print(f"您总共猜测了{count}次")
```

##### （2）while嵌套循环

```python
while 条件1：
	条件1满足时，执行体1
	...
    while 条件2：
    条件2满足时，执行体2
    ...
```

```python
print("hello",end='') #实现打印输出的不换行
print("world",end='') 
print()  # 实现换行
# \t  #实现多行字符串进行对齐
print("hello\tworld")
print("itheima\tbest")

i = 1
while i <= 9:
    j = 1
    while j <= i:
        print(f"{j} * {i} = {i*j}\t", end='')
        j += 1
    i += 1
    print()  # 空内容，实现一个换行
```

##### （3）for循环

```python
for 临时变量 in 待处理数据集（序列）：
	循环满足条件时执行的代码
name = "itheima"
for x in name:  # 遍历，for只能从被处理的数据集中，依次取出内容进行处理
    print(x)
```

##### （4）range语句

```python 
range(num)  # 生成一个0-num的整数，不包含num
range(num1, num2)  # 默认步长为1
range(num1, num2, step)  # 生成一个num1-num2的整数序列
```

```python
# for循环中的变量为临时变量，一般在for外部不建议使用
for x in range(5, 10):  # x可以省略
	print(x)  # 5、6、7、8、9
# 如果想在for外也使用for中的变量，应在for前定义这个变量
```

##### （5）for嵌套循环

```python
i = 1
for i in range(1, 101):
    print(f"第{i}次表白")
    j = 1
    for j in range(1, 11):
        print(f"送第{j}朵花")
        print("我喜欢你")
        j += 1
    i += 1
print("表白成功")
```



### 4.函数

##### （1）定义

```python
# 组织好的，可重复使用的，用于实现特定功能的代码块

# 函数的定义
def 函数名（传入参数）:
	函数体
    return 返回值

# 函数的调用
函数名（参数）
```

##### （2）返回值

```python
# 在函数中，return后面的语句不再执行
# 在没有写返回值的时候，函数会有返回值None
# 返回值的类型为：None Type
# 应用场景：
# 1.用在if判断上： None等同于False
def check_age(age):
    if age >= 18:
        return "SUCCESS"
    else:
        return None
result = check_age(16)
if not result:
    print("未满18岁，不可进入")

# 2.用于声明无内容的变量上
# 定义变量时，但暂时不需变量有具体的值，可以用None代替
name = None
```

##### （3）函数的说明文档

```python
# 通过多行注释的方式，对函数进行说明解释
def func(x, y)  # 当在def下面打出多行注释符就自动写好函数说明的格式
	"""
	函数说明
	：param x：形参x的说明
	：param y：形参y的说明
	：return：返回值的说明
	"""
    函数体
    return 返回值
func(5,6)   # 光标放在（5,6）上就会出现函数说明
```

##### （4）函数的嵌套调用

```python
# 一个函数里面调用另外一个函数，会先执行完另一个函数
```

##### （5）变量的作用域

```python
# 局部变量：函数体内部的变量，不可被函数外部调用，在函数体内执行完就被销毁
# 函数体内部对全局变量进行修改，只对函数体内生效
# 全局变量：

# global关键字：将局部变量设置为全局变量
num = 100
def func():
    global num
    num = 500
    print(f"func：{num}")
func()
print(num)
```


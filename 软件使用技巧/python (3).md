1991年，第一个python解释器由龟叔开发，直译过来是蟒蛇

解释器：将python代码转为二进制，让计算机能读懂

# 一、基础版

### 1.基础知识

##### （1）字面量

```python
int  # 整数型变量
float  # 小数型变量
字符串：用""包含
```



##### （2）注释

```python
#
'''
注释内容
'''
```

##### （3）变量

作用：在程序运行时，记录数据

```python
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

```python
# 标识符：变量的名字、方法的名字、类的名字等
# 英文、数字、下划线 （数字不可用于开头）
# 不可使用关键字
# 大小写区分
```

##### （7）运算符

```python
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

```python
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



### 3.循环语句

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

```python
# 制作银行ATM机用户操作界面
money = 5000000
name = None
# 定义查询函数
def query():
    print("---------查询余额---------")
    print(f"{name}，您的余额为：{money}")
# 定义存款函数
def save_money():
    print("----------存款----------")
    global money
    save = int(input("请输入您的存款金额："))
    money += save
    print(f"{name}，您的余额为：{money}")
# 定义取款函数
def draw_money():
    print("----------取款----------")
    global money
    draw = int(input("请输入您的取款金额："))
    money -= draw
    print(f"{name}，您的余额为：{money}")
# 定义主函数
def main():
    global name
    name = input("请输入您的姓名：")
    print("----------主菜单----------")
    print(f"{name}，您好，欢迎来到黑马银行ATM。请选择执行操作：")
    print("查询余额\t[输入1]")
    print("存款\t\t[输入2]")
    print("取款\t\t[输入3]")
    print("退出\t\t[输入4]")
    while True:
        keyboard = int(input("请输入您的选择："))
        if keyboard == 1:
            query()
            continue
        elif keyboard == 2:
            save_money()
            continue
        elif keyboard == 3:
            draw_money()
            continue
        else:
            print("程序结束")
            break
# 调用主函数
main()
```



### 5.数据容器

##### （1）概念

```python
# 一个容器可以容纳多份数据，每份数据称之为元素
# 数据容器分为5类：
# 	列表（list）
#	元组（tuple）
#	字符串（str）
#	集合（set）
#	字典（dict）
```

##### （2）列表

```python
# 基本语法   列表可以存储多种数据类型
变量名称 = [元素1， 元素2,...,元素n]
# 定义空列表
变量名称 = []
变量名称 = list()
```

```python
# 列表的下标索引  从0开始索引
mylist = ["itheima", 666, True]
print(mylist[0])  # 输出itheima  顺序
print(mylist[1])  # 输出666      
print(mylist[-1])  # 输出Ture    倒序
print(mylist[-2])  # 输出666
# 如果列表式嵌套的列表，同样支持下标索引   
```

```python
# 列表的常用操作
# 在python中，如果将函数定义为class(类)的成员，那么函数会称之为：方法
class student:
    def add(self, x, y):
        return x+y
# 类中函数的调用，方法和函数的功能相同
student = student()
num = student.add(1,2)

mylist = ["itheima", 666, True]
# 查询功能：查询列表的下标
index = mylist.index(666)
# 如果查询的元素不存在，就会报错

# 修改指定下标元素
mylist[0] = 666

# 插入元素
.insert(下标，元素)
mylist.insert(1, "best")
    
# 追加元素：将指定元素添加到列表的尾部
.append(元素)  
mylist.append(6899)
# 追加一批元素：将其他数据容器的内容取出，依次追加到列表尾部
.extend(其他数据容器)
mylist2 = [1, 2, 3]
mylist.extend(mylist2)

# 元素的删除
del 列表[下标]
del mylist[2]
列表.pop(下标)
element = mylist.pop(2)  # element接收删除的元素
# 删除指定元素
mylist.remove(6899)  # 从左向右只删除第一个6899元素
# 清空列表
mylist.clear()

# 统计某元素在列表中的数量
count = mylist.count(666)
# 统计列表中的元素数量
count = len(mylist)
```

```python
# 列表的遍历
# while循环
index = 0
while index < len(列表):
    元素 = 列表[index]
    对元素进行处理
    index += 1

# for 循环
for 临时变量 in 数据容器:
    对临时变量进行处理

```

##### （3）元组

```python
# 元组与列表的区别在于，元组不可以修改
# 定义元组：
(元素,元素,元素,...,元素)
t1 = (1,"hello",True)
t2 = ()
t3 = tuple()
# 如果定义单个元素的元组需要加逗号
t4 = ("hello",)
# 取出嵌套元组中的元素
t5 = ((1, 2, 3), (4, 5, 6))
num = t5[1][2]

# index查找
index = t1.index(1)
# count统计
num = t1.count(True)
# len统计元组元素数量
num = len(t1)
# 元组的遍历(同上列表)
while
for

# 元组中嵌套一个list，list中的内容可以修改

```

##### （4）字符串

```python
# 字符串不可以修改
# 通过下标索引取值
my_str = "itheima and itcast"
value = my_str[2]
value2 = my_str[-16]
my_str.index("and")

# 替换:replace
# 并不会修改原来的字符串，而是会生成一个新的字符串
new = my_str.replace("it","程序" ) # 将"it"替换为"程序"
# 切分：split  给出字符，将按字符进行切分
my_str_split = my_str.split(" ") # 切分后形成列表

# 字符串的规整操作（去除前后空格）：strip
my_str2 = " itheima and itcast "
new_mystr = my_str2.strip() # 默认去除字符串首尾空格
my_str.strip("12") #将字符串中含1和2的去除
# 统计出现次数：count
# 统计字符串长度：len
```

##### （5）序列

```python
# 序列是指内容连续有序，可使用下标索引的一类数据容器
# 列表、元组、字符串均可视为序列
# 切片：从序列中取出一个子序列，得到一个新的序列
序列[起始下标：结束下标：步长] # 不含结束下标
# 步长为负，表示从右向左取
mylist = [0, 1, 2, 3, 4, 5, 6]
result1 = mylist[1:4] # [1, 2, 3]
result2 = mylist[:] # [0, 1, 2, 3, 4, 5, 6]
result3 = mylist[::2] # [0, 2, 4, 6]
```

##### （6）集合

```python
# 不支持元素重复，去重，顺序无序，不支持下标索引，允许修改
变量名称 = {元素， 元素,...,元素}
变量名称 = set()
# add()：添加新元素
# remove()：将指定元素从集合内移除
# pop()：从集合中随机取一个元素
# clear()：清空集合

# 取出两个集合的差集
set1 = {1, 2, 3}
set2 = {1, 5, 6}
set3 = set1.difference(set2) # 得到一个新集合，集合1有的而集合2没有
# 消除两个集合的差集,在set1中删除与set2相同的元素
set1.difference_update(set2)
# 合并2个集合
set5 = set1.union(set2)
# 统计集合数量
num = len(set1)
# 集合的遍历：不能用while，但可以用for
for element in set1:
    print(f"集合的元素有{element}") 
```

##### （7）字典

```python
# 通过key和value组合(键值对)
# key不可以重复，value可以重复
# 字典中的key和value可以是任意数据类型，但key不可以为字典
{key:value, key:value,...}
dect = {"王力宏":99, "周杰伦":80, "林俊杰":77}
# 定义空字典
dict1 = {}
dict2 = dict()
# 从字典中基于key获取value
score = dect["周杰伦"]
print(score)
```

```python
# 字典的嵌套
stu_score_dict = {
    "王力宏": {"语文": 77, "数学": 66, "英语": 33},
    "周杰伦": {"语文": 88, "数学": 86, "英语": 55},
    "林俊杰": {"语文": 99, "数学": 96, "英语": 66}
}
# 从嵌套字典中获取信息
score = stu_score_dict["周杰伦"]["语文"]
```

```python
# 新增元素
dect = {"王力宏":99, "周杰伦":80, "林俊杰":77}
dect["张信哲"] = 66
# 更新元素
dect["周杰伦"] = 33
# 删除元素
dect.pop("周杰伦")
# 清空元素
dect.clear()
# 获取全部的key
keys = dect.keys()
# 遍历字典
for key in keys:
    print(f"字典的key是：{key}")
    print(f"字典的value是：{dect[key]}")
for key in dect:
# 统计字典的元素数量
num = len(dect)
```

```python
# 给级别为1的员工加薪1000元
print("全体员工当前信息如下：")
my_dict = {
    "王力宏": {"部门": "科技部", "工资": 3000, "级别": 1},
    "周杰伦": {"部门": "市场部", "工资": 5000, "级别": 2},
    "林俊杰": {"部门": "市场部", "工资": 7000, "级别": 3},
    "张学友": {"部门": "科技部", "工资": 4000, "级别": 1},
    "刘德华": {"部门": "市场部", "工资": 6000, "级别": 2}
}
print(my_dict)

for name in my_dict:
    if my_dict[name]["级别"] == 1:
        employee = my_dict[name]
        employee["级别"] += 1
        employee["工资"] += 1000
        # 将内层嵌套字典更新回外部字典
        my_dict[name] = employee
print(my_dict)

print("全体员工级别为1的员工完成升职加薪操作，操作后：")
my_dict["王力宏"]["工资"] = 4000
my_dict["王力宏"]["级别"] = 2
my_dict["张学友"]["工资"] = 5000
my_dict["张学友"]["级别"] = 2
print(my_dict)
```

```python
# 容器通用操作
max()
min()
# 数据类型转换
list() # 转列表，将字符串中元素拆分，字典中只保留键
tuple() # 转元组，将字符串中元素拆分，字典中只保留键
str() # 转字符串，都会保留
set() # 转集合
# 排序
sorted() # 顺序，排序完，都变为列表对象
sorted(my_list, reverse = True) # 倒序
```

```python
# 字符串的大小比较
# 通过ASCLL码表，都对应一个ASCll码
大小写英文单词
数字
特殊符号
# 字符串按位比较，从左边开始比较
```



###  6.函数进阶

##### （1）函数的多返回值

```python
# 两个return只会执行第一个return，跳过下面的内容
def return_num():
	return 1
	return 2

# 一个函数有多个返回值,用一个return
def test_return():
    return 1, "hello", True
x,y,z = test_return()  # 用多个变量接收
```

##### （2）多种传参方式

```python
# 1.关键字参数：函数调用通过“键=值”形式传递参数
def user_info(name, age, gender):
    print(f"您的名字是：{name}，年龄是{age}，性别是{gender}")

# 可以混合使用，混合使用时，顺序不能乱；键值对顺序可以换
user_info(name="小明", age=20, gender="男")
```

```python
# 2.缺省参数：不传参使用默认值，传参使用传参值
# 默认值设置统一在最后面设置
def user_info(name, age, gender='男'):
    print(f"您的名字是：{name}，年龄是{age}，性别是{gender}")
# 如下：name设置默认值而age没有设置默认值就会报错  
def user_info(name="小王", age, gender='男'):
    print(f"您的名字是：{name}，年龄是{age}，性别是{gender}")
```

```python
# 3.不定长参数：也称为可变参数，用于不确定调用的时候会传递多少个参数
def user_info(*args):  # 传进的所有参数都会被args收集，根据传进参数的位置合并为一个元组
    print(args)

user_info("TOM", 18)
```

```python
# 4.关键字传递：可变参数，传递的参数是键值对，根据传进的参数组成一个字典
def user_info3(**kwargs):
    print(kwargs)

user_info3(name = "TOM",  age = 18, id = 110)
```

##### （3）匿名函数

```python
# 函数作为参数传递：被传入的数据是确定的，计算逻辑是不确定的
# lambda匿名函数的语法
def 关键字，可以定义带有名称的函数，可重复使用
lambda 关键字，可以定义匿名函数（无名称），只可临时使用一次，可以不用return返回参数
lambda 传入参数：函数体

def test_func2(compute1):
    result = compute(1, 2)
    print(f"compute参数的类型是：{type(compute)}")
    print(f"计算结果是：{result}")
test_func2(lambda x, y: x + y)
```



### 7.文件操作

##### （1）文件编码

```python
# 内容与二进制之间相互转换的逻辑
# UTF-8 应用最为广泛
# GBK
# Big5 繁体字
```

##### （2）文件的读取

```python
# 打开文件
open(name, mode, encoding)
name: 要打开文件名的字符串（包含路径）
mode:设置打开文件的模式（只读、写入、追加）
	r:只读
    w:写入，若文件存在，则从头开始编辑（删除原有内容）；不存在则创建新文件
    a:追加，若文件存在，则在已有内容后添加；不存在则创建新文件
encoding:编码格式（推荐UTF-8）
```

```python
# 读取文件
.read(num) # 从文件中读取的数据长度，未传入num就读取文件中所有数据
# 程序中调用多次read，下次read从上次read的结尾开始读取
f = open("./测试.txt", "r", encoding="UTF-8")
print(f"读取10个字节的结果：{f.read(10)}")

.readlines() # 按照行的方式将整个文件中的内容一次性读取，返回一个列表，其中每一行的数据为一个元素
lines = f.readlines()
print(lines) # 结果为：['你好\n', '再见\n', 'hello\n', 'bye']

readline() # 只读取一行
line1 = f.readline() # 读取第一行内容
line2 = f.readline() # 读取第二行内容

for # 循环读取
for line in f:
    print(f"每一行的数据是：{line}")
```

```python
# 关闭文件对象,如果文件读取后不关闭，就会被一直占用，不能对文件进行删除、重命名等操作了
.close()
# 在操作完成后自动关闭文件
with open("测试.txt","r") as f:
    f.readlines()
```

##### （3）文件的写入

```python
# write() 内容会暂存在缓存区
f = open("测试.txt", "w", encoding="UTF-8")
f.write("hellow world")
f.flush() # 将内存中积攒的内容，写入到硬盘文件中
f.close() # 内置flush的功能

```

##### （4）文件的追加

```python
# “a”
```

### 8. Python异常、模块、包

##### （1）异常

```python
# 捕获异常
try:
    可能出现错误的代码
except:
    如果出现异常执行的代码
# 捕获指定异常
try:
    print(name)
except NameError as e:
    print('name变量名称未定义错误')
    print(e)
# 捕获多个异常
try:
    print(1 / 0)
except (NameError, ZeroDivisionError) as e:
    print('name变量名称未定义错误 或者 除以0的异常错误')
    print(e)
# 捕获所有异常
try:
    可能出现错误的代码
except Exception as e:
    print("出现异常了")
else:
    print("没有异常")
finally:
    f.close()  
```

```python
# 异常的传递，代码中的异常会逐级传递
def func1():
    print("func1开始执行")
    num = 1/0
    print("func1结束执行")
def func2():
    print("func2开始执行")
    func1()
    print("func2结束执行")
def main():
    try:
        func2()
    except Exception as e:
        print(f"出现异常了，异常的信息是：{e}")
main()
```

##### （2）模块

```python
# 模块是一个python文件，以.py结尾，里面含有类、函数、变量等
# 作用：快速实现某些功能
# 模块导入语法：
[from 模块名] import [模块|类|变量|函数|*][as 别名]
# 1.import 模块名
模块名.功能名()
import time  # ctrl+左击 进入该模块的.py文件
time.sleep(5)  # 睡眠5s
# 2.from 模块名 import 功能名
from time import sleep
# 3.from 模块名 import *   # 导入模块的全部功能
from timt import *
sleep(5)  # 不需要写time.
# 4.import time as t  # 简写模块名称
from time import sleep as sl
```

```python
# 自定义模块导入
写一个符合命名规则的.py文件，里面写入一些函数
在另外一个文件里Import 刚才的模块即可

# 用于在模块内部进行测试用，当调用该模块时不会执行test(1, 2)
if __name__=='__main__':
    test(1, 2)

# 在调用的时候用*，__all__放在模块内部，调用的时候就只能用test_A函数了
__all__ = ['test_A']  # __all__作用于*

```

##### （3）包

![image-20240418215013394](assets/image-20240418215013394.png)

```python
# 自定义包，包是一个文件夹，存放一堆模块
# 文件夹里有__init__.py就是一个包，没有就是一个普通文件节
pycharm里面可以自定义软件包
```

```python
# 安装第三方包（非python官方）
# 在终端输入
pip install 包名称  # 通过网络安装包
pip install numpy -i https://pypi.tuna.tsinghua.edu.cn/simple
```

### 9. 案例开发

##### （1）json数据格式

```python
# json是一种轻量化的数据交互格式，本质上是一个带有特定格式的字符串
# 负责不同编程语言的数据传递和交互
# python转json数据
import json
data = [{"name": "张大山", "age": 13}, {"name": "王大锤", "age": 15}, {"name": "赵小虎", "age": 16}]
json_str = json.dumps(data, ensure_ascii=False)
print(type(json_str))  # 字符串
print(json_str)
# json转python
l = json.loads(json_str)
print(type(l))  # 列表
print(l)
```

##### （2）pyecharts模块

```python
# 做出数据可视化效果图
# 官网： pyecharts.org
# 构建折线图 
from pyecharts.charts import Line
from pyecharts.options import TitleOpts, LegendOpts, ToolboxOpts, VisualMapOpts
# 创建一个折线图对象
line = Line()
# 给折线图对象添加x轴和y轴的数据
line.add_xaxis(["中国", "美国", "英国"])
line.add_yaxis("GDP", [30, 20, 10])
# 设置全局配置项set_global_opts来设置标题、工具箱等
line.set_global_opts(
    title_opts=TitleOpts(title="GDP展示", pos_left="center", pos_bottom="1%"),
    legend_opts=LegendOpts(is_show=True),
    toolbox_opts=ToolboxOpts(is_show=True),
    visualmap_opts=VisualMapOpts(is_show=True)
)
# 通过render方法将代码生成图像
line.render()
```

##### （3）通过json模块对数据进行处理

```python
# json数据转为python字典
data_dict = json.loads(data)
# 取到河南省数据
cities_data = data_dict["areaTree"][0]["children"][3]["children"]
```

##### （4）构建地图

```python
# 从pyecharts.charts导入Map
from pyecharts.charts import Map
map = Map()
map.add("河南省疫情分布图", data_list, "河南") # （标题，数据，地图区域）
```

# 二、进阶版

### 1.类

```python
# 类中成员的定义方法
# 在类中定义成员方法与定义函数基本一致，但仍有细微差别
def 方法名(self, 形参1, ...,形参N):  # self必须写
    方法体
class Student():
    name = None

    def say_hi(self):
        print(f"大家好呀，我是{self.name}，欢迎大家多多关照")
    def say_hi2(self, msg):
        print(f"大家好，我是：{self.name}，{msg}")

stu = Student()
stu.name = "周杰伦"
stu.say_hi()
stu.say_hi2("你干嘛~哎呦")

stu2 = Student()
stu2.name = "林俊杰"
stu2.say_hi()
stu2.say_hi2("姬霓太美")
```

```python
# 类和对象  面向对象编程
对象名 = 类名称()

```

### 2.属性（成员变量）的赋值

```python
# 像函数方法那样，通过传参的形式对属性赋值
# __init__()称为构造方法
# 创建类对象的时候，会自动执行，将传入参数自动传递给__init__方法使用
class Student:
    def __init__(self , name, age, tel):
        self.name = name
        self.age = age
        self.tel = tel
        print("Student创建了一个类对象")
stu = Student("周杰伦", 31, "18800000666")
print(stu.name)
print(stu.age)
print(stu.tel)
```

```python
# 魔术方法 
class Student:
    # __init__魔术方法：构造方法，初始化行为
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # __str__魔术方法：实现类对象转字符串的操作
    def __str__(self):
        return f"Student类对象，name：{self.name}, age：{self.age}"

    # __lt__魔术方法:<或>的比较
    def __lt__(self, other):
        return self.age < other.age

    # __le__魔术方法:<=或>=的比较
    def __le__(self, other):
        return self.age <= other.age

    # __eq__魔术方法：是否相等的比较
    def __eq__(self, other):
        return self.age == other.age

stu1 = Student("周杰伦", 31)
stu2 = Student("林俊杰", 36)
print(stu1 < stu2)
print(stu1 >= stu2)
print(stu1 == stu2)
```

### 3.封装

```python
# 将现实世界事物的属性，行为封装到类中，描述为：成员变量、成员方法
# 私有变量和方法在外部无法使用，类对象无法访问私有成员
# 定义一个类，内含私有成员变量和私有成员方法
class Phone:  
    __current_voltage = 0.5  # 当前手机运行电压，以__来定义私有成员

    def __kep_single_core(self):
        print("让CPU以单核模式运行")

    def all_by_5g(self):
        if self.__current_voltage >= 1:
            print("5g通话已开启")
        else:
            self.__kep_single_core()  # 以__来定义私有成员
            print("电量不足，无法使用5G通话，并已设置为单核模式进行省电。")
phone = Phone()
phone.all_by_5g()
```

### 4.继承

```python
# 继承是指一个类（子类）继承另外一个类（父类）的所有属性
# 分为单继承和多继承
# 单继承
class Phone:
    IMEI = None
    producer = "HM"

    def call_by_4g(self):
        print("4G通话")
        
class Phone2(Phone):
    face_id = "10001"

    def call_by_5g(self):
        print("2022年新功能：5G通话")
        
phone = Phone2()
print(phone.producer)

# 多继承
class NFCCReader:
    nfc_type = "第五代"
    producer = "HM"

    def read_card(self):
        print("NFC读卡器")

    def write_card(self):
        print("NFC写卡")

class RemoteCont:
    rc_type = "红外遥控"

    def control(self):
        print("红外遥控开启了")

class MyPhone(Phone, NFCCReader, RemoteCont):  # 多个父类
    pass  # 补全语法，表示空

# 当输出同名的成员属性时，优先输出左边子类的成员属性
phone = MyPhone()
phone.call_by_4g()
phone.read_card()
phone.write_card()
phone.control()
```

```python
# 复写：子类在继承父类的成员属性和方法之后，如果对其不满意可以进行复写

```

##### （5）类型注解

```python
# 类型注解：在代码中涉及数据交互的地方，提供数据类型的注解（显示的说明）
# 帮助第三方IDE工具对代码进行类型推断，协助做代码提示，帮助开发者自身对变量进行类型注解
# 变量的类型注解
变量：类型
var_1: int =10
class Student:
    pass
stu: Student = Student()
my_list: list = [1, 2, 3]

# 在注释中进行类型注解
var_1 = random.randint(1, 10)  # type: int

var_2: dict = json.loads(data)
var_3: Student = func()
```

```python
# 函数（方法）的类型注解
# 对形参进行类型注解
def add(x: int, y: int):
    return x + y
add()

# 对返回值进行类型注解
def func(data: list) -> list:
    return data
func([1, 2])
```

```python
# union类型注解
from typing import Union

my_list: list[Union[int, str]] = [1, 2, "heima"]
my_dict: dict[str,Union[int, str]] = {"heiam": 666, "IT": "hello"}
def func(data: Union[int, str]) -> Union[int, str]:
    pass
```

##### （6）多态

```python
# 多态：多种状态。完成某个行为时，使用不同的对象会得到不同的状态
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        print("汪汪汪")

class Cat(Animal):
    def speak(self):
        print("喵喵喵")

def make_noise(animal: Animal):
    animal.speak()

dog = Dog()
cat = Cat()
make_noise(dog)
make_noise(cat)

# 抽象类（接口）
# 父类用来确定有哪些方法；具体的方法实现由子类自行决定
# 抽象类相当于定义一个标准，包含了一些抽象的方法，要求子类必须实现
class AC:
    def cool_wind(self):
        pass

    def hot_wind(self):
        pass

    def swing_l_r(self):
        pass

class Midea_AC(AC):
    def cool_wind(self):
        print("美的空调制冷")

    def hot_wind(self):
        print("美的空调制热")

    def swing_l_r(self):
        print("美的空调左右摆凤")

class GREE_AC(AC):
    def cool_wind(self):
        print("格力空调制冷")

    def hot_wind(self):
        print("格力空调制热")

    def swing_l_r(self):
        print("格力空调左右摆凤")

def make_cool(ac: AC):
    ac.cool_wind()

midea_ac = Midea_AC()
gree_ac = GREE_AC()

make_cool(midea_ac)
make_cool(gree_ac)
```

### 2.SQL

##### （1）基础知识

```python
# 数据库： 数据存储的库，作用是组织数据并存储数据
# 数据库按照：库 -> 表 -> 数据 三个层次进行组织
# 常见的数据库软件有：Oracle、MySQL、PostgreSQL、SQLite，本课程以MyAQL软件为基础进行学习
# 数据库提供数据存储的能力，SQL语言是操作数据、数据库的工具语言
https://dev.mysql.com/downloads/
```

##### （2）SQL语言

```python
# 进入MySQL
mysql -uroot -p
# 展示所有数据库
show databases;
# 使用world数据库
use world;
# 查看world数据库中的表
show tables;
# 退出MySQL命令行环境
exit
```

```python
# 图形化工具操作软件-->DBeaver
https://dbeaver.io/download/
```

```python
# SQL语言分类
数据定义:DDL
数据操纵:DML  # 对数据库中表的数据记录进行更新
数据控制:DCL
数据查询:DQL
```

```python
# 语言特征
1.大小写不敏感
2.以;结尾
3.支持注释  
# 单行注释
SHOW datasets;
-- 我是注释
# 我是注释
# 多行注释
/*
我是注释
*/
```

##### （3）DDL 库管理

```sql
# 查看数据库
show databases;
# 使用数据库
use 数据库名称;
# 创建数据库
create database 数据库名称 [charset utf8]
# 删除数据库
drop database 数据库名称;
# 从查看当前使用的数据库
select database();
```

##### （4）DDL表管理

```sql
# 查看有哪些表
show tables;
# 创建表 
create table student(
	id int,            # 列名称 列类型  # int, float
	name varchar(10),  # varchar（长度） # 字符串
	age int            # data 日期类型    timestamp 时间戳类型
);
# 删除表
drop table student;
```

##### （5）DML

```sql
# 插入数据
insert into student(id) values(1), (2), (3);

insert into student(id, name, age) values(4, '周杰伦', 31), (5, '林俊杰', 35); # sql只支持''
```

```sql
# 删除数据
delete from 表名称 [where 条件判断]
delete from student where id = 1;
delete from student  # 删除student中所有内容
```

```sql
# 数据更新
update 表名 set 列=值 [where 条件判断]
update student set name = '张学友' where id = 4;
update student set name = '王力宏'  # name全变为 王力宏
```

##### （6）DQL

```sql
# 基础数据查询
select 字段列表 |* from 表 where 条件判断
select id, name, age, gender from student;
select * from student; # 查询所有信息
select * from student where age > 31;
```

```sql
# 分组聚合
select 字段 | 聚合函数 from 表 [where 条件] group by 列
聚合函数有：
- sum(列)  求和
- avg(列)  求平均值
- min(列)  求最小值
- max(列)  求最大值
- count(列|*)  求数量
# 按照性别进行分类并进行统计，执行多个聚合
# group by # 进行分组， group by 中出现了哪个列，哪个列才能出现在select中的非聚合中
select gender, avg(age), sum(age), min(age), max(age), count(age) from student group by gender;
```

```sql
# 排序分页，顺序不能颠倒
# 结果排序
select 列|聚合函数|* from 表 where ... group by ...
order by ... [asc | desc] # asc升序， desc降序
select * from student where age > 20 order by age asc;

# 结果的分页限制
select age, count(*)  from student where age > 20 group by age order by age limit 3; # 取前3条
limit 10， 5 # 表示从第11条开始取5条数据
```


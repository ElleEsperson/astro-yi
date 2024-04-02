---
title: PYTHON笔记
date: 2023-11-10 20:12:52
category: 编程学习

description: PYTHON基础语法学习记录
---

## 一、基础语法

### 1.基础数学函数

```python
from math import *
#withNumber
num=-6
print(num)
print(floor(6,2))#floor函数：剪切掉小数点后的数字
print(ceil(3.3))#ceil函数：直接直接进位
print(sqrt(36))#sqrt函数：求平方根
```

### 2.用户输入

```python
name = input("Enter your name: ")
age = input("Enter your age ")
print("Hello" + name + "! You are " + age)

#SetupCal
num1=input("Enter your first numer")
num2=input("Enter your second numer")
result=float(num1) + float(num2)#float:将其转换成浮点数
print(result)

#填空游戏
color = input("Enter a color: ")
plural_noun = input("Enter a Plural_noun")
celebrity = input("Enter a celebrity: ")

print("Roses are " + color)
print(plural_noun + " are blue ")
print(" I love " + celebrity )
```

### 3.列表

```python
friends = ["Tom", "Sam", "Joey", "Jim", "Wu"]

print(friends[1])#读取小标为1的数据
print(friends[1:])#从下标为1的数据开始读取
print(friends[1:4])#从下标为1的数据读取到下标为4的数据但不包括4

#列表的功能
friends = ["Tom", "Sam", "Joey", "Jim", "Wu"]
luck_numbers = [4, 6, 2, 4, 8]
#print(friends[1])
#print(friends[1:])
#print(friends[1:4])
#friends.extend(luck_numbers)
friends.append("Creed")#添加单个数据
friends.insert(2,"Aili")#在第三个位置插入数据
friends.remove("Jim")#删除指定内容
#friends.clear()
friends.pop()#删掉最后一个数据
print(friends)
print(friends.index("Wu"))#输出指定元素下标
print(friends.count("Tom"))#输出指定元素的数量
friends.sort()#对元素进行升序排序
print(friends)
luck_numbers.reverse()#将数据颠倒输出
print(luck_numbers)

friends2 = friends.copy()#复制数据
print(friends2)
```

### 4.元组

```python
coordinates = (4,6,2,7)#元组
coordinates[1] = 10#错误无法更改数据
print(coordinates[1])
```

#### 4.1二者之间的区别

Python中的列表和元组都是用来存储一组数据的数据类型，但它们有以下区别：

1. 列表是可变的，元组是不可变的。也就是说，列表中的元素可以被修改、添加或删除，而元组中的元素不能被修改。
2. 列表使用方括号 [] 来表示，元组使用圆括号 () 来表示。
3. 列表通常用于存储同类型的数据，而元组通常用于存储异构的数据。
4. 列表的操作速度比元组慢，因为列表需要动态分配内存，而元组在创建后就不可修改，因此可以更快地访问。
5. 列表可以作为函数的参数传递，而元组通常用于函数的返回值。

总之，列表和元组都有各自的优缺点，应根据具体情况选择使用哪种数据类型。

### 5.语法结构

#### 5.1条件语句

```python
is_male = True
is_tall = False
if is_male and is_tall:#两者都为真
    print("You are a male or tall or both")
elif is_male and not(is_tall):#前为真，后为假
    print("You are a short male")
elif not (is_male) and  is_tall:#前为假后为真
    print("You  are not a male but are tall")
else:#both is false
    print("You neither male nor tall")
```

#### 5.2比较语句

```python
def max_num(num1,num2,num3):
    if num1 >= num2 and num1 >=num3:
        return num1
    elif num2 >= num1 and num2 >= num3:
        return num2
    else:return num3

print(max_num(3,49,5))
```

#### 5.3建立计算器

```python
#从用户处输入数据
num1 = float(input("Enter first number: "))
op = input("Enter operator: ")#根据输入符号判断进行的运算
num2 = float(input("Enter second number: "))

if op == "+ ":
    print(num1 + num2)
elif op =="-":
    print(num1 - num2)
elif op == "/":
    print(num1/num2)
elif op == "*":
    print(num1 * num2)
else:
    print("Invalid operator")
```

#### 5.4while循环

```python
i = 1
while i <= 10:
    print(i)
    i +=1
    
print("Done with loop")
```

#### 5.5猜字游戏

```python
secret_word = "giraffe"
guess = ""
guess_count = 0
guess_limit = 3
out_of_guesses = False
while guess != secret_word and not(out_of_guesses):
    if guess_count < guess_limit:
        guess = input("Enter your guess: ")
        guess_count +=1
    else:
        out_of_guesses = True
if out_of_guesses:
    print("Out of Guesses, YOU LOSE")
else:
    print("You win!")
```

### 6.建立字典

```python
monthConversions = 
{
"Jan": "January",
"Feb": "February",
"Mar": "March",
}

print(monthConversions["Mar"])
#print(monthConversions.get("Mar"))
```

通过Mar关键字打印出March

### 7.列表与嵌套循环

```python
number_grid = [
[1,2,3],
[4,5,6],
[7,8,9],
[0]
]

#print(number_grid[0][2])

#for row in number_grid:
 #   print(row)

for row in number_grid:
    for col in row:
        print(col)
```

### 8.捕捉错误

```python
try:
    #Value = 10/0
    number = int(input("Enter a number: "))
    print(number)
except ZeroDivisionError:
    print("Divided by zero")#错误输入
except ValueError:
    print("invalid input")

```



## 二、函数

### 1.函数基本声明调用

```python
def say_Hi(name):
    {
        print("Hello User" + name)
    }

print("Top")
say_Hi(" Tom")
print("Buttom")
```

### 2.return语句

```python
def cube(num):
   return num*num*num
result = cube(4)
print(result)
```

### 3.指数函数

```python
    def raise_to_power(base_num, pow_num):
        result = 1
        for index in range(pow_num):
            result = result * base_num
            return result

        print(raise_to_power(2,4))


```

### 4.建立翻译

```python
def translate(phrase):#读入phrase字符串
    translate = ""
    for letter in phrase:
        if letter.lower() in "aeiou":
            if letter.isupper():#判断大小写
                translate = translate + "G"
            else:
                translate = translate + "g"
        else:  
            translate = translate + letter
    return translate


print(translate(input("Enter a phrase: ")))
```

### 5.模块

#### 5.1被调用模块

useful_tools

```python
def get_file_ext(filename):
    return filename[filename[filename.index(".") + 1]]

def putnum(num):
    return num+10
#对输入进来的数进行加十操作		
```

#### 5.2调用

```python
import useful_tools#调用useful_tools模块

#print(useful_tools.get_file_ext("bsjfsa"))
print(useful_tools.putnum(10))
```

## 三、文件操作

### 1.读文件

```python
employee_file = open("pythonProject\\测试.txt", "r")

'''
print(employee_file.read())#读全部文件
print(employee_file.readline())#读一行
'''

print(employee_file.readlines())#分成数组读出
employee_file.close()
```

### 2.写文件

```python
employee_file = open("pythonProject\\测试2.txt", "w")

employee_file.write("\nTobe,a man")
employee_file.close()
```

## 四、类与对象

### 1.创建类

```python
class Student:
    def __init__(self, name, major, gpa, is_on_probation):
        self.name = name
        self.major = major
        self.gpa = gpa
        self.is_on_probation = is_on_probation
#__init__是python指定的构造函数写法，self类似于c 中的this指针
```

调用类创建对象

```python
from Student import Student

student1 = Student("Jim", "Business", 4.1, False)
student2 = Student("Pam", "Art", 4.5, True)
print(student2.gpa)
print(student1.is_on_probation)
```

### 2.继承

父类

```python
class Chef:

    def make_chicken(self):
        print("Te chef makes a chicken")

    def make_salad(self):
        print("The chef makes a salad")
    
    def make_special_dish(self):
        print("The chef make a special_dish")
```

子类

```python
from Chef import Chef

class ChineseChef(Chef):
  
    def make_fried_rice(self):
        print("The chef mkes fried rice")

    def make_special_dish(self):
        print("The chef makes orange chicken")
```

调用

```python
from Chef import Chef
from ChineseChef import ChineseChef

myChef = Chef()
myChef.make_special_dish()

myChineseChef = ChineseChef()
myChineseChef.make_chicken()
myChineseChef.make_special_dish()
```












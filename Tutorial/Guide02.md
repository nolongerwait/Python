# 学习Python的第二天

任务:  
- 掌握变量的概念和Python中的基础数据类型
    - 了解静态语言和动态语言的数据类型的差别(口述后补充)
- 掌握操作符的类型和功能
    - 掌握变量和操作符的操作关系

## 数据类型
在数学中，我们把数字分为多种类型，整数，小数等。  

与之对应的，计算机中的所有数据，都有对应的分类。而在Python动态语言中，基础数据类型有**整形**，**浮点数**，**字符(字符串)**,**布尔类型**和**空值**。

### 整形(integer)
Python可以处理任意大小的整数，无论正负。在正负数的表示上，和数学表示一致。例如在Python中的整数可以有`1`, `100`, `-999`, `0`等等。  

当然，在计算机中，有时候更多会看见用十六进制来表示一系列数。十六进制的表示则是通过`0x`前缀加上十六进制表达法来表示的。例如`0x000`, `0x9abc`, `0x1234`

### 浮点数(小数)
浮点数，在通常认知上，我们可以将浮点数理解为数学意义上的小数。至于为何称之为“浮点数”，这涉及数据在计算机中的存储方式，需等我起床后讲解。  

浮点数可以用数学写法，如`1.23`，`3.14`，`-9.01`等等。  

但是对于很大或很小的浮点数，就必须用科学计数法表示，把10用e替代，1.23x109就是`1.23e9`，或者`12.3e8`，0.000012可以写成`1.2e-5`等等。

### 字符和字符串（char & string）

字符串是以单引号`'`或双引号`"`括起来的任意文本，比如`'abc'`，`"xyz"`等等。请注意，`''`或`""`本身只是一种表示方式，不是字符串的一部分，因此，字符串`'abc'`只有`a`，`b`，`c`这3个字符。如果`'`本身也是一个字符，那就可以用`""`括起来，比如`"I'm OK"`包含的字符是`I`，`'`，`m`，` `(空格)，`O`，`K`这6个字符。

如果字符串内部包含`"`怎么办？可以用转义字符`\`来标识，比如：
`"\"Mr. Lee\", she said"`在Python中表示的是`"Mr. Lee", she said`。

#### 转义字符

### 布尔类型(bool)

布尔值和布尔代数的表示完全一致，一个布尔值只有True、False两种值，要么是True，要么是False，在Python中，可以直接用True、False表示布尔值（请注意大小写），也可以通过布尔运算计算出来。

布尔类型存在的功能: 在一个处理流程中，我们通过***条件语句***来进行分支，条件为真时走一条处理分支，条件为假时走另一条处理分支。

#### 布尔运算 “与” “或” “非”
`and`运算是**与运算**，只有所有都为True，`and`运算结果才是True:  
```
>>> True and True
True
>>> True and False
False
>>> False and False
False
>>> 5 > 3 and 3 > 1
True
```

`or`运算是**或运算**，只要其中有一个为True，`or`运算结果就是True:  
```
>>> True or True
True
>>> True or False
True
>>> False or False
False
>>> 5 > 3 or 1 > 3
True
```

`not`运算是**非运算**，它是一个单目运算符，把True变成False，False变成True:  
```
>>> not True
False
>>> not False
True
>>> not 1 > 2
True
```

### 空值

空值是Python里一个特殊的值，用`None`表示。`None`不能理解为`0`，因为`0`是有数学意义的，而`None`是一个特殊的空值。

### 变量
变量，类似于数学中的概念，是计算机中用于存储和指代某一个内容的抽象性内容。

比如，在矩形周长计算公式中L = 2ab， a, b分别为两个变量，指代矩形的长和宽。a和b可以是任何值。这在Python中也是一样。

在Python中创建一个变量，对变量的名字有一定要求: 
* 变量名必须是大小写英文、数字和`_`的组合，且不能用数字开头。  
例如。`a123`是合法的变量名， `abcD`也是合法的变量名, `_mC`合法。但是`1A`不合法，不能作为变量名。

```python
a = 1  # a is the variable as integer type
t_007 = 'T007' # t_007 is the variable as String type
Answer = True # Answer is the variable as bool type
```
由于Python是动态语言，在基础数据类型的变量定义时没有定义类型，所以在Python中，一个变量课任意赋给不同基础数据类型。
```python
a = 123 # a is integer type
print(a)
a = 'ABC' # a changed to string type
print(a)
```

### 操作符
操作符，是指对一个或者多个变量进行操作的符号。  
例如: `4 + 5` 中，`4`和`5`都是“操作数”，而`+`即为“操作符” 

Python中的操作符有多种类型。

#### 算术运算符

| 运算符 | 描述                                            | 实例                              |
| ------ | ----------------------------------------------- | --------------------------------- |
| +      | 加 - 两个对象相加                               | a + b 输出结果 30                 |
| -      | 减 - 得到负数或是一个数减去另一个数             | a - b 输出结果 -10                |
| *      | 乘 - 两个数相乘或是返回一个被重复若干次的字符串 | a * b 输出结果 200                |
| /      | 除 - x除以y                                     | b / a 输出结果 2                  |
| %      | 取模 - 模运算                                   | b % a 输出结果 0                  |
| **     | 幂 - 返回x的y次幂                               | a**b 为10的5次方， 输出结果 10000 |
| //     | 取整除 - 返回商的整数部分（**向下取整**）       |                                   |

#### 比较运算符

| 运算符 | 描述                            | 实例                  |
| ------ | ------------------------------- | --------------------- |
| ==     | 等于 - 比较对象是否相等         | (a == b) 返回 False。 |
| !=     | 不等于 - 比较两个对象是否不相等 | (a != b) 返回 True.   |
| >      | 大于 - 返回x是否大于y           | (a > b) 返回 False。  |
| <      | 小于 - 返回x是否小于y。         | (a < b) 返回 True。   |
| >=     | 大于等于 - 返回x是否大于等于y。 | (a >= b) 返回 False。 |
| <=     | 小于等于 - 返回x是否小于等于y。 | (a <= b) 返回 True。  |

#### 赋值运算符

| 运算符 | 描述             | 实例                                  |
| ------ | ---------------- | ------------------------------------- |
| =      | 简单的赋值运算符 | c = a + b 将 a + b 的运算结果赋值为 c |
| +=     | 加法赋值运算符   | c += a 等效于 c = c + a               |
| -=     | 减法赋值运算符   | c -= a 等效于 c = c - a               |
| *=     | 乘法赋值运算符   | c *= a 等效于 c = c * a               |
| /=     | 除法赋值运算符   | c /= a 等效于 c = c / a               |
| %=     | 取模赋值运算符   | c %= a 等效于 c = c % a               |
| **=    | 幂赋值运算符     | c ** = a 等效于 c = c ** a            |
| //=    | 取整除赋值运算符 | c //= a 等效于 c = c // a             |

#### 位运算符

| 运算符 | 描述                                                         | 实例                                          |
| ------ | :----------------------------------------------------------- | --------------------------------------------- |
| &      | 按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0 | (a & b) 输出结果 12 ，二进制解释： 0000 1100  |
| \|     | 按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1。 | (a \| b) 输出结果 61 ，二进制解释： 0011 1101 |
| ^      | 按位异或运算符：当两对应的二进位相异时，结果为1              | (a ^ b) 输出结果 49 ，二进制解释： 0011 0001  |
| ~      | 按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1 。~x 类似于 -x-1 |                                               |
| <<     | 左移动运算符：运算数的各二进位全部左移若干位，由 << 右边的数字指定了移动的位数，高位丢弃，低位补0。 | a << 2 输出结果 240 ，二进制解释： 1111 0000  |
| >>     | 右移动运算符：把">>"左边的运算数的各二进位全部右移若干位，>> 右边的数字指定了移动的位数 | a >> 2 输出结果 15 ，二进制解释： 0000 1111   |

#### 逻辑运算符

| 运算符 | 逻辑表达式 | 描述                                                         | 实例                    |
| ------ | ---------- | ------------------------------------------------------------ | ----------------------- |
| and    | x and y    | 布尔"与" - 如果 x 为 False，x and y 返回 False，否则它返回 y 的计算值。 | (a and b) 返回 20。     |
| or     | x or y     | 布尔"或" - 如果 x 是非 0，它返回 x 的值，否则它返回 y 的计算值。 | (a or b) 返回 10。      |
| not    | not x      | 布尔"非" - 如果 x 为 True，返回 False 。如果 x 为 False，它返回 True。 | not(a and b) 返回 False |

#### 成员运算符

| 运算符 | 描述                                                    | 实例                                              |
| ------ | ------------------------------------------------------- | ------------------------------------------------- |
| in     | 如果在指定的序列中找到值返回 True，否则返回 False。     | x 在 y 序列中 , 如果 x 在 y 序列中返回 True。     |
| not in | 如果在指定的序列中没有找到值返回 True，否则返回 False。 | x 不在 y 序列中 , 如果 x 不在 y 序列中返回 True。 |

#### 身份运算符

身份运算符用于比较两个对象的存储单元

| 运算符 | 描述                                        | 实例                                                         |
| ------ | ------------------------------------------- | ------------------------------------------------------------ |
| is     | is 是判断两个标识符是不是引用自一个对象     | **x is y**, 类似 **id(x) == id(y)** , 如果引用的是同一个对象则返回 True，否则返回 False |
| is not | is not 是判断两个标识符是不是引用自不同对象 | **x is not y** ， 类似 **id(a) != id(b)**。如果引用的不是同一个对象则返回结果 True，否则返回 False。 |

#### Python运算符优先级

指数运算 > 按位反转运算 > 乘，除，取模和取整除运算 > 加，减运算 > 右移和左移运算 > 位运算符 > 比较运算符 > 等于不等于运算符 > 赋值运算 > 身份运算 > 成员运算 > 逻辑运算 
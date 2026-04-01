# 第2章 Java编程基础
> 《Java基础案例教程》（第3版）
---

## 章节概述

通过学习第一章，大家已经对Java有了基本认识。然而，要能够熟练使用Java编写程序，需要充分掌握Java的基础知识，并不断进行练习和实践。本章将对Java的基本语法、变量与常量、运算符、结构语句、数组和方法等知识进行详细讲解。

## 目录

- 2.1 Java基本语法
- 2.2 变量
- 2.3 数据类型转换
- 2.4 Java中的运算符
- 2.5 选择结构语句
- 2.6 循环结构语句
- 2.7 数组
- 2.8 方法

---

## 2.1 Java基本语法

每一种编程语言都有一套自己的语法规则，同样，使用Java编写程序也必须遵循一定的语法规范。

### 2.1.1 Java程序的基本结构

一个典型的Java程序包括**包声明**、**导入类**、**定义类**、**入口方法**和**主体代码**等多个组成部分。

**示例代码：**
```java
package cn.itcast.myapp;   // 包声明
import java.util.Scanner;  // 导入类

public class MyApp {        // 定义类
    public static void main(String[] args) {  // 入口方法
        // 主体代码
        Scanner scanner = new Scanner(System.in);
        System.out.print("请输入您的名字：");
        String name = scanner.nextLine();
        System.out.println("您好，" + name + "!");
    }
}
```

**（1）包声明**
Java中的包是一种组织和管理类文件的机制。包使用关键字`package`声明：
```java
package 包名;
```
- 包的声明只能位于Java源文件的第一行
- Java中的包是可选的

**（2）导入类**
使用`import`关键字导入类：
```java
import 包名.类名;
// 或导入包下所有类
import 包名.*;
```

**（3）定义类**
Java的所有代码都需要在类中书写：
```java
修饰符 class 类名 {
    // 类体
}
```

**（4）入口方法**
入口方法是程序执行的起始位置：
```java
public static void main(String[] args) {
    // 入口方法主体代码
}
```

**（5）Java程序编写注意事项**
- 使用`public`修饰的类名和文件名需要保持一致
- Java严格区分大小写
- 每条语句需要以`;`结束
- 一般使用四个空格作为一个缩进级别

### 2.1.2 Java中的注释

**1. 单行注释**
以符号`//`开头：
```java
int x = 5;  // 定义一个变量
```

**2. 多行注释**
以`/*`开头，以`*/`结尾：
```java
/* 这是多行注释
   用于说明代码功能 */
```

**3. 文档注释**
以`/**`开始，以`*/`结束，用于生成API文档：
```java
/**
 * 入门的HelloWorld程序
 * @author 黑马程序员
 * @since 1.0
 */
```

### 2.1.3 关键字和标识符

**关键字**是编程语言中具有特殊含义和功能的预定单词。

**Java关键字表：**
| 访问控制符 | 修饰符 | 程序控制 | 类型/其他 |
|-----------|--------|---------|----------|
| public | abstract | if | void |
| private | class | else | return |
| protected | extends | for | int |
| - | final | while | double |
| - | static | switch | char |
| - | - | case | boolean |
| - | - | default | null |
| - | - | break | true |
| - | - | continue | false |
| - | - | try | - |
| - | - | catch | - |

**标识符**用于唯一地标识程序的各种元素。

**命名规则：**
- 可以由字母、数字、下划线`_`和美元符号`$`组成
- 不能以数字开头
- 区分大小写
- 不能是Java中的关键字

**命名约定：**
- 包名：所有字母小写
- 类名和接口名：每个单词首字母大写（PascalCase）
- 常量名：所有字母大写，单词用下划线连接
- 变量名和方法名：首字母小写的驼峰命名法（camelCase）

### 2.1.4 Java的数据类型

Java的数据类型分为**基本数据类型**和**引用数据类型**。

**（1）整数类型**
| 类型 | 存储空间 | 取值范围 |
|------|---------|---------|
| byte | 1字节 | -2⁷ ~ 2⁷-1 |
| short | 2字节 | -2¹⁵ ~ 2¹⁵-1 |
| int | 4字节 | -2³¹ ~ 2³¹-1 |
| long | 8字节 | -2⁶³ ~ 2⁶³-1 |

**整数的表示形式：**
- 二进制（Java 7+）：`0b101`或`0B101`
- 八进制：`0342`
- 十进制：`198`
- 十六进制：`0x25AF`

**（2）浮点数类型**
| 类型 | 存储空间 | 取值范围 |
|------|---------|---------|
| float | 4字节 | 约 -3.4E+38 ~ 3.4E+38 |
| double | 8字节 | 约 -1.7E+308 ~ 1.7E+308 |

**（3）字符类型**
用`char`表示单个字符，需要用单引号引起来：
- 单个字符：`'a'`
- 转义字符：`'\n'`、`'\t'`
- Unicode：`'\u0000'`

**（4）布尔类型**
使用`boolean`表示，只有`true`和`false`两个值。

**Java 10 新特性：var关键字**
`var`关键字允许省略类型声明，编译器会自动推断类型。

---

## 2.2 变量

变量是用于标识内存单元的标识符，内存单元中存储的数据即为变量的值。

**1. 变量的声明**
```java
数据类型 变量名[, 变量名2 ...];
```

**2. 变量的定义**
```java
数据类型 变量名 = 初始值;
int x = 25;
int y = x;
```

**3. 变量的作用域**
变量的作用域由变量声明时所在的大括号`{}`决定。

---

## 2.3 数据类型转换

### 2.3.1 自动类型转换

在不同数据类型之间进行操作或赋值时，编译器会自动完成类型转换。

**条件：**
- 两种数据类型彼此兼容
- 目标类型的取值范围大于源类型

```java
byte a = 10;
int b = a;  // 自动类型转换
```

### 2.3.2 强制类型转换

将取值范围大的数据类型转换为取值范围小的数据类型：
```java
int a = 10;
byte b = (byte) a;  // 强制类型转换
```

**注意：**
- 可能会导致数据精度丢失
- 浮点数转换为整数时，会直接截断小数部分

---

## 2.4 Java中的运算符

### 算术运算符
| 运算符 | 名称 | 示例 |
|-------|------|------|
| + | 加法 | a + b |
| - | 减法 | a - b |
| * | 乘法 | a * b |
| / | 除法 | a / b |
| % | 取模 | a % b |
| ++ | 自增 | a++ 或 ++a |
| -- | 自减 | a-- 或 --a |

### 赋值运算符
| 运算符 | 说明 |
|-------|------|
| = | 简单赋值 |
| += | 加后赋值 |
| -= | 减后赋值 |
| *= | 乘后赋值 |
| /= | 除后赋值 |
| %= | 取模后赋值 |

### 比较运算符
| 运算符 | 说明 |
|-------|------|
| == | 等于 |
| != | 不等于 |
| > | 大于 |
| < | 小于 |
| >= | 大于等于 |
| <= | 小于等于 |

### 逻辑运算符
| 运算符 | 名称 | 说明 |
|-------|------|------|
| && | 短路与 | 两个都为true才返回true |
| \|\| | 短路或 | 两个都为false才返回false |
| ! | 逻辑非 | 取反 |

### 三元运算符
```java
条件表达式 ? 值1 : 值2
int max = (a > b) ? a : b;
```

---

## 2.5 选择结构语句

### if语句

**1. if语句**
```java
if (条件) {
    // 条件为true时执行的代码
}
```

**2. if-else语句**
```java
if (条件) {
    // 条件为true时执行的代码
} else {
    // 条件为false时执行的代码
}
```

**3. if-else if-else语句**
```java
if (条件1) {
    // 条件1为true时执行的代码
} else if (条件2) {
    // 条件2为true时执行的代码
} else {
    // 所有条件都不满足时执行的代码
}
```

### switch语句

```java
switch (表达式) {
    case 值1:
        // 表达式等于值1时执行的代码
        break;
    case 值2:
        // 表达式等于值2时执行的代码
        break;
    default:
        // 所有case都不匹配时执行的代码
        break;
}
```

**注意：**
- 表达式类型可以是：byte、short、int、char、enum、String（Java 7+）
- 每个case后面要加break语句

---

## 2.6 循环结构语句

### while循环
```java
while (条件) {
    // 循环体
}
```

先判断条件，条件为false时可能一次都不执行。

### do...while循环
```java
do {
    // 循环体
} while (条件);
```

先执行一次循环体，然后再判断条件，至少会执行一次。

### for循环
```java
for (初始化表达式; 条件表达式; 更新表达式) {
    // 循环体
}
```

**执行顺序：**
1. 执行初始化表达式
2. 判断条件表达式
3. 如果条件为true，执行循环体
4. 执行更新表达式
5. 重复步骤2-4，直到条件为false

### 循环嵌套
在一个循环的循环体中再包含另一个循环。

### 跳转语句
**break语句**：跳出当前循环或switch语句。
**continue语句**：跳过本次循环，继续执行下一次循环。
**标签（Label）**：为循环设置标签，用于跳出指定层次的循环。
```java
outer: for (int i = 0; i < 10; i++) {
    for (int j = 0; j < 10; j++) {
        if (j == 5) {
            break outer;  // 跳出外层循环
        }
    }
}
```

---

## 2.7 数组

数组是用来存储一组相同类型数据的集合。数组中的每个元素可以通过索引来访问，索引从0开始。

### 数组的声明
```java
数据类型[] 数组名;
// 或者
数据类型 数组名[];
```

### 数组的初始化
**1. 静态初始化**
```java
int[] numbers = {1, 2, 3, 4, 5};
```

**2. 动态初始化**
```java
int[] numbers = new int[5];  // 创建一个长度为5的整型数组
```

动态初始化的数组元素会有默认值：
- 整数类型：0
- 浮点数类型：0.0
- 布尔类型：false
- 引用类型：null

### 数组元素的访问和赋值
```java
int[] numbers = new int[3];
numbers[0] = 10;     // 为第一个元素赋值
int first = numbers[0];  // 访问第一个元素
```

### 数组的遍历
**1. 使用普通for循环**
```java
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

**2. 使用增强for循环（foreach）**
```java
for (int num : numbers) {
    System.out.println(num);
}
```

### 数组的排序
使用`Arrays`类的`sort()`方法对数组进行排序：
```java
import java.util.Arrays;

int[] numbers = {5, 3, 1, 4, 2};
Arrays.sort(numbers);  // 排序后数组变为 {1, 2, 3, 4, 5}
```

### 获取数组的最值
```java
int max = numbers[0];
int min = numbers[0];

for (int i = 1; i < numbers.length; i++) {
    if (numbers[i] > max) {
        max = numbers[i];
    }
    if (numbers[i] < min) {
        min = numbers[i];
    }
}
```

### 二维数组
二维数组是数组的数组。

**1. 静态初始化**
```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

**2. 动态初始化**
```java
int[][] matrix = new int[3][4];  // 3行4列的二维数组
```

**3. 二维数组的遍历**
```java
for (int i = 0; i < matrix.length; i++) {
    for (int j = 0; j < matrix[i].length; j++) {
        System.out.print(matrix[i][j] + " ");
    }
    System.out.println();
}
```

---

## 2.8 方法

方法（Method）是用于完成特定功能的代码块，可以被重复调用。

### 方法的定义
```java
修饰符 返回类型 方法名(参数列表) {
    // 方法体
}
```

**说明：**
- 修饰符：控制方法的访问权限和其他特性
- 返回类型：方法执行完毕后返回的数据类型，如果没有返回值则使用`void`
- 参数列表：方法可以接收的输入参数

**示例：**
```java
public static int add(int a, int b) {
    return a + b;
}

public static void printMessage(String message) {
    System.out.println(message);
}
```

### 方法的调用
```java
方法名(参数);
```

### 方法的重载
方法的重载（Overload）是指在同一个类中，可以定义多个同名的方法，但它们的参数列表不同。

**构成重载的条件：**
- 参数个数不同
- 参数类型不同
- 参数顺序不同

**示例：**
```java
public static int add(int a, int b) {
    return a + b;
}

public static double add(double a, double b) {
    return a + b;
}

public static int add(int a, int b, int c) {
    return a + b + c;
}
```

**注意：**
- 方法重载与返回类型无关
- 方法重载与参数名称无关，只与参数列表有关

### 可变参数
JDK 5引入了可变参数（Varargs）功能，允许方法接受可变数量的参数。
```java
public static int sum(int... numbers) {
    int total = 0;
    for (int num : numbers) {
        total += num;
    }
    return total;
}

// 调用
int result = sum(1, 2, 3, 4, 5);  // 返回15
```

**注意：**
- 可变参数必须放在参数列表的最后
- 可变参数在方法内部被当作数组处理


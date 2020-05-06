---
show: step
version: 1.0
enable_checker: true
---

# JavaScript 语句

## JavaScript语句

JavaScript语句由以下内容组成：

值，运算符，表达式，关键字和注释。

该语句告诉浏览器在`id="demo"`的HTML元素中写`"Hello Dolly"`：

```javascript
document.getElementById("demo").innerHTML = "Hello Dolly.";
```

大多数JavaScript程序包含许多JavaScript语句。

语句以与编写语句相同的顺序一一执行。

### 分号 (`;`)

分号分隔JavaScript语句。

在每个可执行语句的末尾添加分号：

```javascript
var a, b, c;     // Declare 3 variables
a = 5;           // Assign the value 5 to a
b = 6;           // Assign the value 6 to b
c = a + b;       // Assign the sum of a and b to c
```

当用分号分隔时，允许在一行上使用多个语句：

```javascript
a = 5; b = 6; c = a + b;
```

>在网上，您可能会看到没有分号的示例。
>语句以分号结尾不是必须的，但是强烈建议使用。

###  空格

JavaScript会忽略多个空格。可以在脚本中添加空格以使其更具可读性。

以下几行是等效的：

```javascript
var person = "Hege";
var person="Hege";
```

建议在操作符（`=` `+` `-` `*` `/`）前后放置空格。

```javascript
var x = y + z;
```

### 代码行长度和换行

为了获得最佳可读性，程序员通常喜欢避免使用超过80个字符的代码行。

如果JavaScript语句不适合放在一行，则打破它的最佳位置是在运算符之后：

```javascript
document.getElementById("demo").innerHTML =
"Hello Dolly!";
```

### JavaScript代码块

JavaScript语句可以组合成代码块，放在大括号（`{}`）中。

代码块的目的是定义要一起执行的语句。

在JavaScript函数中，可以找到以块分组在一起的语句的一个地方是：

```javascript
function myFunction() {
  document.getElementById("demo1").innerHTML = "Hello Dolly!";
  document.getElementById("demo2").innerHTML = "How are you?";
}
```
### JavaScript关键词


| 关键词        	| 描述                                         	|
|---------------	|----------------------------------------------	|
| break         	| 中断switch语句或循环                         	|
| continue      	| 跳出当前循环，回到循环起点                   	|
| debugger      	| 停止执行JavaScript，并调用调试功能（如果有） 	|
| do ... while  	| 当条件为真时，执行语句块并重复执行该块       	|
| for           	| 只要条件为真，就标记要执行的语句块           	|
| function      	| 声明一个功能                                 	|
| if ... else   	| 根据条件标记要执行的语句块                   	|
| return        	| 退出方法                                     	|
| switch        	| 根据不同的情况标记要执行的语句块             	|
| try ... catch 	| 对语句块实施错误处理                         	|
| var           	| 声明一个变量                                 	|

> JavaScript关键词是保留字，不能用作变量名。












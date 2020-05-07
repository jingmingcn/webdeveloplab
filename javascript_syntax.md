---
show: step
version: 1.0
enable_checker: true
---

# JavaScript语法

## 语法

示例：

```javascript
var x, y, z;       // How to declare variables
x = 5; y = 6;      // How to assign values
z = x + y;         // How to compute values
```

### javascript 值

JavaScript语法定义了两种类型的值：固定值和变量值。

固定值称为文字（`literals`）。 变量值称为变量(`variables`)。

**javascript文字**

编写固定值的最重要规则是：

- `Numbers`可以有或没有小数位：`10.50 1001`
- 字符串用文本表示，可以放在单引号(`'`)或双引号(`"`)中间. `"John Doe"` `'John Doe'`


**javascript变量**

javascript`变量`用来保存数据值，javascript使用`var`声明变量，使用等号`=`给变量赋值。以下的例子中，`x`定义为变量，然后赋值`6`。

```javascript
var x;
x = 6;
```

### javascript运算符

javascript使用算法运算符（`+` `-` `*` `/`）计算数值。使用以下代码，实验算法运算符的用法。

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Operators</h2>

<p>JavaScript uses arithmetic operators to compute values (just like algebra).</p>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = (5 + 6) * 10;
</script>

</body>
</html>
```

### javascript注释

并不是所有javascript语句都能被执行，放在双斜线(`//`)后面或者(`/* */`)中间的语句被定义为注释。注释会被忽略，不会被执行。

```javascript
var x = 5;   // I will be executed

// var x = 6;   I will NOT be executed
```

### javascript标识符

标识符是命名。

在JavaScript中，标识符用于命名变量（以及关键字，函数和标签）。

在大多数编程语言中，命名的规则几乎相同。

在JavaScript中，第一个字符必须是字母，下划线（`_`）或美元符号（`$`）。

后续字符可以是字母，数字，下划线或美元符号。


> 不允许数字作为第一个字符。
> 这样，JavaScript可以轻松区分标识符和数值。

### javascript是大小写敏感的

所有javascript标识符都是大小写敏感的，比如：`lastName`和`lastname`是不同的标识符。

```javascript
var lastname, lastName;
lastName = "Doe";
lastname = "Peterson";
```




























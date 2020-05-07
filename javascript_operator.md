---
show: step
version: 1.0
enable_checker: true
---

# JavaScript运算符

## JavaScript算术运算符

算术运算符对数值进行算术运算(文字或变量)

示例:

```html
<!DOCTYPE html>
<html>
<body>

<p>A typical arithmetic operation takes two numbers and produces a new number.</p>

<p id="demo"></p>

<script>
var x = 100 + 50;
document.getElementById("demo").innerHTML = x;
</script>

</body>
</html>
```

## JavaScript运算符优先级

实验以下运算符，了解各个运算符的运算规则和优先级。

| 优先级	| 运算符	| 描述 |	示例 |
|---|---|---|---|
|20	|( )|	Expression grouping	|(3 + 4)|
|||||
|19	|.	|Member	|person.name|
|19	|[]	|Member	|person["name"]|
|19	|()	|Function call	|myFunction()
|19	|new	|Create	|new Date()
||||| 
|17	|++	|Postfix Increment	|i++
|17	|--	|Postfix Decrement	|i--
|||||
|16	|++	|Prefix Increment	|++i
|16	|--	|Prefix Decrement	|--i
|16	|!	|Logical not	|!(x==y)
|16	|typeof	|Type	|typeof x
|||||
|15	|`**`	|Exponentiation (ES2016)	|`10 ** 2`
|||||
|14	|*	|Multiplication	|10 * 5
|14	|/	|Division	|10 / 5
|14	|%	|Division Remainder	|10 % 5
|||||
|13	|+	|Addition	|10 + 5
|13	|-	|Subtraction	|10 - 5
|||||
|12	|<<	|Shift left	|x << 2
|12	|>>	|Shift right	|x >> 2
|12	|>>>	|Shift right (unsigned)	|x >>> 2
|||||
|11	|<	|Less than	|x < y 
|11	|<=	|Less than or equal	|x <= y
|11	|>	|Greater than	|x > y
|11	|>=	|Greater than or equal	|x >= y
|11	|in	|Property in Object	|"PI" in Math
|11	|instanceof	|Instance of Object	|instanceof Array
|||||
|10	|==	|Equal	|x == y
|10	|===	|Strict equal	|x === y
|10	|!=	|Unequal	|x != y
|10	|!==	|Strict unequal	|x !== y
|||||
|9	|&	|Bitwise AND	|x & y
|||||
|8	|^	|Bitwise XOR	|x ^ y
|||||
|7	|\|	|Bitwise OR	|x \| y
|||||
|6	|&&	|Logical AND	|x && y
|||||
|5	|\|\|	|Logical OR	|x \|\| y
|||||
|4	|? :	|Condition	|? "Yes" : "No"
|||||
|3	|+=	|Assignment	|x += y
|3	|/=	|Assignment	|x /= y
|3	|-=	|Assignment	|x -= y
|3	|*=	|Assignment	|x *= y
|3	|%=	|Assignment	|x %= y
|3	|<<=	|Assignment	|x <<= y
|3	|>>=	|Assignment	|x >>= y
|3	|>>>=	|Assignment	|x >>>= y
|3	|&=	|Assignment	|x &= y
|3	|^=	|Assignment	|x ^= y
|3	|\|=	|Assignment	|x \|= y
|||||
|2	|yield	|Pause Function	|yield x
|1	|,	|Comma	|5 , 6















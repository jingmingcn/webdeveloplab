---
show: step
version: 1.0
enable_checker: true
---

# JavaScript基础

## 为什么学习JavaScript?


JavaScript是所有Web开发人员必须学习的三种语言之一：

1. HTML定义网页内容
2. CSS指定网页的布局
3.使用JavaScript编写网页行为

网页不是唯一使用JavaScript的地方。 许多桌面和服务器程序都使用JavaScript, 其中最著名的是Node.js。 一些数据库，例如MongoDB和CouchDB，也使用JavaScript作为其编程语言。

## JavaScript介绍

### 使用JavaScript改变HTML文档内容

使用JavaScript操作HTML的方法之一是：`getElementById()`

以下示例使用该方法“查找” HTML元素（具有`id='demo'`），并将元素内容（`innerHTML`）更改为`“ Hello JavaScript”`：

```html
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p id="demo">JavaScript can change HTML content.</p>

<button type="button" onclick='document.getElementById("demo").innerHTML = "Hello JavaScript!"'>Click Me!</button>

</body>
</html>
```

请实验以上代码，预览操作结果。

### 使用JavaScript改变HTML属性

在此示例中，JavaScript更改了`<img>`标签的`src`（源）属性的值：

![Light Off](https://doc.shiyanlou.com/courses/uid1361580-20200506-1588695886024)

![Light On](https://doc.shiyanlou.com/courses/uid1361580-20200506-1588695871792)

```html
<!DOCTYPE html>
<html>
<body>

<h2>What Can JavaScript Do?</h2>

<p>JavaScript can change HTML attribute values.</p>

<p>In this case JavaScript changes the value of the src (source) attribute of an image.</p>

<button onclick="document.getElementById('myImage').src='pic_bulbon.gif'">Turn on the light</button>

<img id="myImage" src="https://doc.shiyanlou.com/courses/uid1361580-20200506-1588695886024/wm" style="width:100px">

<button onclick="document.getElementById('myImage').src='https://doc.shiyanlou.com/courses/uid1361580-20200506-1588695871792/wm'">Turn off the light</button>

</body>
</html>
```

## JavaScript代码位置和调用

### `<script>`标签

在HTML中，JavaScript代码编写在`<script>`和`</script>`标签中间。

示例：

```html
<script>
document.getElementById("demo").innerHTML = "My First JavaScript";
</script>
```

旧的JavaScript示例可能使用`type`属性：`<script type ="text/javascript">`。
类型属性不是必需的。 JavaScript是HTML中的默认脚本语言。


### JavaScript方法和事件

JavaScript `function` 是JavaScript代码块，可以在被“调用”时执行。

例如，可以在`event`发生时（例如用户单击按钮时）调用函数。

### JavaScript代码放置在`<head>`或`<body>`标签中

可以在HTML文档中放置任意多的JavaScript代码。

JavaScript代码可以放置在HTML页面的`<body>`或`<head>`部分中，或同时放置在这两者中。


#### JavaScript代码放置在`<head>`中

以下示例中，JavaScript代码的`function`放置在HTML页面的`<head>`标签中。

当按钮点击时，调用`function`代码。

```html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction() {
  document.getElementById("demo").innerHTML = "Paragraph changed.";
}
</script>
</head>
<body>

<h1>A Web Page</h1>
<p id="demo">A Paragraph</p>
<button type="button" onclick="myFunction()">Try it</button>

</body>
</html>
```

#### JavaScript代码放置在`<body>`中

示例：

```html
<!DOCTYPE html>
<html>
<body>

<h1>A Web Page</h1>
<p id="demo">A Paragraph</p>
<button type="button" onclick="myFunction()">Try it</button>

<script>
function myFunction() {
 document.getElementById("demo").innerHTML = "Paragraph changed.";
}
</script>

</body>
</html>
```

> 把javascript代码放在`<body>`标签的底部可以改善页面的显示速度，因为脚本解析会减慢显示速度。

### 外置javascript代码

代码可以放在外置文件中。

外置文件：myScript.js
```javascript
function myFunction() {
 document.getElementById("demo").innerHTML = "Paragraph changed.";
}
```

当在许多不同的网页中使用相同的代码时，外部脚本是实用的。

JavaScript文件的文件扩展名为.js。

要使用外部脚本，请将脚本文件的名称放在`<script>`标记的src（源）属性中：

```
<script src="myScript.js"></script>
```

外置javascript代码也可以放在`<body>`或`<head>`中。执行方式和代码放置在`<script>`标签中是一样的。

> 外置脚本中不能包含`<script>`标签

### 外置javascript代码的优点

将脚本放在外部文件中具有一些优点：

- 它将HTML和代码分开
- 它使HTML和JavaScript易于阅读和维护
- 缓存的JavaScript文件可以加快页面加载速度

要将多个脚本文件添加到一页中，可以使用多个脚本标签：

```html
<script src="myScript1.js"></script>
<script src="myScript2.js"></script>
```

### 外部引用 

可以使用完整URL或相对于当前网页的路径引用外部脚本。

本示例使用完整的URL链接到脚本：

```html
<script src="https://www.domain.com/js/myScript1.js"></script>
```

本示例使用位于当前网站上指定文件夹中的脚本：

```html
<script src="/js/myScript1.js"></script>
```

本示例链接到与当前页面位于同一文件夹中的脚本：

```html
<script src="myScript1.js"></script>
```

## JavaScript输出

JavaScript可以通过不同的方式“显示”数据：

- 使用`innerHTML`写入HTML元素。
- 使用`document.write()`写入HTML输出。
- 使用`window.alert()`写入警报框。
- 使用`console.log()`写入浏览器控制台。

### 使用`innerHTML`

访问html元素，可以使用`document.getElementById(id)`方法。`id`属性定义的html元素，`innerHTML`属性定义的html内容。

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My First Paragraph</p>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>

</body>
</html>
```

### 使用 `document.write()`

使用`document.write()`可以方便测试

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
document.write(5 + 6);
</script>

</body>
</html>
```

> 文档加载后，使用`document.write()`方法会删除文档所有内容。
> `document.write()`仅用于代码测试

尝试以下代码：

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<button type="button" onclick="document.write(5 + 6)">Try it</button>

</body>
</html>
```

### `window.alert()`

可以使用提示窗口显示数据

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<script>
window.alert(5 + 6);
</script>

</body>
</html>
```

### `console.log()`

为了测试，可以使用`console.log()`方法显示数据。

```html
<!DOCTYPE html>
<html>
<body>

<script>
console.log(5 + 6);
</script>

</body>
</html>
```




  

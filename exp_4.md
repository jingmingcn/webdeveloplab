---
show: step
version: 1.0
enable_checker: true
---

# `CSS`基础

## `CSS`介绍

**什么是`CSS`？**

- `CSS`代表级联样式表
- `CSS`描述了如何在屏幕，纸张或其他媒体上显示HTML元素
- `CSS`节省了大量工作。 它可以一次控制多个网页的布局
- 外部样式表存储在`CSS`文件中

新建文件`demo.html`, 并复制以下源代码，将显示一个`HTML`页面，其中显示了四个不同的样式表。点击"Stylesheet 1", "Stylesheet 2", "Stylesheet 3", "Stylesheet 4" 四个链接查看不同的显示效果。

```html

<!DOCTYPE html>
<html>
<head>
<style>/* Stylesheet 1: */
body {
    font: 100% Lucida Sans, Verdana;
    margin: 20px;
    line-height: 26px;
}

.container {
    xmin-width: 900px;
}

.wrapper {
    position: relative;
    overflow: auto;
}

#top, #sidebar, #bottom, .menuitem {
    border-radius: 4px;
    margin: 4px;
}

#top {
    background-color: #4CAF50;
    color: #ffffff;
    padding: 15px;
}

#menubar {
    width: 200px;
    float: left
}

#main {
    padding: 10px;
    margin: 0 210px;
}

#sidebar {
    background-color: #32a4e7;
    color: #ffffff;
    padding: 10px;
    width: 180px;
    bottom: 0;
    top: 0;
    right: 0;
    position: absolute;
}

#bottom {
    border: 1px solid #d4d4d4;
    background-color: #f1f1f1;
    text-align: center;
    padding: 10px;
    font-size: 70%;
    line-height: 14px;
}

#top h1, #top p, #menulist {
    margin: 0;
    padding: 0;
}

.menuitem {
    background-color: #f1f1f1;
    border: 1px solid #d4d4d4;
    list-style-type: none;
    padding: 2px;
    cursor: pointer;
}

.menuitem:hover {
    background-color: #ffffff;
}

.menuitem:first-child {
   background-color:#4CAF50;
   color: white;
   font-weight:bold;
}

a {
    color: #000000;
    text-decoration: underline;
}

a:hover {
    text-decoration: none;
}


@media (max-width: 800px) {
    #sidebar {
        width: auto;
        position: relative;
    } 
    #main {
        margin-right: 0;
    }    
       
}

@media (max-width: 600px) {
    #menubar {
        width: auto;
        float: none;
    }
    #main {
        margin: 0;
    }    
}
</style>

<style>/* Stylesheet 2: */
body {
    font-family: Arial;
    background-color: #d14836;
    line-height: 20px;
}

.container {
    xmin-width: 900px;
}

.wrapper {
    position: relative;
    overflow: auto;
}

#top {
    color: #ffffff;
    padding: 15px;
    font-size: 30px;
    line-height: 26px;    
}

#top h1 {
    margin:0;
    line-height: 50px;
}

#menubar {
    width: 190px;
    float: right;
}

#main {
    padding: 10px;
    background-color: #ffffff;
    font: 80% Verdana;
}

#main h1, #main h2 {
    color: #d14836;
}

#sidebar {
    background-color: #F6DAD7;
    color: #d14836;
    padding: 10px;
}

#bottom {
    text-align: center;
    padding: 10px;
    font-size: 70%;
    color: #ffffff;
}

#menulist {
    padding:0;
    font: 16px verdana;
}

.menuitem {
    width: 155px;
    background-color: #d14836;
    border: 1px solid #d14836;
    border-radius: 40px;
    color: #ffffff;
    list-style-type: none;
    margin: 10px;
    padding: 5px;
    text-align: center;
    cursor: pointer;
}

.menuitem:nth-child(2) {
   background-color:white;
   color: #d14836;
   font-weight:bold;
}

.menuitem:hover {
    background-color: #ffffff;
    color: #d14836;
}

a {
    color: #d14836;
    text-decoration: none;
}

a:hover {
    text-decoration: underline;
}
</style>

<style>/* Stylesheet 3: */
body {
    font: 100% Verdana;
    margin: 20px;
    line-height: 26px;
}

.container {
    xmin-width: 900px;
}

.wrapper {
    position: relative;
    overflow: auto;
}

#sidebar {
    background-color: #f1f1f1;
    border: 1px solid #d4d4d4;
    padding-left: 10px;
}

#bottom {
    text-align: center;
    padding: 10px;
    font-size: 70%;
    line-height: 14px;
}

h1, h2, h3 {
    color: #4CAF50;
}

#menulist {
    padding: 0;
    position: relative;
    overflow: auto;
}

.menuitem {
    width: 165px;
    float: left;
    background-color: #555555;
    color: #ffffff;
    list-style-type: none;
    margin: 4px;
    padding: 2px;
    text-align: center;
    cursor: pointer;
}

.menuitem:nth-child(3) {
   background-color:#4CAF50;
}

.menuitem:hover {
    background-color: #999999;
}

a {
    color: #000000;
}

a:hover {
    color: #84c754;
}
</style>
<style>/* Stylesheet 4: */
body {
    font: 100% Courier New;
    margin: 20px;
    line-height: 26px;
    background-color: #000000;
}

.container {
    xmin-width: 900px;
}

.wrapper {
    position: relative;
    overflow: auto;
}

#top {
    color: #84c754;
    padding: 15px;
}

#main {
    padding: 10px;
    color: #84c754;
}

#sidebar {
    color: #ffffff;
    border: 1px solid #ffffff;
    border-radius: 4px;
    padding: 10px;
    width: 320px;
    top: 0;
    right: 0;
    position: absolute;
    font-size: 80%;
    line-height: 20px;
}

#bottom {
    border: 1px solid #ffffff;
    border-radius: 4px;
    color: #ffffff;
    text-align: center;
    padding: 10px;
    font-size: 70%;
    line-height: 14px;
}

#top h1,#top p {
    margin: 0;
}

.menuitem {
    color: #84c754;
    cursor: pointer;
}

.menuitem:nth-child(4) {
    color:white;
    font-weight:bold;
}

.menuitem:hover {
    color: #ffffff;
}

a {
    color: #ffffff;
}

a:hover {
    color: #84c754;
}
@media (max-width: 600px) {
    #sidebar {
       width: auto;
       margin-bottom:10px;        
       position: relative;
    }    
}

</style>

</head>
<body>

<div class="container wrapper">
  <div id="top">
    <h1>Welcome to My Homepage</h1>
    <p>Use the menu to select different Stylesheets</p>
  </div>
  <div class="wrapper">
   <div id="menubar">
     <ul id="menulist">
       <li class="menuitem" onclick="reStyle(0)">Stylesheet 1
       <li class="menuitem" onclick="reStyle(1)">Stylesheet 2
       <li class="menuitem" onclick="reStyle(2)">Stylesheet 3
       <li class="menuitem" onclick="reStyle(3)">Stylesheet 4
       <li class="menuitem" onclick="noStyles()">No Stylesheet
     </ul>
    </div>
    <div id="main">
      <h1>Same Page Different Stylesheets</h1>
      <p>This is a demonstration of how different stylesheets can change the layout of your HTML page. You can change the layout of this page by selecting different stylesheets in the menu, or by selecting one of the following links:<br>
      <a href="#" onclick="reStyle(0);return false">Stylesheet1</a>,
      <a href="#" onclick="reStyle(1);return false">Stylesheet2</a>,
      <a href="#" onclick="reStyle(2);return false">Stylesheet3</a>,
      <a href="#" onclick="reStyle(3);return false">Stylesheet4</a>.
      </p>
       <h2>No Styles</h2>
      <p>This page uses DIV elements to group different sections of the HTML page. Click here to see how the page looks like with no stylesheet:<br><a href="#" onclick="noStyles();return false">No Stylesheet</a>.</p>
   </div>
    <div id="sidebar">
      <h3>Side-Bar</h3>
      <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.</p>
    </div>
  </div>  
  
  
  <div id="bottom">
    Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
  </div>
</div>

<script>
function noStyles() {
    document.styleSheets[0].disabled = true;
    document.styleSheets[1].disabled = true;
    document.styleSheets[2].disabled = true;
    document.styleSheets[3].disabled = true;
}

function reStyle(n) {
    noStyles()
    document.styleSheets[n].disabled = false;
}

function closeBlackdiv() {
    var blackdiv, stylediv;
    blackdiv = document.getElementById("blackdiv")
    blackdiv.parentNode.removeChild(blackdiv);
    stylediv = document.getElementById("stylediv")
    stylediv.parentNode.removeChild(stylediv);
}

function showStyle(n) {
var div, text, blackdiv;
blackdiv = document.createElement("DIV");
blackdiv.setAttribute("style","background-color:#000000;position:absolute;width:100%;height:100%;top:0;opacity:0.5;margin-left:-20px;");
blackdiv.setAttribute("id","blackdiv");
blackdiv.setAttribute("onclick","closeBlackdiv()");
document.body.appendChild(blackdiv);
div = document.createElement("DIV");
div.setAttribute("id","stylediv");
div.setAttribute("style","background-color:#ffffff;padding-left:5px;position:absolute;width:auto;height:auto;top:100px;bottom:50px;left:200px;right:200px;overflow:auto;font-family: monospace; white-space: pre;line-height:16px;");
text = document.createTextNode(document.getElementsByTagName("STYLE")[n].innerHTML);
div.appendChild(text);
document.body.appendChild(div);
//alert(document.getElementsByTagName("STYLE")[n].innerHTML);
}
reStyle(0);
</script>
</body>
</html>

```

**为什么使用CSS？**

CSS用于定义网页的样式，包括针对不同设备和屏幕尺寸的显示设计，布局和变体。

实验以下代码，了解基本的CSS使用方法。

```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: lightblue;
}

h1 {
  color: white;
  text-align: center;
}

p {
  font-family: verdana;
  font-size: 20px;
}
</style>
</head>
<body>

<h1>My First CSS Example</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

**CSS解决了一个很大的难题**

HTML规范从设计之初，从未打算包含用于格式化网页的标签！

创建HTML来描述网页的内容，例如：

```html
<h1>这是标题</h1>
<p>这是一个段落。</p>
```

将`<font>`之类的标签和`color`属性添加到HTML 3.2规范后，这对Web开发人员来说是一场噩梦。 大型网站的开发将字体和颜色信息添加到每个页面中，这是一个漫长而昂贵的过程。

为了解决此问题，万维网联盟（W3C）创建了CSS。

CSS从HTML页面中删除了样式格式！

**使用CSS可以节省大量的工作**

样式定义通常保存在外部`.css`文件中。

使用外部样式表文件，您只需更改一个文件即可更改整个网站的外观！

## CSS语法


CSS规则集由一个选择器和一个声明块组成：
![CSS语法](https://doc.shiyanlou.com/courses/uid1361580-20200430-1588176630231)

选择器指向您要设置样式的HTML元素。

声明块包含一个或多个用分号分隔的声明。

每个声明都包含一个CSS属性名称和一个值，以冒号(:)分隔。

多个CSS声明用分号(;)分隔，声明块用花括号({})括起来。

**示例**

在此示例中，所有`<p>`元素都将居中对齐，并带有红色文本颜色：

```html
<!DOCTYPE html>
<html>
<head>
<style>
p {
  color: red;
  text-align: center;
} 
</style>
</head>
<body>

<p>Hello World!</p>
<p>These paragraphs are styled with CSS.</p>

</body>
</html>
```

示例解释：

- `p`是CSS中的选择器（它指向要设置样式的HTML元素：`<p>`）。
- `color`是属性，`red`是属性值
- `text-align`是属性，`center`是属性值

## CSS选择器

CSS选择器用于“查找”（或选择）要设置样式的HTML元素。

CSS选择器可以分为五类：

- 简单选择器（根据`name`，`id`，`class`选择元素）
- 组合器选择器（根据它们之间的特定关系选择元素）
- 伪类选择器（根据特定状态选择元素）
- 伪元素选择器（选择元素的一部分并设置其样式）
- 属性选择器（根据属性或属性值选择元素）

本次实验主要讲解第一类简单选择器。

### 元素选择器

元素选择器基于元素名字选择HTML元素。以下示例，页面中所有`<p>`元素都会居中并用红色显示。

```style
p {
  text-align: center;
  color: red;
}
```

### id选择器

- id选择器使用HTML元素的`id`属性来选择特定元素。

- 元素的ID在页面中是唯一的，因此ID选择器用于选择一个唯一的元素！

- 要选择具有特定ID的元素，请写一个井号（`＃`），后跟该元素的ID。

以下CSS规则将应用于`id ="para1"`的HTML元素：

```style
#para1 {
  text-align: center;
  color: red;
}
```
**注意**：ID名称不能以数字开头！


### `class`类选择器

- 类选择器选择具有特定类属性的HTML元素。
- 要选择具有特定类的元素，请写一个句点（`.`）字符，后跟类名。

在此示例中，所有带有 `class="center"`的HTML元素将为红色且居中对齐：

```style
.center {
  text-align: center;
  color: red;
}
```

还可以指定仅特定的HTML元素应受此类影响。

在此示例中，只有具有`class ="center"`的`<p>`元素将居中对齐：

```style
p.center {
  text-align: center;
  color: red;
}
```

HTML元素也可以引用多个类, 以下示例`<p>`元素关联了两个类定义`center`,`large`。

```html
<p class="center large">This paragraph refers to two classes.</p>
```

### CSS通用选择器

通用选择器（`*`）选择页面上的所有HTML元素。

下面的CSS规则将影响页面上的每个HTML元素：

```style
* {
  text-align: center;
  color: blue;
}
```

完整源代码如下所示，实验并预览效果。

```html
<!DOCTYPE html>
<html>
<head>
<style>
* {
  text-align: center;
  color: blue;
}
</style>
</head>
<body>

<h1>Hello world!</h1>

<p>Every element on the page will be affected by the style.</p>
<p id="para1">Me too!</p>
<p>And me!</p>

</body>
</html>
```

### 分组选择器

分组选择器选择所有具有相同样式定义的HTML元素。

查看以下CSS代码（`h1`，`h2`和`p`元素具有相同的样式定义）：

```style
h1 {
  text-align: center;
  color: red;
}

h2 {
  text-align: center;
  color: red;
}

p {
  text-align: center;
  color: red;
}
```

可以通过分组选择器简化代码，将每个选择器使用逗号分隔(`,`)

```style
h1, h2, p {
  text-align: center;
  color: red;
}
```

## CSS注释

CSS注释使用`/*`开始，并用`*/`结尾。一般有以下三种注译方法：

```style
/* This is a single-line comment */
p {
  color: red;
}
```

```style
p {
  color: red;  /* Set text color to red */
}
```

```style
/* This is
a multi-line
comment */

p {
  color: red;
}
```

## CSS盒子模型（Box Model）

所有HTML元素都可以视为盒子。 在CSS中，谈论设计和布局时使用术语“盒子模型”。

CSS盒子模型本质上是一个包装每个HTML元素的框。 它包括：页边距（margins），边框（borders），填充（padding）和实际内容（content）。 下图说明了盒子模型：

![盒子模型](https://doc.shiyanlou.com/courses/uid1361580-20200430-1588179203218)

- Content-框的内容，其中显示文本和图像
- Padding-清除内容周围的区域。 填充是透明的
- Border-围绕边框和内容的边框
- Margin-清除边界外的区域。 边距是透明的

盒子模型允许我们在元素周围添加边框，并定义元素之间的空间。 

**盒子模型示例**

实验并尝试修改以下源代码，预览显示效果。

```html
<!DOCTYPE html>
<html>
<head>
<style>
div {
  background-color: lightgrey;
  width: 300px;
  border: 15px solid green;
  padding: 50px;
  margin: 20px;
}
</style>
</head>
<body>

<h2>Demonstrating the Box Model</h2>

<p>The CSS box model is essentially a box that wraps around every HTML element. It consists of: borders, padding, margins, and the actual content.</p>

<div>This text is the content of the box. We have added a 50px padding, 20px margin and a 15px green border. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>

</body>
</html>
```

**元素的宽度和高度**

为了在所有浏览器中正确设置元素的宽度和高度，需要了解盒子模型如何工作。

**重要**：使用CSS设置元素的`width`和`height`属性时，只需设置内容区域的宽度和高度。 要计算元素的完整大小，还必须添加填充，边框和边距。


示例： `<div>`元素总共有`350px`的宽度。

```style
div {
  width: 320px;
  padding: 10px;
  border: 5px solid gray;
  margin: 0;
}
```

计算过程如下：

```
320px (width)
+ 20px (left + right padding)
+ 10px (left + right border)
+ 0px (left + right margin)
= 350px
```

```
Total element width = width + left padding + right padding + left border + right border + left margin + right margin
Total element height = height + top padding + bottom padding + top border + bottom border + top margin + bottom margin
```

## CSS链接

使用CSS，链接可以是以下几种样式。

![四种链接样式](https://doc.shiyanlou.com/courses/uid1361580-20200430-1588186697633)

链接可以使用CSS的任意属性 (如：`color`, `font-family`, `background`, 等.).

示例：

```style
a {
  color: hotpink;
}
```

此外，可以根据链接处于何种状态来设置其样式。

链接的四种状态：

- a:link - 正常，未访问的链接
- a:visited - 已经访问过的链接
- a:hover - 鼠标悬停在链接上
- a:active - 链接被点击激活

对应的源代码示例如下，实验以下源代码，预览显示效果。

```html
<!DOCTYPE html>
<html>
<head>
<style>
/* unvisited link */
a:link {
  color: red;
}

/* visited link */
a:visited {
  color: green;
}

/* mouse over link */
a:hover {
  color: hotpink;
}

/* selected link */
a:active {
  color: blue;
}
</style>
</head>
<body>

<p><b><a href="default.asp" target="_blank">This is a link</a></b></p>
<p><b>Note:</b> a:hover MUST come after a:link and a:visited in the CSS definition in order to be effective.</p>
<p><b>Note:</b> a:active MUST come after a:hover in the CSS definition in order to be effective.</p>

</body>
</html>

```

**`text-decoration`属性**

`text-decoration`属性经常用于去掉链接下划线。

```style
a:link {
  text-decoration: none;
}

a:visited {
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

a:active {
  text-decoration: underline;
}
```

**背景色**

可以使用`background-color`属性设置链接背景颜色。

```style
a:link {
  background-color: yellow;
}

a:visited {
  background-color: cyan;
}

a:hover {
  background-color: lightgreen;
}

a:active {
  background-color: hotpink;
} 
```

**链接按钮**

此示例演示了一个更高级的示例，其中我们组合了多个CSS属性以将链接显示为框/按钮：

```html
<!DOCTYPE html>
<html>
<head>
<style>
a:link, a:visited {
  background-color: #f44336;
  color: white;
  padding: 14px 25px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
}

a:hover, a:active {
  background-color: red;
}
</style>
</head>
<body>

<h2>Link Button</h2>
<p>A link styled as a button:</p>
<a href="default.asp" target="_blank">This is a link</a>

</body>
</html>

```

##CSS表单

HTML表单的外观可以通过CSS样式改善。

第一个例子：实验以下源代码，预览显示效果。

```html
<!DOCTYPE html>
<html>
<style>
input[type=text], select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type=submit] {
  width: 100%;
  background-color: #4CAF50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type=submit]:hover {
  background-color: #45a049;
}

div {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>
<body>

<h3>Using CSS to style an HTML Form</h3>

<div>
  <form action="/action_page.php">
    <label for="fname">First Name</label>
    <input type="text" id="fname" name="firstname" placeholder="Your name..">

    <label for="lname">Last Name</label>
    <input type="text" id="lname" name="lastname" placeholder="Your last name..">

    <label for="country">Country</label>
    <select id="country" name="country">
      <option value="australia">Australia</option>
      <option value="canada">Canada</option>
      <option value="usa">USA</option>
    </select>
  
    <input type="submit" value="Submit">
  </form>
</div>

</body>
</html>

```

### 装饰 `input` 输入框

使用`width`属性确定输入字段的宽度：

```html
<!DOCTYPE html>
<html>
<head>
<style> 
input {
  width: 100%;
}
</style>
</head>
<body>

<p>A full-width input field:</p>

<form>
  <label for="fname">First Name</label>
  <input type="text" id="fname" name="fname">
</form>

</body>
</html>

```

上面的示例适用于所有`<input>`元素。 如果只想设置特定输入类型的样式，则可以使用属性选择器：

- `input[type=text]` 只选择文本输入框
- `input[type=password]` 只选择密码输入框
- `input[type=number]` 只选择数值输入框

### `padding`输入框

使用`padding`属性添加输入框内的空间

提示：当彼此之间有很多输入时，您可能还想添加一些边距，以在它们之外添加更多空间：

```html
<!DOCTYPE html>
<html>
<head>
<style> 
input[type=text] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
}
</style>
</head>
<body>

<p>Padded text fields:</p>

<form>
  <label for="fname">First Name</label>
  <input type="text" id="fname" name="fname">
  <label for="lname">Last Name</label>
  <input type="text" id="lname" name="lname">
</form>

</body>
</html>

```

### 给输入框加边框

使用`border`属性更改边框的大小和颜色，并使用`border-radius`属性添加圆角：

```html
<!DOCTYPE html>
<html>
<head>
<style> 
input[type=text] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
  border: 2px solid red;
  border-radius: 4px;
}
</style>
</head>
<body>

<p>Text fields with borders:</p>

<form>
  <label for="fname">First Name</label>
  <input type="text" id="fname" name="fname">
  <label for="lname">Last Name</label>
  <input type="text" id="lname" name="lname">
</form>

</body>
</html>

```

如果只需要底部边框，可以使用`border-bottom`属性：

```style
input[type=text] {
  border: none;
  border-bottom: 2px solid red;
}
```

### 给输入框添加颜色

使用`background-color`属性为输入添加背景色，并使用`color`属性更改文本颜色：

```style
input[type=text] {
  background-color: #3CBC8D;
  color: white;
}

```

### 聚焦输入框

默认情况下，某些浏览器在获得焦点（单击）时会在输入周围添加蓝色轮廓。 您可以通过添加`outline: none;`来消除此行为。

使用：`:focus`选择器可以在输入字段获得焦点时对其进行操作：

```style
input[type=text]:focus {
  background-color: lightblue;
}
```

```style
input[type=text]:focus {
  border: 3px solid #555;
}
```

### 给输入框添加图标或图片

如果要在输入中包含图标，请使用`background-image`属性，并将其与`background-position`属性一起放置。 还要注意，我们添加了一个较大的左填充来保留图标的空间：

可以使用以下图片作为`searchicon.png`文件。

![searchicon.png](https://doc.shiyanlou.com/courses/uid1361580-20200430-1588188993765)

```html
<!DOCTYPE html>
<html>
<head>
<style> 
input[type=text] {
  width: 100%;
  box-sizing: border-box;
  border: 2px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
  background-color: white;
  background-image: url('searchicon.png');
  background-position: 10px 10px; 
  background-repeat: no-repeat;
  padding: 12px 20px 12px 40px;
}
</style>
</head>
<body>

<p>Input with icon:</p>

<form>
  <input type="text" name="search" placeholder="Search..">
</form>

</body>
</html>

```

### 给搜索输入框添加动画

在此示例中，我们使用CSS`transition`属性为搜索输入获得焦点时的宽度设置动画。 

```html
<!DOCTYPE html>
<html>
<head>
<style> 
input[type=text] {
  width: 130px;
  box-sizing: border-box;
  border: 2px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
  background-color: white;
  background-image: url('searchicon.png');
  background-position: 10px 10px; 
  background-repeat: no-repeat;
  padding: 12px 20px 12px 40px;
  transition: width 0.4s ease-in-out;
}

input[type=text]:focus {
  width: 100%;
}
</style>
</head>
<body>

<p>Animated search input:</p>

<form>
  <input type="text" name="search" placeholder="Search..">
</form>

</body>
</html>

```

### 下拉列表菜单加样式

```html
<!DOCTYPE html>
<html>
<head>
<style> 
select {
  width: 100%;
  padding: 16px 20px;
  border: none;
  border-radius: 4px;
  background-color: #f1f1f1;
}
</style>
</head>
<body>

<p>A styled select menu.</p>

<form>
  <select id="country" name="country">
  <option value="au">Australia</option>
  <option value="ca">Canada</option>
  <option value="usa">USA</option>
  </select>
</form>

</body>
</html>

```

## CSS布局 `display: inline-block`

**`display:inline-block`**

与`display:inline`相比，主要区别在于`display:inline-block`允许在元素上设置宽度和高度。

另外，在`display:inline-block`中，将遵守顶部和底部边距/填充，但在`display:inline`中则不考虑。

与`display:block`相比，主要区别在于`display:inline-block`在元素之后不添加换行符，因此该元素可以位于其他元素旁边。

以下示例显示`display`的不同行为`display:inline`，`display:inline-block`和`display:block`：

```html
<!DOCTYPE html>
<html>
<head>
<style>
span.a {
  display: inline; /* the default for span */
  width: 100px;
  height: 100px;
  padding: 5px;
  border: 1px solid blue;  
  background-color: yellow; 
}

span.b {
  display: inline-block;
  width: 100px;
  height: 100px;
  padding: 5px;
  border: 1px solid blue;    
  background-color: yellow; 
}

span.c {
  display: block;
  width: 100px;
  height: 100px;
  padding: 5px;
  border: 1px solid blue;    
  background-color: yellow; 
}
</style>
</head>
<body>

<h1>The display Property</h1>

<h2>display: inline</h2>
<div>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum consequat scelerisque elit sit amet consequat. Aliquam erat volutpat. <span class="a">Aliquam</span> <span class="a">venenatis</span> gravida nisl sit amet facilisis. Nullam cursus fermentum velit sed laoreet. </div>

<h2>display: inline-block</h2>
<div>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum consequat scelerisque elit sit amet consequat. Aliquam erat volutpat. <span class="b">Aliquam</span> <span class="b">venenatis</span> gravida nisl sit amet facilisis. Nullam cursus fermentum velit sed laoreet. </div>

<h2>display: block</h2>
<div>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum consequat scelerisque elit sit amet consequat. Aliquam erat volutpat. <span class="c">Aliquam</span> <span class="c">venenatis</span> gravida nisl sit amet facilisis. Nullam cursus fermentum velit sed laoreet. </div>

</body>
</html>

```














  

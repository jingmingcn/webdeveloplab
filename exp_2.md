---
show: step
version: 1.0
enable_checker: true
---

# HTML5 表格和表单

## HTML5 表格

本次实验内容主要学习html5表格的使用方法。实验内容汇总如下：

- 使用HTML `<table>`元素定义一个表
- 使用HTML `<tr>`元素定义表行
- 使用HTML `<td>`元素定义表数据
- 使用HTML `<th>`元素定义表标题
- 使用HTML `<caption>`元素定义表格标题
- 使用CSS `border`属性定义边框
- 使用CSS `border-collapse`属性折叠单元格边框
- 使用CSS `padding`属性将填充添加到单元格
- 使用CSS `text-align`属性对齐单元格文本
- 使用CSS `border-spacing`属性设置单元格之间的间距
- 使用`colspan`属性使单元格跨很多列
- 使用`rowspan`属性使一个单元格跨很多行
- 使用`id`属性唯一定义一个表

### 第一个表格示例

首先看一个html5表格的示例，源代码如下：

```html
<!DOCTYPE html>
<html>
<head>
<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>
</head>
<body>

<h2>HTML Table</h2>

<table>
  <tr>
    <th>Company</th>
    <th>Contact</th>
    <th>Country</th>
  </tr>
  <tr>
    <td>Alfreds Futterkiste</td>
    <td>Maria Anders</td>
    <td>Germany</td>
  </tr>
  <tr>
    <td>Centro comercial Moctezuma</td>
    <td>Francisco Chang</td>
    <td>Mexico</td>
  </tr>
  <tr>
    <td>Ernst Handel</td>
    <td>Roland Mendel</td>
    <td>Austria</td>
  </tr>
  <tr>
    <td>Island Trading</td>
    <td>Helen Bennett</td>
    <td>UK</td>
  </tr>
  <tr>
    <td>Laughing Bacchus Winecellars</td>
    <td>Yoshi Tannamuri</td>
    <td>Canada</td>
  </tr>
  <tr>
    <td>Magazzini Alimentari Riuniti</td>
    <td>Giovanni Rovelli</td>
    <td>Italy</td>
  </tr>
</table>

</body>
</html>
```

新建文件`index.html`,使用以上源码预览显示效果。

```checker
- name: check table tag exist
  script: |
    #!/bin/bash
    grep 'table' /home/project/index.html
  error: index.html文件中没有找到&lt;table&gt;标签
```

### 定义html5表格

HTML表是用`<table>`标记定义的。

每个表行都用`<tr>`标记定义。 表头是用`<th>`标记定义的。 默认情况下，表标题为粗体和居中。 表数据/单元格用`<td>`标记定义。

```html
<table style="width:100%">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
</table>
```

请实验以上源码，并预览显示效果。

注意：`<td>`元素是表的数据容器。
它们可以包含各种HTML元素。 文字，图片，列表，其他表格等。

```checker
- name: check table tag exist
  script: |
    #!/bin/bash
    grep 'table' /home/project/index.html
  error: index.html文件中没有找到&lt;table&gt;标签
```

### html5表格添加边框

如果没有为表格指定边框，它将显示为无边框。

使用CSS border属性设置边框：

```style
table, th, td {
  border: 1px solid black;
}
```

以上CSS代码定义了表格的边框样式，`1px`表示宽度，`solid`表示实线，`black`表示边框颜色。

注：CSS详细内容会在下一次实验中涉及，本次实验只需要了解基本使用方式，CSS样式代码需要放在`<style>`标签中，完整源代码参考`table_border.html`文件源码。

**实验内容：**

新建文件table_border.html，实验以下源代码并预览显示效果，可自行修改样式，实验显示效果的变化。

```html
<!DOCTYPE html>
<html>
<head>
<style>
table, th, td {
  border: 1px solid black;
}
</style>
</head>
<body>

<h2>Bordered Table</h2>
<p>Use the CSS border property to add a border to the table.</p>

<table style="width:100%">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th> 
    <th>Age</th>
  </tr>
  <tr>
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
  <tr>
    <td>John</td>
    <td>Doe</td>
    <td>80</td>
  </tr>
</table>

</body>
</html>
```

```checker
- name: check style tag exist
  script: |
    #!/bin/bash
    grep 'style' /home/project/table_border.html
  error: table_border.html文件中没有找到&lt;style&gt;标签
```

### HTML5表格边框折叠

如上节效果所示，表格的边框是分开的两条实线表示，如果希望表格的边框合并成一个边框，请添加CSS `border-collapse`属性：

CSS样式代码如下：

```style
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
```

请实验以上样式代码。

### HTML5表格单元填充

单元格填充指定单元格内容及其边界之间的空间。

如果您不指定填充，则表格单元格将不显示填充。

要设置填充，请使用CSS `padding` 属性：

```style
th, td {
  padding: 15px;
}
```
请实验以上样式代码。

### HTML5 左对齐标题

默认情况下，表标题为粗体和居中。

要使表格标题左对齐，请使用CSS `text-align`属性：

```style
th {
  text-align: left;
}
```
请实验以上样式代码。

### HTML5添加边框空隙

边框间距指定了单元格之间的间隔。

要设置表格的边框间距，请使用CSS `border-spacing`属性：

```style
table {
  border-spacing: 5px;
}
```

注意：如果表格的边框已折叠，则边框间距`border-spacing`无效。

请实验以上样式代码。

### HTML5单元格跨列

要使一个单元格跨越一列以上，请使用`colspan`属性：

```html
<table style="width:100%">
  <tr>
    <th>Name</th>
    <th colspan="2">Telephone</th>
  </tr>
  <tr>
    <td>Bill Gates</td>
    <td>55577854</td>
    <td>55577855</td>
  </tr>
</table>
```

请实验以上源代码。

### HTML5单元格跨行

要使一个单元格跨度超过一行，请使用`rowspan`属性：

```html
<table style="width:100%">
  <tr>
    <th>Name:</th>
    <td>Bill Gates</td>
  </tr>
  <tr>
    <th rowspan="2">Telephone:</th>
    <td>55577854</td>
  </tr>
  <tr>
    <td>55577855</td>
  </tr>
</table>
```
请实验以上源代码。

### HTML5表格添加标题

要将标题添加到表，请使用`<caption>`标记：

注意：`<caption>`标签必须紧接在`<table>`标签之后。

```html
<table style="width:100%">
  <caption>Monthly savings</caption>
  <tr>
    <th>Month</th>
    <th>Savings</th>
  </tr>
  <tr>
    <td>January</td>
    <td>$100</td>
  </tr>
  <tr>
    <td>February</td>
    <td>$50</td>
  </tr>
</table>
```
请实验以上源代码。

### HTML5表格对应特定样式

要为特殊表格定义特殊样式，请向该表添加`id`属性：

```html
<table id="t01">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
</table>
```

然后，为表格定义特定的样式：

```style
table#t01 {
  width: 100%;
  background-color: #f1f1c1;
}
```

也可以添加更多的样式：

```style
table#t01 tr:nth-child(even) {
  background-color: #eee;
}
table#t01 tr:nth-child(odd) {
  background-color: #fff;
}
table#t01 th {
  color: white;
  background-color: black;
}
```

实验以上三段代码，并预览显示效果。

### HTML5 table 标签

HTML5 table标签如下表所示，本实验下一步的内容将实验`colgroup`,`thead`,`tbody`,`tfoot`标签。

| 标签         | 描述                               |
|--------------|------------------------------------|
| `<table>`    | 定义表                             |
| `<th>`       | 定义表的单元格头                   |
| `<tr>`       | 定义表的一行                       |
| `<td>`       | 定义表的单元格                     |
| `<caption>`  | 定义表的标题                       |
| `<colgroup>` | 定义表中一列或多列的组用于格式化   |
| `<col>`      | 定义`<colgroup>`元素中每列的列属性 |
| `<thead>`    | 定义表中标题内容组                 |
| `<tbody>`    | 定义表中主内容组                   |
| `<tfoot>`    | 定义表的脚内容组                   |

### HTML5 `<colgroup>`标签

使用`<colgroup>`和`<col>`标记设置三列的背景色,源代码示例如下：

```html
<table>
  <colgroup>
    <col span="2" style="background-color:red">
    <col style="background-color:yellow">
  </colgroup>
  <tr>
    <th>ISBN</th>
    <th>Title</th>
    <th>Price</th>
  </tr>
  <tr>
    <td>3476896</td>
    <td>My first HTML</td>
    <td>$53</td>
  </tr>
</table>
```

`<colgroup>`标记指定表中一组用于格式化的一列或多列。

`<colgroup>`标记对于将样式应用于整个列很有用，而不是为每一行的每个单元格重复样式。

注意：`<colgroup>`标记必须`是<table>`元素的子元素，在任何`<caption>`元素之后以及在任何`<thead>`，`<tbody>`，`<tfoot>`和`<tr>`元素之前。

提示：要为`<colgroup>`中的列定义不同的属性，请使用`<colgroup>`标记内的`<col>`标记。

实验以下代码，预览显示效果。

```html
<!DOCTYPE html>
<html>
<head>
<style>
table, th, td {
  border: 1px solid black;
}
</style>
</head>
<body>

<h1>The colgroup element</h1>

<table>
  <colgroup>
    <col span="2" style="background-color:red">
    <col style="background-color:yellow">
  </colgroup>
  <tr>
    <th>ISBN</th>
    <th>Title</th>
    <th>Price</th>
  </tr>
  <tr>
    <td>3476896</td>
    <td>My first HTML</td>
    <td>$53</td>
  </tr>
  <tr>
    <td>5869207</td>
    <td>My first CSS</td>
    <td>$49</td>
  </tr>
</table>

</body>
</html>

```


### HTML5 `<thead>`标签，`<tbody>`标签，`<tfoot>`标签

一个带有`<thead>`，`<tbody>`和`<tfoot>`元素的HTML表,源代码示例如下：

```html
<table>
  <thead>
    <tr>
      <th>Month</th>
      <th>Savings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>January</td>
      <td>$100</td>
    </tr>
    <tr>
      <td>February</td>
      <td>$80</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Sum</td>
      <td>$180</td>
    </tr>
  </tfoot>
</table>
```

实验以上代码，并预览查看显示效果。

`<thead>`标记用于将HTML表中的标题内容分组。

`<thead>`元素与`<tbody>`和`<tfoot>`元素一起使用以指定表的每个部分（页眉，正文，页脚）。

浏览器可以使用这些元素来使表格主体独立于页眉和页脚滚动。 同样，当打印跨越多页的大表时，这些元素可以使表的页眉和页脚可以打印在每页的顶部和底部。

`<thead>`标记必须在以下上下文中使用：作为`<table>`元素的子代，在任何`<caption>`和`<colgroup>`元素之后以及任何`<tbody>`，`<tfoot>`和`<tr>`之前元素。

注意：`<thead>`元素内部必须具有一个或多个`<tr>`标记。

提示：默认情况下，`<thead>`，`<tbody>`和`<tfoot>`元素不会影响表格的布局。 但是，您可以使用CSS设置这些元素的样式。

### 练习

设计一个表格，显示以下数据，并使用样式对表格进行美化，最后将实验源代码和效果截图填写到实验报告中。

| 姓名 | 课程            | 成绩     |
|------|-----------------|----------|
| 张三 | Web开发<br> Java<br> OO | 90<br> 80<br>70    |
| 李四 | Web开发<br>Java     | 70 <br>60    |
| 周吴 | Web开发<br>Java<br>OO   | 50<br> 30<br> 60 |

## HTML5 表单

### 第一个表单示例

以下是一个表单的源代码，新建文件index.html，实验以下代码，预览效果。

```html
<!DOCTYPE html>
<html>
<body>

<h2>HTML Forms</h2>

<form action="index.html">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname" value="John"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname" value="Doe"><br><br>
  <input type="submit" value="Submit">
</form> 

</body>
</html>
```

### `<form>`元素

HTML`<form>`元素定义用于收集用户输入的表单：

```html
<form>
.
form elements
.
</form>
```

HTML表单包含表单元素。

表单元素是不同类型的输入元素，例如：文本字段，复选框，单选按钮，提交按钮等。

### `<input>`元素

`<input>`元素是最重要的`form`元素。

`<input>`元素以多种方式显示，具体取决于`type`属性。

这里有些例子：

| 类型 | 描述 |
|------|------|
|`<input type="text">`|定义单行文本输入字段|
|`<input type="radio">`|定义一个单选按钮（用于选择多个选项之一）|
|`<input type="submit">`|定义一个提交按钮（用于提交表单）|


**文本输入框**

`<input type ="text">`定义用于文本输入的单行输入字段。

实验以下源代码，预览显示效果。
```html
<form>
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname">
</form>
```

**`<label>`元素**


请注意，在上面的示例中使用了`<label>`元素。

`<label>`标记为许多表单元素定义了一个标签。

`<label>`元素对屏幕阅读器用户很有用，因为当用户将注意力集中在`input`元素上时，屏幕阅读器将读出加载标签。

`<label>`元素还可以帮助在很小的区域（例如单选按钮或复选框）上单击的用户遇到困难-因为当用户单击`<label>`元素内的文本时，它将切换单选按钮/复选框。

`<label>`标记的`for`属性应等于`<input>`元素的`id`属性，以将它们绑定在一起。

**单选按钮**

`<input type ="radio">`定义单选按钮。

单选按钮使用户可以选择有限数量的选项之一。

实验以下代码，预览查看效果。

```html
<form>
  <input type="radio" id="male" name="gender" value="male">
  <label for="male">Male</label><br>
  <input type="radio" id="female" name="gender" value="female">
  <label for="female">Female</label><br>
  <input type="radio" id="other" name="gender" value="other">
  <label for="other">Other</label>
</form>
```

**提交按钮**

`<input type ="submit">`定义用于将表单数据提交给表单处理程序的按钮。

表单处理程序通常是服务器上的页面，带有用于处理输入数据的脚本。

表单处理程序在表单的`action`属性中指定。

实验以下代码，预览显示效果。

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname" value="John"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname" value="Doe"><br><br>
  <input type="submit" value="Submit">
</form>
```

**`action`按钮**

`action`属性定义提交表单时要执行的操作。

通常，当用户单击“提交”按钮时，表单数据将发送到服务器上的页面。

在上面的示例中，表单数据被发送到服务器上名为`"/action_page.php"`的页面。 此页面包含用于处理表单数据的服务器端脚本：

如果省略`action`属性，则将动作设置为当前页面。


**`target`属性**

`target`属性指定提交的结果是否将在新的浏览器选项卡，框架或当前窗口中打开。

默认值为`"_self"`，这意味着表单将在当前窗口中提交。

要在新的浏览器选项卡中打开表单结果，请使用值`"_blank"`。

其他合法值是`"_parent"`，`"_top"`或代表`iframe`名称的名称。


**`method`属性**

`method`属性指定提交表单数据时要使用的`HTTP`方法（`GET`或`POST`）。

```html
<form action="/action_page.php" method="get">
```

**什么情况下使用GET**

提交表单数据时，默认的`HTTP`方法是`GET`。

但是，使用`GET`时，表单数据将在页面的地址字段中可见：

```html
/action_page.php?firstname=John&lastname=Doe
```

* 以名称/值对的形式将表单数据附加到URL中
* `URL`的长度受到限制（2048个字符）
* 切勿使用`GET`发送敏感数据！ （将在URL中显示）
* 对于用户希望将结果添加为书签的表单提交很有用
* `GET`更适合非安全数据，例如Google中的查询字符串

**什么情况下使用POST**

如果表单数据包含敏感信息或个人信息，请始终使用`POST`。 `POST`方法不会在页面地址字段中显示表单数据。

- `POST`没有大小限制，可用于发送大量数据。
- 带有`POST`的表单提交无法添加书签

**`name`属性**

每个`input`字段必须具有要提交的名称属性。

如果省略`name`属性，则将完全不发送该`input`字段的数据。

本示例将不提交“First name”输入字段的值：

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" value="John"><br><br>
  <input type="submit" value="Submit">
</form>
```


### `<select>`元素

`<select>`元素定义了一个下拉列表。

实验以下代码，预览显示效果。

```html
<select id="cars" name="cars">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>

```

`<option>`元素定义可以选择的选项。

默认情况下，下拉列表中的第一项处于选中状态。

要定义预选选项，请将`selected`属性添加到该选项：

```html
<option value="fiat" selected>Fiat</option>
```

使用`size`属性指定可见值的数量：

```html
<select name="cars" size="3">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```

使用`multiple`属性允许用户选择多个值：

```html
<select name="cars" size="4" multiple>
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```

### `<textarea>`元素

`<textarea>`元素定义了多行输入字段（文本区域）：

```html
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
```

`rows`属性指定文本区域中可见的行数。

`cols`属性指定文本区域的可见宽度。

您还可以使用`CSS`定义文本区域的大小：

```html
<textarea name="message" style="width:200px; height:600px;">
The cat was playing in the garden.
</textarea>
```

### `<button>`元素

`<button>`元素定义一个可以点击的按钮：

```html
<button type="button" onclick="alert('Hello World!')">Click Me!</button>
```

注意：始终为按钮元素指定`type`属性。 不同的浏览器可能对按钮元素使用不同的默认类型。


### `<fieldset>`和`<legend>`元素

`<fieldset>`用于编组数据中的相关数据。

`<legend>`元素给`<fieldset>`元素定义标题。

实验以下代码，预览显示效果:

```html
<form action="/action_page.php">
  <fieldset>
    <legend>Personalia:</legend>
    <label for="fname">First name:</label><br>
    <input type="text" id="fname" name="fname" value="John"><br>
    <label for="lname">Last name:</label><br>
    <input type="text" id="lname" name="lname" value="Doe"><br><br>
    <input type="submit" value="Submit">
  </fieldset>
</form>
```

### `<datalist>`元素

`<datalist>`元素为`<input>`元素指定预定义选项的列表。

用户在输入数据时将看到预定义选项的下拉列表。

`<input>`元素的`list`属性必须引用`<datalist>`元素的`id`属性。

```html
<form action="/action_page.php">
  <input list="browsers">
  <datalist id="browsers">
    <option value="Internet Explorer">
    <option value="Firefox">
    <option value="Chrome">
    <option value="Opera">
    <option value="Safari">
  </datalist>
</form>
```

### `<output>`元素

`<output>`元素表示计算的结果（类似于脚本执行的结果）。

```html
<form action="/action_page.php"
  oninput="x.value=parseInt(a.value)+parseInt(b.value)">
  0
  <input type="range"  id="a" name="a" value="50">
  100 +
  <input type="number" id="b" name="b" value="50">
  =
  <output name="x" for="a b"></output>
  <br><br>
  <input type="submit">
</form>
```










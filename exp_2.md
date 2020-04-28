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












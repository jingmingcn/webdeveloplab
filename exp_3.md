---
show: step
version: 1.0
enable_checker: true
---

# HTML5 表单

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

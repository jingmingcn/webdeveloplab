---
show: step
version: 1.0
enable_checker: true
---

# HTML5 基础

## 文档结构元素

新建文件`index.html`，添加 html5 文档类型声明，源代码如下：

```html
<!DOCTYPE html>
<html></html>
```

在 html5 文档中，文档类型声明`<!DOCTYPE>`是强制使用的，必须位于文档首行，浏览器才能获知文档类型。`<!DOCTYPE>`声明不是 html 标签，浏览器通过`<!DOCTYPE>`声明判断 html 文档使用的 html 版本，`<!DOCTYPE html>`声明使用的是 html5 的版本。

之前 html 版本的声明如下:

`HTML 4.01:`

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```

`XHTML 1.1:`

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```

- `<html>`标签
- `<head>`标签
- `<body>`标签

`<html>`与`</html>`标签定义了文档的开始和结束，文档由头部和主体组成，文档的头部由`<head>`标签定义，主体由`<body>`标签定义。

在`index.html`文件中添加`<head>`和`<body>`标签。

index.html 页面的源代码如下：

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
```

```checker
- name: check index.html exist
  script: |
    #!/bin/bash
    ls -l /home/project/index.html
  error: 没有找到 /home/project/index.html 文件
```

## 头部元素

- `<title>`标签
- `<meta>`标签

### `<title>`标签

`<title>`标记在所有 HTML 文档中都是必需的，它定义了文档的标题。

`<title>`元素：

- 在浏览器工具栏中定义标题
- 将页面添加到收藏夹时为其提供标题
- 在搜索引擎结果中显示页面标题

在 index.html 文档中添加`<title>`元素。

index.html 页面的源代码如下：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML Reference</title>
  </head>
</html>
```

### `<meta>`标签

`<meta>`标签数据是有关数据的数据（信息）。

`<meta>`标记始终位于`<head>`元素内，并且它们提供有关 HTML 文档的元数据。

`<meta>`标记通常用于指定字符集，页面描述，关键字，文档的作者和视口设置。

元数据将不会显示在页面上，但是可以在计算机上解析。

浏览器（如何显示内容或重新加载页面），搜索引擎（关键字）和其他 Web 服务都使用元数据。

HTML5 引入了一种方法，使 Web 设计人员可以通过`<meta>`标记来控制视口（用户在网页上的可见区域）（请参见下面的“设置视口”示例）。

| 属性       | 值                                                                                       | 描述                                   |
| ---------- | ---------------------------------------------------------------------------------------- | -------------------------------------- |
| charset    | character_set                                                                            | 指定 HTML 文档的字符编码               |
| content    | text                                                                                     | 给出与 http-equiv 或 name 属性关联的值 |
| http-equiv | content-type <br> default-style <br> refresh                                             | 为内容属性的信息/值提供 HTTP 标头      |
| name       | application-name <br> author <br> description <br> generator <br> keywords <br> viewport | 指定元数据的名称                       |

`<meta>`标签示例：

1. 定义搜索引擎的关键字：

```html
<meta name="keywords" content="HTML, CSS, JavaScript" />
```

2. 定义您的网页描述：

```html
<meta name="description" content="Free Web tutorials for HTML and CSS" />
```

3. 定义页面的作者：

```html
<meta name="author" content="John Doe" />
```

4. 每 30 秒刷新一次文档：

```html
<meta http-equiv="refresh" content="30" />
```

5. 设置视口，以使您的网站在所有设备上看起来都不错：

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

Viewport 是用户在网页上的可见区域。 它随设备的不同而不同-手机上的尺寸要小于计算机屏幕上的尺寸。
以下<meta>元素应该在所有网页中包含：

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

这为浏览器提供了有关如何控制页面尺寸和缩放比例的说明。

`width = device-width`部分将页面的宽度设置为跟随设备的屏幕宽度（视设备而定）。

`initial-scale = 1.0`部分设置浏览器首次加载页面时的初始缩放级别。

实验内容：在`index.html`文件中实验`<meta>`标签。

```checker
- name: check <meta> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'meta' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;meta&gt; 标签
```

## 文档结构标签

html5 结构标签用于搭建页面主体内容结构，形成不同的区块，完成整个页面的排版布局。

| 标签        | 描述                            |
| ----------- | ------------------------------- |
| `<article>` | 定义文章                        |
| `<aside>`   | 定义页面内容之外的内容          |
| `<details>` | 定义元素的细节                  |
| `<footer>`  | 定义 section 或 page 的页脚     |
| `<header>`  | 定义 section 或 page 的页眉     |
| `<nav>`     | 定义导航链接                    |
| `<section>` | 定义 section                    |
| `<summary>` | 为`<details>`元素定义可见的标题 |
| `<div>`     | 定义文档中的节                  |
| `<span>`    | 定义文档中的行内元素            |

### `<header>`标签

`<header>`元素表示介绍性内容或一组导航链接的容器。

`<header>`元素通常包含：

- 一个或多个标题元素（`<h1>`-`<h6>`）
- 徽标或图标
- 作者信息

一个文档中可以包含多个`<header>`元素。

注意：`<header>`标记不能放在`<footer>`，`<address>`或另一个`<header>`元素内。

示例：

```html
<article>
  <header>
    <h1>Most important heading here</h1>
    <h2>Less important heading here</h2>
    <p>Some additional information here</p>
  </header>
  <p>Lorem Ipsum dolor set amet....</p>
</article>
```

实验内容：在`index.html`文件中实验`<header>`标签。

```checker
- name: check <header> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'header' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;header&gt; 标签
```

### `<nav>`标签

`<nav>`标记定义了一组导航链接。

请注意，并非文档的所有链接都应在`<nav>`元素内。 `<nav>`元素仅用于主要的导航链接块。

浏览器（例如，供残障用户使用的屏幕阅读器）可以使用此元素来确定是否忽略此内容的初始呈现。

示例：

```html
<nav>
  <a href="/html/">HTML</a> | <a href="/css/">CSS</a> |
  <a href="/js/">JavaScript</a> |
  <a href="/jquery/">jQuery</a>
</nav>
```

```checker
- name: check <nav> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'nav' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;nav&gt; 标签
```

### `<article>`标签

`<article>`标记指定独立的，独立的内容。

文章应该是有意义的，并且有可能独立于网站的其余部分进行分发。

`<article>`元素的潜在来源：

- 论坛帖子
- 博客文章
- 新闻故事
- 评论

示例：

```html
<article>
  <h2>Google Chrome</h2>
  <p>
    Google Chrome is a web browser developed by Google, released in 2008. Chrome
    is the world's most popular web browser today!
  </p>
</article>

<article>
  <h2>Microsoft Edge</h2>
  <p>
    Microsoft Edge is a web browser developed by Microsoft, released in 2015.
    Microsoft Edge replaced Internet Explorer.
  </p>
</article>
```

```checker
- name: check <article> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'article' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;article&gt; 标签
```

### `<section>`标签

`<section>`标记定义文档中的各个部分，例如章节，页眉，页脚或文档的任何其他部分。

示例：

文档中的一节，说明什么是 WWF：

```html
<section>
  <h2>WWF</h2>
  <p>The World Wide Fund for Nature (WWF) is....</p>
</section>
```

```checker
- name: check <section> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'section' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;section&gt; 标签
```

### `<aside>`标签

`<aside>`标记定义了放置内容以外的内容。

预留内容应与周围的内容有关。

示例：

```html
<p>
  My family and I visited The Epcot center this summer. The weather was nice,
  and Epcot was amazing! I had a great summer together with my family!
</p>

<aside>
  <h4>Epcot Center</h4>
  <p>
    Epcot is a theme park at Walt Disney World Resort featuring exciting
    attractions, international pavilions, award-winning fireworks and seasonal
    special events.
  </p>
</aside>
```

```checker
- name: check <aside> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'aside' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;aside&gt; 标签
```

### `<footer>`标签

`<footer>`标记定义文档或节的页脚。

`<footer>`元素通常包含：

- 作者信息
- 版权信息
- 联系信息
- 网站地图
- 回到顶部链接
- 相关文件

一个文档中可以包含多个<footer>元素。

示例：

```html
<footer>
  <p>Posted by: Hege Refsnes</p>
  <p>
    Contact information:
    <a href="mailto:someone@example.com"> someone@example.com</a>.
  </p>
</footer>
```

```checker
- name: check <footer> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'footer' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;footer&gt; 标签
```

### `<details>`和`<summary>`标签

`<details>`标签指定用户可以按需查看或隐藏的其他详细信息。

`<details>`标签可用于创建用户可以打开和关闭的交互式窗口小部件。 任何种类的内容都可以放在`<details>`标记内。

除非设置了 open 属性，否则`<details>`元素的内容应该不可见。

`<summary>`标记为`<details>`元素定义了可见的标题。 可以单击标题以查看/隐藏详细信息。

指定用户可以按需查看或隐藏的详细信息：

```html
<details>
  <summary>Copyright 1999-2018.</summary>
  <p>- by Refsnes Data. All Rights Reserved.</p>
  <p>
    All content and graphics on this web site are the property of the company
    Refsnes Data.
  </p>
</details>
```

```checker
- name: check <details> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'details' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;details&gt; 标签
```

```checker
- name: check <summary> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'summary' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;summary&gt; 标签
```

### `<div>`标签

文档中具有浅蓝色背景色的部分：

```html
<div style="background-color:lightblue">
  <h3>This is a heading</h3>
  <p>This is a paragraph.</p>
</div>
```

`<div>`标记定义 HTML 文档中的分区或部分。

`<div>`元素通常用作其他 HTML 元素的容器，以使用 CSS 对其进行样式设置或使用 JavaScript 执行某些任务。

```checker
- name: check <div> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'div' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;div&gt; 标签
```

### `<span>`标签

使用`<span>`标签定义文本颜色

```html
<p>My mother has <span style="color:blue">blue</span> eyes.</p>
```

`<span>`标记是一个内联容器，用于标记文本的一部分或文档的一部分。

`<span>`标记本身并没有提供视觉上的变化，但是标记后，您可以使用 CSS 设置样式或使用 JavaScript 对其进行操作。

```checker
- name: check <span> tag exist in file index.html
  script: |
    #!/bin/bash
    grep 'span' /home/project/index.html
  error: 在 index.html 文件中没有找到 &lt;span&gt; 标签
```

## html5 基础标签

| 标签        | 描述            |
| ----------- | --------------- |
| `<h1>~<h6>` | 标题 1 至标题 6 |
| `<p>`       | 定义段落        |
| `<br>`      | 换行            |
| `<hr>`      | 水平线          |
| `<!-->`     | 注释            |

### `<h1>~<h6>`

`<h1>`到`<h6>`标记用于定义 HTML 标题。

`<h1>`定义最重要的标题。 `<h6>`定义最不重要的标题。

```html
<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<h3>This is heading 3</h3>
<h4>This is heading 4</h4>
<h5>This is heading 5</h5>
<h6>This is heading 6</h6>
```

### `<p>`

`<p>`标记定义一个段落。

浏览器会在每个`<p>`元素之前和之后自动添加一些空间（边距）。 可以使用 CSS（带有 margin 属性）修改页边距。

```html
<p>This is some text in a paragraph.</p>
```

### `<br>`

`<br>`标签插入了一个换行符。

`<br>`标签是一个空标签，这意味着它没有结束标签。

```html
<p>
  To force<br />
  line breaks<br />
  in a text,<br />
  use the br<br />
  element.
</p>
```

### `<hr>`

`<hr>`标记定义 HTML 页面中的主题中断（例如，主题转移）。

`<hr>`元素通常显示为水平规则，用于分隔 HTML 页面中的内容（或定义更改）。

```html
<h1>HTML</h1>
<p>HTML is a language for describing web pages.....</p>

<hr />

<h1>CSS</h1>
<p>CSS defines how to display HTML elements.....</p>
```

### 注释标签

comment 标签用于在源代码中插入注释。 注释不会显示在浏览器中。

您可以使用注释来解释代码，以便日后编辑源代码时为您提供帮助。 如果您有很多代码，这特别有用。

```html
<!--This is a comment. Comments are not displayed in the browser-->

<p>This is a paragraph.</p>
```

## html5 格式化标签

- 文本格式化标签
- 引用和术语定义标签
- html5 新增格式化标签

### 文本格式化标签

| 标签    | 描述                         |
| ------- | ---------------------------- |
| `<sub>` | 下标文本                     |
| `<sup>` | 上标文本                     |
| `<ins>` | 插入文本                     |
| `<del>` | 删除文本                     |
| `<wbr>` | 定义在文本何处适合添加换行符 |
| `<pre>` | 预设格式文本                 |

示例：

```html
<p>This text contains <sub>subscript</sub> text.</p>

<p>This text contains <sup>superscript</sup> text.</p>

<p>My favorite color is <del>blue</del> <ins>red</ins>!</p>

<p>My favorite color is <del>blue</del> <ins>red</ins>!</p>

<p>
  To learn AJAX, you must be familiar with the XML<wbr />Http<wbr />Request
  Object.
</p>

<pre>
Text in a pre element
is displayed in a fixed-width
font, and it preserves
both      spaces and
line breaks
</pre>
```

### 引用和术语定义标签

| 标签           | 描述       |
| -------------- | ---------- |
| `<abbr>`       | 缩写       |
| `<address>`    | 地址       |
| `<bdo>`        | 文字方向   |
| `<blockquote>` | 长的引用语 |
| `<q>`          | 短的引用语 |

示例：

```html
The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.

<address>
  Written by <a href="mailto:webmaster@example.com">Jon Doe</a>.<br />
  Visit us at:<br />
  Example.com<br />
  Box 564, Disneyland<br />
  USA
</address>

<bdo dir="rtl">
  This text will go right-to-left.
</bdo>

<blockquote cite="http://www.worldwildlife.org/who/index.html">
  For 50 years, WWF has been protecting the future of nature. The world's
  leading conservation organization, WWF works in 100 countries and is supported
  by 1.2 million members in the United States and close to 5 million globally.
</blockquote>

<p>
  WWF's goal is to:
  <q>Build a future where people live in harmony with nature.</q>
  We hope they succeed.
</p>
```

## html5 列表

| 标签   | 描述             |
| ------ | ---------------- |
| `<ol>` | 有序列表         |
| `<ul>` | 无序列表         |
| `<li>` | 列表项           |
| `<dl>` | 定义列表         |
| `<dt>` | 定义列表项目     |
| `<dd>` | 定义列表项目描述 |

### 有序列表

`<ol>`标记定义一个有序列表。 有序列表可以是数字或字母。

使用`<li>`标记定义列表项。

两个不同的有序列表（第一个列表从 1 开始，第二个列表从 50 开始）：

```html
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>

<ol start="50">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

### 无序列表

`<ul>`标记定义了无序列表（项目符号）。

将`<ul>`标记与`<li>`标记一起使用可创建无序列表。

示例：

```html
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

### 定义列表

`<dl>`标记定义描述列表。

`<dl>`标记与`<dt>`（定义术语/名称）和`<dd>`（描述每个术语/名称）一起使用。

示例：描述列表，其中包含术语和描述：

```html
<dl>
  <dt>Coffee</dt>
  <dd>Black hot drink</dd>
  <dt>Milk</dt>
  <dd>White cold drink</dd>
</dl>
```

## html5 超链接

本节讲述`<a>`标签。示例：

```html
<a href="https://www.bing.com">Visit Bing!</a>
```

### `<a>`标签

`<a>`标记定义超链接，该超链接用于从一个页面链接到另一页面。

`<a>`元素最重要的属性是`href`属性，它指示链接的目的地。

默认情况下，链接将在所有浏览器中显示如下：

- 未访问的链接带有下划线并显示为蓝色

- 已访问链接带有下划线和紫色

- 活动的链接带有下划线和红色

**注意事项**

- 提示：如果`<a>`标记没有`href`属性，则它只是超链接的占位符。

- 提示：如果`href`属性不存在，则不会显示以下属性：`download`，`hreflang`，`media`，`rel`，`target`和`type`。

- 提示：除非您指定其他目标，否则通常在当前浏览器窗口中显示链接页面。

- 提示：使用`CSS`设置链接样式：`CSS`链接和`CSS`按钮。

**属性**

| 属性           | 值                                                                                                                                                                       | 描述                                                                                                         |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| download       | filename                                                                                                                                                                 | 指定当用户单击超链接时将下载目标。                                                                           |
| href           | URL                                                                                                                                                                      | 指定链接转到的页面的 URL                                                                                     |
| hreflang       | language_code                                                                                                                                                            | 指定链接文档的语言                                                                                           |
| media          | media_query                                                                                                                                                              | 指定链接文档针对哪种媒体/设备进行了优化                                                                      |
| ping           | list_of_URLs                                                                                                                                                             | 指定以空格分隔的 URL 列表，当链接被链接时，带有正文 ping 的发布请求将由浏览器（在后台）发送。 通常用于跟踪。 |
| referrerpolicy | no-referrer <br/> no-referrer-when-downgrade <br/> origin <br/> origin-when-cross-origin <br/> unsafe-url                                                                | 指定要发送的引荐来源                                                                                         |
| rel            | alternate <br/>author <br/> bookmark <br/> external <br/> help <br/> license <br/> next <br/> nofollow <br/> noreferrer <br/> noopener <br/> prev <br/> search <br/> tag | 指定当前文档和链接文档之间的关系                                                                             |
| target         | \_blank <br/>\_parent <br/> \_self <br/>\_top <br/> framename                                                                                                            | 指定在何处打开链接的文档                                                                                     |
| type           | media_type                                                                                                                                                               | 指定链接文档的媒体类型                                                                                       |

## html5 多媒体

使用 html5 多媒体标签可以在文档中添加图像、音频、视频内容。

### html5 图像

`<img>`标签

```html
<img
  src="https://pic1.zhimg.com/v2-e327160ba23d1bc7c457b63798b85a69_1200x500.jpg"
  alt="Smiley face"
  height="420"
/>
```

`<img>`标记在 HTML 页面中定义图像。

`<img>`标记具有两个必需的属性：`src`和`alt`。

注意：从技术上讲，图像不是插入到 HTML 页面中，而是将图像链接到 HTML 页面。 `<img>`标签为引用的图像创建一个容纳空间。

提示：要将图像链接到另一个文档，只需将`<img>`标记嵌套在`<a>`标记内。

### html5 音视频

`<audio>`标签定义声音，例如音乐或其他音频流。

当前，`<audio>`元素支持 3 种文件格式：`MP3`，`WAV`和`OGG`：

`<audio>`示例：

```html
<audio controls>
  <source src="horse.ogg" type="audio/ogg" />
  <source src="horse.mp3" type="audio/mpeg" />
  Your browser does not support the audio tag.
</audio>
```

提示：`<audio>`和`</audio>`之间的任何文本将在不支持`<audio>`标记的浏览器中显示。

`<video>`标签指定视频，例如影片剪辑或其他视频流。

当前，`<video>`元素支持 3 种视频格式：`MP4`，`WebM`和`Ogg`：

```html
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4" />
  <source src="movie.ogg" type="video/ogg" />
  Your browser does not support the video tag.
</video>
```

提示：`<video>`和`</video>`标记之间的所有文本将在不支持`<video>`元素的浏览器中显示。

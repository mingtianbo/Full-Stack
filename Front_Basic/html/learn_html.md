# HTML

## 01

### 简介

<strong>什么是HTML？</strong>

HTML是用来描述网页的一种语言

- HTML指的是超文本标记语言（**H**yper **T**ext **M**arkup **L**anguage）
- HTML不是一种编程语言，而是一种**标记语言**（markup language）
- 标记语言是一套**标记标签**（markup tag）
- HTML使用**标记标签**来描述网页

<hr></hr>

**HTML标签**

HTML标记标签通常被称为HTML标签（HTML tag）。

- HTML标签是由**尖括号**包围的关键词，比如`<html>`
- HTML标签通常是**成对出现**的，比如`<b>`和`</b>`
- 标签对中的第一个标签是**开始标签**，第二个标签是**结束标签**
- 开始和结束标签也被称为**开放标签**和**闭合标签**

<hr></hr>

**HTML文档 = 网页**

- HTML文档**描述网页**
- HTML文档**包含HTML标签**和纯文本
- HTML文档也被称为**网页**

Web 浏览器的作用是读取 HTML 文档，并以网页的形式显示出它们。浏览器不会显示 HTML 标签，而是使用标签来解释页面的内容：

```html
<html>
  <body>
    <h1>
      我的第一个标题
    </h1>
    <p>
      我的第一个段落。
    </p>
  </body>
</html>
```

**例子解释**

- `<html>`与`</html>`之间的文本描述网页
- `<body>`与`</body>`之间的文本是可见的页面内容
- `<h1>`与`</h1>`之间的文本被显示为标题
- `<p>`与`</p>`之间的文本被显示为段落

<hr></hr>

### HTML编辑器

建议使用[Visual Studio Code](https://code.visualudio.com/)

使用vscode的优点；

- 开源，免费
- 自定义配置
- 集成git
- 智能提示强大
- 支持各种文件格式
- 调试功能强大
- 强大插件扩展

直接在vscode中新建文件以`.html`为后缀

编写完之后，用浏览器打开即可查看结果～

<hr></hr>

### HTML元素

**HTML文档是由HTML元素定义的。**

<hr></hr>

HTML元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码。

| 开始标签                 | 元素内容            | 结束标签 |
| ------------------------ | ------------------- | -------- |
| `<p>`                    | This is a paragraph | `</p>`   |
| `<a href="default.htm">` | This is a link      | `</a>`   |
| `<br />`                 |                     |          |

**注释**：开始标签被称为开放标签（opening tag），结束标签常称为闭合标签（closing tag）。

<hr></hr>

**HTML元素语法**

- HTML元素以**开始标签**起始

- HTML元素以**结束标签**终止

- **元素的内容**是开始标签与结束标签之间的内容

- 某些HTML元素具有**空内容（empty content）**

- 空元素**在开始标签中进行关闭**（以开始标签的结束而结束）

- 大多数HTML元素可拥有**属性**

  > 在下一章中将会介绍有关属性的内容。

<hr></hr>

**嵌套的HTML元素**

大多数HTML元素可以嵌套（可以包含其他HTML元素）。

HTML文档由嵌套的HTML元素构成。

**HTML文档实例**

```html
<html>
  	<body>
      	<p>
          	This is my first paragraph.
      	</p>
  	</body>
</html>
```

上面的例子包含了三个HTML元素。

**HTML实例解释**

**`<p>`元素：**

```html
<p>This is my first paragraph.</p>
```

这个`<p>`元素定义了HTML文档中的一个段落。

这个元素拥有一个开始标签`<p>`，以及一个结束标签`</p>`。

元素内容是：This is my first paragraph.

**`<body>`元素：**

```html
<body>
  	<p>This is my first paragraph.</p>
</body>
```

`<body>`元素定义了HTML文档的主体。

这个元素拥有一个开始标签`<body>`，以及一个结束标签`</body>`。

元素内容是另一个HTML元素（p元素）。

**`<html>`元素：**

```html
<html>
  	<body>
      	<p>
         		This is my first paragraph. 
      	</p>
  	</body>
</html>
```

`<html>`元素定义了整个HTML文档。

这个元素拥有一个开始标签`<html>`，以及一个结束标签`</html>`。

元素内容是另一个HTML元素（body元素）。

------

**不要忘记结束标签！**

即使您忘记了使用结束标签，大多数浏览器也会正确地显示HTML：

```html
<p>This is a paragraph.
<p>This is a paragraph.
```

上面的例子在大多数浏览器中都没有问题，但不要依赖这种做法。忘记使用结束标签会产生不可预料的结果或错误。

> 说明：未来的HTML版本不允许省略结束标签。

<hr></hr>

**空的HTML元素**

没有内容的HTML元素被称为空元素。空元素是在开始标签中关闭的。

`<br>`就是没有关闭标签的空元素（`<br>`标签定义换行）。

在XHTML、XML以及未来版本的HTML中，所有元素都必须被关闭。

在开始标签中添加斜杠，比如`<br />`，是关闭空元素的正确方法，HTML、XHTML和XML都接受这种方式。

即使`<br>`在所有浏览器中都是有效的，但使用`<br />`其实是更长远的保障。

<hr></hr>

**HTML提示：使用小写标签**

HTML标签对大小写不敏感：`<P>`等同于`<p>`。许多网站都使用大写的HTML标签。

W3School 使用的是小写标签，因为万维网联盟（W3C）在 HTML 4 中**推荐**使用小写，而在未来 (X)HTML 版本中**强制**使用小写。

<hr></hr>

### HTML属性

**属性为HTML元素提供附加信息。**

<hr></hr>

HTML标签可以拥有**属性**。属性提供了有关HTML元素的**更多的信息**。

属性总是以名称/值对的形式出现，比如：**name = "value"**。

属性总是在HTML元素的**开始标签**中规定。

<hr></hr>

**属性实例**

HTML链接由`<a>`标签定义。链接的地址在`href`属性中指定：

```html
<a href="http://www.w3school.com.cn">This is a link</a>
```

<hr></hr>

**更多HTML属性实例**

**属性例子1：**

`<h1>`：定义标题的开始。

`<h1 align="center">`：拥有关于对齐方式的附加信息。

> 说明：居中排列标题。

**属性例子2：**

`<body>`：定义HTML文档的主体。

`<body bgcolor="yellow">`：拥有关于背景颜色的附加信息。

> 说明：背景颜色。

**属性例子3:**

`<table>`：定义HTML表格。（将在后面的章节中学习到更多有关的内容，所以示例中先不展示）。

`<table border="1">`：拥有关于表格边框的附加信息。

<hr></hr>

**HTML提示：使用小写属性**

属性和属性值对大小写**不敏感**。

不过，万维网联盟在其 HTML 4 推荐标准中推荐小写的属性/属性值。

而新版本的 (X)HTML 要求使用小写属性。

<hr></hr>

**始终为属性值加引号**

属性值应该始终被包括在引号内，双引号是最常用的，不过使用单引号也没有问题。

在某些个别的情况下，比如属性值本身就含有双引号，那么您必须使用单引号，例如：

```html
name='Bill "HelloWorld"Gates'
```

****

**HTML属性参考手册**

我们完整的HTML参考手册提供了每个HTML元素可使用的合法属性的完成列表：

[完整的HTML参考手册](https://www.w3school.com.cn/tags/index.asp)

下面列出了适用于大多数HTML元素的属性：

| 属性    | 值                 | 描述                                     |
| ------- | ------------------ | ---------------------------------------- |
| `class` | `classname`        | 规定元素的类名（classname）              |
| `id`    | `id`               | 规定元素的唯一id                         |
| `style` | `style_definition` | 规定元素的行内样式（inline style）       |
| `title` | `text`             | 规定元素的额外信息（可在工具提示中显示） |

如需更多关于标准属性的信息，请访问：

[HTML标准属性参考手册](https://www.w3school.com.cn/tags/html_ref_standardattributes.asp)

<hr></hr>



## 02

### HTML标题

**在HTML文档中，标题很重要**

<hr></hr>

**HTML标题**

标题（Heading）是通过`<h1>-<h6>`等标签进行定义的。

`<h1>`定义是最大的标题。`<h6>`定义是最小的标题。

**实例**

```html
<h1>This is a heading</h1>
<h2>This is a heading</h2>
<h3>This is a heading</h3>
<h4>This is a heading</h4>
<h5>This is a heading</h5>
<h6>This is a heading</h6>
```

> 说明：浏览器会自动地在标题的前后添加空行。
>
> 默认情况下，HTML会自动地在块级元素前后添加一个额外的空行，比如段落、标题元素前后。

<hr></hr>

**标题很重要**

- 请确保将HTML heading标签只用于标题。不要仅仅是为了产生粗体或大号的文本而使用标题。
- 搜索引擎使用标题为您的网页的结构和内容编制索引。
- 因为用户可以通过标题来快速浏览您的网页，所以用标题来呈现文档结构是很重要的。
- 应该将h1用作主标题（最重要的），其后是h2（次重要的），再其次是h3，以此类推。

<hr></hr>

**HTML水平线**

`<hr/>`标签在HTML页面中创建水平线。

hr元素可用于分隔内容。

**实例**

```html
<h1>This is a heading</h1>
<hr/>
<h2>This is a heading</h2>
<hr/>
<h3>This is a heading</h3>
```

> 说明：使用水平线（<hr>标签）来分隔文章中的小节是一个办法（但并不睡唯一的办法）。

<hr/>

#### HTML提示 - 如何查看源代码

您一定曾经在看到某个网页时惊叹道 “WOW! 这是如何实现的？”

如果您想找到其中的奥秘，只需要单击右键，然后选择“查看源文件”（IE）或“查看页面源代码”（Chrome），其他浏览器的做法也是类似的。这么做会打开一个包含页面 HTML 代码的窗口。

<hr/>

### HTML段落

**可以把HTML文档分割为若干段落**

<hr/>

**HTML段落**

段落是通过`<p>`标签定义的。

**实例**

```html
<p>This is a paragraph</p>
<p>This is another paragraph</p>
```

> 说明：浏览器会自动地在段落的前后添加空行。（`<p>`是块级元素）
>
> 提示：使用空的段落标记`<p></p>`去插入一个空行是一个坏习惯。用`<br/>`标签代替它！


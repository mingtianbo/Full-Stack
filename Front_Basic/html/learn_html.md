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

> **说明**：未来的HTML版本不允许省略结束标签。

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

> **说明**：居中排列标题。

**属性例子2：**

`<body>`：定义HTML文档的主体。

`<body bgcolor="yellow">`：拥有关于背景颜色的附加信息。

> **说明**：背景颜色。

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

> **说明**：浏览器会自动地在标题的前后添加空行。
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

> **说明**：使用水平线（<hr>标签）来分隔文章中的小节是一个办法（但并不睡唯一的办法）。

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

> **说明**：浏览器会自动地在段落的前后添加空行。（`<p>`是块级元素）
>
> **提示**：使用空的段落标记`<p></p>`去插入一个空行是一个坏习惯。用`<br/>`标签代替它！

<hr/>

#### 不要忘记结束标签

即使忘了使用结束标签，大多数浏览器也会正确地将HTML显示出来：

```html
<p>This is a paragraph
<p>This is another paragraph
```

上面的例子在大多数浏览器中都没有问题，但不要依赖这种做法。忘记使用结束标签会产生意想不到的结果和错误。

> **注释：**在未来的HTML版本中，不允许省略结束标签。
>
> **提示：**通过结束标签来关闭HTML是一种经得起未来考验的HTML编写方法。清楚地标记某个元素在何处开始，并在何处结束。

<hr/>

#### HTML折行

如果希望在不产生一个新段落的情况下进行换行（新行），请使用`<br/>`标签：

```html
<p>
  This is <br/>a para<br/>graph with line breaks
</p>
```

`<br/>`元素是一个空的HTML元素。由于关闭标签没有任何意义，因此它没有结束标签。

<hr/>

**`<br>`还是`<br/>`**

您也许会发现`<br>`与`<br/>`很相似。

但在未来的HTML版本中，不允许使用没有结束标签（闭合标签）的HTML元素。

即使`<br>`在所有浏览器中的显示都没有问题，使用`<br/>`也有更长远的保障。

<hr/>

**HTML输出 - 有用的提示**

我们无法确定 HTML 被显示的确切效果。屏幕的大小，以及对窗口的调整都可能导致不同的结果。

对于 HTML，您无法通过在 HTML 代码中添加额外的空格或换行来改变输出的效果。

当显示页面时，浏览器会移除*源代码中*多余的空格和空行。所有连续的空格或空行都会被算作一个空格。需要注意的是，HTML 代码中的所有连续的空行（换行）也被显示为一个空格。

### Test

1. 在HTML代码中，排版一首唐诗

## 03

### HTML样式

**HTML的`style`属性**

style属性的作用：

**提供了一种改变所有HTML元素的样式的通用方法。**

通过 HTML 样式，能够通过使用 style 属性直接将样式添加到 HTML 元素，或者间接地在独立的样式表中（CSS 文件）进行定义。

您可以在我们的 [CSS 教程](https://www.w3school.com.cn/css/index.asp)中学习关于样式和 CSS 的所有知识。

在我们的 HTML 教程中，我们将使用 style 属性向您讲解 HTML 样式。

<hr/>

#### 背景颜色

`background-color`属性为元素定义了背景颜色：

```html
<html>
  	<body style="background-color:yellow">
      	<h2 style="background-color:red">This is a heading</h2>
      	<p style="background-color:green">This is a paragraph</p>
  	</body>
</html>
```

<hr/>

#### 字体、颜色和尺寸

`font-family`、`color`以及`font-size`属性分别定义元素中文本的字体系列、颜色和字体尺寸：

```html
<html>
		<body>
				<h1 style="font-family:verdana">A heading</h1>
				<p style="font-family:arial;color:red;font-size:20px;">A paragraph.</p>
		</body>
</html>
```

<hr/>

#### 文本对齐

`text-align`属性规定了元素中文本的水平对齐方式：

```html
<html>
		<body>
				<h1 style="text-align:center">This is a heading</h1>
				<p>The heading above is aligned to the center of this page.</p>
		</body>
</html>
```

<hr/>

### HTML格式化

HTML可定义很多供格式化输出的元素，比如粗体和斜体字。这里列出部分供参考。

#### 文本格式化标签

| 标签       | 描述           |
| ---------- | -------------- |
| `<b>`      | 定义粗体文本。 |
| `<big>`    | 定义大号字。   |
| `<em>`     | 定义着重文字。 |
| `<i>`      | 定义斜体字。   |
| `<small>`  | 定义小号字。   |
| `<strong>` | 定义加重语气。 |
| `<sub>`    | 定义下标字。   |
| `<sup>`    | 定义上标字。   |
| `<ins>`    | 定义插入字。   |
| `<del>`    | 定义删除字。   |
| `<style>`  | 定义样式。     |

<hr/>

#### “计算机输出“标签

| 标签     | 描述                 |
| -------- | -------------------- |
| `<code>` | 定义计算机代码。     |
| `<kbd>`  | 定义键盘码。         |
| `<samp>` | 定义计算机代码样本。 |
| `<tt>`   | 定义打字机代码。     |
| `<var>`  | 定义变量。           |
| `<pre>`  | 定义预格式文本。     |

<hr/>

#### 引用和术语定义

| 标签           | 描述               |
| -------------- | ------------------ |
| `<abbr>`       | 定义缩写。         |
| `<acronym>`    | 定义首字母缩写。   |
| `<address>`    | 定义地址。         |
| `<bdo>`        | 定义文字方向。     |
| `<blockquote>` | 定义长的引用。     |
| `<q>`          | 定义短的引用语。   |
| `<cite>`       | 定义引用、引证。   |
| `<dfn>`        | 定义一个定义项目。 |

#### 文本格式化实例

见text_ini.html

<hr/>

## 04

### HTML注释

HTML中用`<!--` 与` -->`插入注释。

浏览器不会显示注释，但是能够帮助记录您的HTML文档。

你可以利用注释在HTML中放置通知和提醒信息：

```html
<!-- 这是一段注释 -->
<p>这是一个段落。</p>
<!-- 记得在此添加信息 -->
```

<hr/>

注释对于HTML纠错也大有帮助，因为您可以一次注释一行HTML代码，以搜索错误：

```html
<!-- 此刻不显示图片：
<img border="0" src="/i/tulip_ballade.jpg" alt="Tulip">
-->
```

<hr/>

**条件注释**

可以在HTML中偶尔发现条件注释：

```html
<!--[if IE 8]>
		... some HTML here ...
<![endif]-->
```

条件注释定义只有_Internet Explorer_ 执行的HTML标签。

<hr/>

**软件程序标签**

各种HTML软件程序也能够生成HTML注释。

例如`<!--webbot bot-->`标签会被包围在由`FrontPage`和`Expression Web`构建的HTML注释中。作为一项规则，这些标签的存在，有助于对创建这些标签的软件的支持。

<hr/>

### HTML CSS

#### 使用样式

当浏览器读到一个样式表，它就会按照这个样式表来对文档进行格式化。有以下三种方式来插入样式表：

**外部样式表**

当样式需要被应用到很多页面的时候，外部样式表将是理想的选择。使用外部样式表，你就可以通过更改一个条件来改变整个站点的外观。

```html
<head>
  <link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

**内部样式表**

当单个文件需要特别样式时，就可以使用内部样式表。你可以在`head`部分通过`<style>`标签定义内部样式表。

```html
<head>
  <style type="text/css">
  body {background-color: red}
  p {margin-left: 20px}
  </style>
</head>
```

**内联样式**

当特殊的样式需要应用到个别元素时，就可以使用内联样式。使用内联样式的方法是在相关的标签中使用样式属性。样式属性可以包含各种任何CSS属性。以下实例显示出如何改变段落的颜色和左外边距。

```html
<p style="color: red; margin-left: 20px">
This is a paragraph
</p>
```

访问我们的 [CSS 教程](https://www.w3school.com.cn/css/index.asp)，学习更多有关样式的知识。

<hr/>

| 标签         | 描述                                           |
| ------------ | ---------------------------------------------- |
| `<style>`    | 定义样式定义。                                 |
| `<link>`     | 定义资源引用。                                 |
| `<div>`      | 定义文档中的节或区域（块级）。                 |
| `<span>`     | 定义文档中的行内的小块或区域。                 |
| `<font>`     | 规定文本的字体、字体尺寸、字体颜色。（不推荐） |
| `<basefont>` | 定义基准字体。（不推荐）                       |
| `<center>`   | 对文本进行水平居中。（不推荐）                 |

这一节中的实例参见css_test.html

<hr/>

### HTML链接

HTML使用超级链接与网络上的另一个文档相连。

几乎可以在所有的网页中找到链接。点击链接可以从一张页面跳转到另一张页面。

<hr/>

#### 超链接

超链接可以是一个字，一个词，或者一组词，也可以是一副图像，你可以点击这些内容来跳转到新的文档或者当前文档中的某个部分。

当你把鼠标指针移动到网页中的某个链接上时，箭头会变成一只小手。

我们通过使用`<a>`标签在HTML中创建链接。

有两种使用`<a>`标签的方式：

1. 通过使用`href`属性 - 创建指向另一个文档的链接
2. 通过使用`name`属性 - 创建文档内的书签

<hr/>

#### 语法

链接的HTML代码很简单：

```html
<a href="url">Link text</a>
```

`href`属性规定链接的目标。

开始标签和结束标签之间的文字被作为超链接来显示。

**实例**

```html
<a href="http://www.w3school.com.cn/">Visit W3School</a>
```

<hr/>

#### `target`属性

如果你亲自运行了上面的实例，你就会发现，当点开那个超链接之后，会直接在当前页面显示新页面。

这时，使用`Target`属性，你可以定义被链接的文档在何处显示。

下面的这行会在新窗口打开文档：

```html
<a href="http://www.w3school.com.cn/" target="_blank">Visit W3chool!</a>
```

<hr/>

#### `name`属性

`name`属性规定锚（anchor）的名称。

你可以使用`name`属性创建HTML页面中的书签。

书签不会以任何特殊方式显示，它对读者是不可见的。

当使用命名锚（named anchors）时，我们可以创建直接跳至该命名锚（比如页面中某个小节）的链接，这样使用者就无需不停地滚动页面来寻找他们需要的信息了。

**命名锚的语法**

```html
<a name="lable">锚（显示在页面上的文本）</a>
```

> **注释：**锚的名字可以是任何你喜欢的名字。
>
> **提示：**你可以使用`id`属性来替代`name`属性，命名锚同样有效。

**实例**

首先，我们在HTML文档中对锚进行命名（创建一个书签）：

```html
<a name="tips">基本的注意事项 - 有用的提示</a>
```

然后，我们在同一个文档中创建指向该锚的链接：

```html
<a href="#tips">有用的提示</a>
```

你也可以在其他页面中创建指向该锚的链接：

```html
<a href="http://www.w3school.com.cn/html/html_links.asp#tips">有用的提示</a>
```

在上面的代码中，我们将`#`符号和锚名称添加到`URL`的末端，就可以直接链接到`tips`这个命名锚了。

<hr/>

**基本的注意事项 - 有用的提示：**

**注释：**请始终将正斜杠添加到子文件夹。假如这样书写链接：href="http://www.w3school.com.cn/html"，就会向服务器产生两次 HTTP 请求。这是因为服务器会添加正斜杠到这个地址，然后创建一个新的请求，就像这样：href="http://www.w3school.com.cn/html/"。

**提示：**命名锚经常用于在大型文档开始位置上创建目录。可以为每个章节赋予一个命名锚，然后把链接到这些锚的链接放到文档的上部。如果您经常访问百度百科，您会发现其中几乎每个词条都采用这样的导航方式。

**提示：**假如浏览器找不到已定义的命名锚，那么就会定位到文档的顶端。不会有错误发生。

<hr/>

#### 实例演示

见link.html

## 05

### HTML图像

#### 标签和源属性

在HTML中，图像由`<img>`标签定义。

`<img>`是空标签，意思是说，它只包含属性，并且没有闭合标签。

要在页面上显示图像，你需要使用源属性（src）。`src`指“source”。源属性的值是图像的URL地址。

定义图像的语法是：

```html
<img src="url"/>
```

URL指存储图像的位置。如果名为"boat.gif"的图像位于`www.w3school.com.cn`的`images`目录中，那么其URL为`http://www.w3school.com.cn/images/boat.gif`。

浏览器将图像显示在文档中图像标签出现的地方。如果你将图像标签置于两个段落之间，那么浏览器会首先显示第一个段落，然后显示图片，最后显示第二段。

<hr/>

#### 替换文本属性

`alt`属性用来为图像定义一串预备的可替换的文本。替换文本属性的值是用户定义的。

```html
<img src="boat.gif" alt="Big Boat">
```

在浏览器无法载入图像时，替换文本属性告诉读者他们失去的信息。此时，浏览器将显示这个替代性的文本而不是图像。为页面上的图像都加上替换文本属性是个好习惯，这样有助于更好的显示信息，并且对于那些使用纯文本浏览器的人来说是非常有用的。

**有用的提示**

假如某个HTML文件包含十个图像，那么为了正确显示这个页面，需要加载11个文件。加载图片是需要时间的，所以我们的建议是：慎用图片！

<hr/>

#### 实例

见image_test.html

<hr/>

### HTML表格

#### 表格

表格由`<table>`标签来定义。每个表格均有若干行（由`<tr>`标签定义），每行被分割为若干单元格（由`<td>`标签定义）。字母`td`指表格数据（table data），即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。

```html
<table>
  <tr>
    <td>row 1, cell 1</td>
    <td>row 1, cell 2</td>
  </tr>
  <tr>
    <td>row 2, cell 1</td>
    <td>row 2, cell 2</td>
  </tr>
</table>
```

<hr/>

#### 属性

如果不定义边框属性，表格将不显示边框。有时这很有用，但是大多数时候，我们希望显示边框。

使用边框属性来显示一个带有边框的表格：

```html
<table border="1">
  <tr>
    <td>row 1, cell 1</td>
    <td>row 1, cell 2</td>
  </tr>
  <tr>
    <td>row 2, cell 1</td>
    <td>row 2, cell 2</td>
  </tr>
</table>
```

<hr/>

#### 表头

表格的表头使用`<th>`标签来进行定义。

大多数浏览器会把表头显示为粗体居中的文本：

```html
<table border="1">
  <tr>
    <th>Heading</th>
    <th>Another Heading</th>
  </tr>
  <tr>
    <td>row 1, cell 1</td>
    <td>row 1, cell 2</td>
  </tr>
  <tr>
    <td>row 2, cell 1</td>
    <td>row 2, cell 2</td>
  </tr>
</table>
```

<hr/>

#### 空单元格

在一些浏览器中，没有内容的表格单元显示得不太好。如果某个单元格是空的（没有内容），浏览器可能无法显示出这个单元格的边框。

```html
<table border="1">
	<tr>
		<td>row 1, cell 1</td>
		<td>row 1, cell 2</td>
	</tr>
	<tr>
		<td></td>
		<td>row 2, cell 2</td>
	</tr>
</table>
```

**注意：**上面的空单元格的边框没有被显示出来。为了避免这种情况，在空单元格中添加一个空格占位符，就可以将边框显示出来。

```html
<table border="1">
	<tr>
		<td>row 1, cell 1</td>
		<td>row 1, cell 2</td>
	</tr>
	<tr>
		<td>&nbsp;</td>
		<td>row 2, cell 2</td>
	</tr>
</table>
```

<hr/>

#### 实例

见tablemore.html

<hr/>

## 06

### HTML列表

HTML支持有序、无序和定义列表

#### 无序列表

无序列表是一个项目的列表，此列项目使用粗体圆点进行标记。

无序列表始于`<ul>`标签。每个列表项始于`<li>`。

```html
<ul>
  <li>Coffee</li>
  <li>Milk</li>
</ul>
```

浏览器显示如下：

- Coffee
- Milk

列表项内部可以使用段落、换行符、图片、链接以及其他列表等等。

<hr/>

#### 有序列表

同样，有序列表也是一列项目，列表项目使用数字进行标记。

有序列表始于`<ol>`标签。每个列表项始于`<li>`标签。

```html
<ol>
  <li>Coffee</li>
  <li>Milk</li>
</ol>
```

浏览器会显示如下：

1. Coffee
2. Milk

列表项内部可以使用段落、换行符、图片、链接以及其他列表等等。

<hr/>

#### 定义列表

自定义列表不仅仅是一列项目，而是项目及其注释的组合。

自定义列表以`<dl>`标签开始。每个自定义列表项以`<dt>`开始。每个自定义列表项的定义以`<dd>`开始。

```html
<dl>
  <dt>Coffee</dt>
  <dd>Black hot drink</dd>
  <dt>Milk</dt>
  <dd>White cold drink</dd>
</dl>
```

定义列表的列表项内部可以使用段落、换行符、图片、链接以及其他列表等等。

<hr/>

#### 实例

见list_test.html

<hr/>

### HTML 的块

可以通过`<div>`和`<span>`将HTML元素组合起来。

#### HTML块元素

大多数 HTML 元素被定义为块级元素或内联元素。

>  **注释**：“块级元素”译为`block level element`，“内联元素”译为`inline element`。

块级元素在浏览器显示时，通常会以新行来开始（和结束）。

例子：`<h1>`, `<p>`,` <ul>`,` <table>`

<hr/>

#### HTML内联元素

内联元素在显示时通常不会以新行开始。

例子：`<b>`,` <td>`, `<a>`,` <img>`

<hr/>

#### HTML `<div>`元素

HTML`<div>`元素是块级元素，它是可用于组合其他 HTML 元素的容器。

<div> 元素没有特定的含义。除此之外，由于它属于块级元素，浏览器会在其前后显示折行。

如果与 CSS 一同使用，`<div>`元素可用于对大的内容块设置样式属性。

`<div>`元素的另一个常见的用途是文档布局。它取代了使用表格定义布局的老式方法。使用 `<table> `元素进行文档布局不是表格的正确用法。`<table> `元素的作用是显示表格化的数据。

<hr/>

#### HTML `<span>`元素

HTML`<span>`元素是内联元素，可用作文本的容器。

`<span>`元素也没有特定的含义。

当与 CSS 一同使用时，`<span>`元素可用于为部分文本设置样式属性。

<hr/>

### HTML类

对 HTML 进行分类（设置类），使我们能够为元素的类定义 CSS 样式。

为相同的类设置相同的样式，或者为不同的类设置不同的样式。

<iframe src="https://www.w3school.com.cn/demo/html_classes_london.asp" width="500" height="330" style="margin: 0px; padding: 0px; border: 0px;"></iframe>

**实例**

```html
<!DOCTYPE html>
<html>
<head>
<style>
.cities {
    background-color:black;
    color:white;
    margin:20px;
    padding:20px;
} 
</style>
</head>

<body>

<div class="cities">
<h2>London</h2>
<p>
London is the capital city of England. 
It is the most populous city in the United Kingdom, 
with a metropolitan area of over 13 million inhabitants.
</p>
</div> 

</body>
</html>
```

<hr/>

#### 分类块级元素

HTML` <div> `元素是*块级元素*。它能够用作其他 HTML 元素的容器。

设置 `<div>` 元素的类，使我们能够为相同的 `<div>` 元素设置相同的类：

<iframe src="https://www.w3school.com.cn/demo/html_classes_cities.asp" width="500" height="1020" style="margin: 0px; padding: 0px; border: 0px;"></iframe>

**实例**

```html
<!doctype html>
<html>
<head>
<style>
.cities {
    background-color:black;
    color:white;
    margin:20px;
    padding:20px;
} 
</style>
</head>

<body>

<div class="cities">
<h2>London</h2>
<p>London is the capital city of England. 
It is the most populous city in the United Kingdom, 
with a metropolitan area of over 13 million inhabitants.</p>
</div>

<div class="cities">
<h2>Paris</h2>
<p>Paris is the capital and most populous city of France.</p>
</div>

<div class="cities">
<h2>Tokyo</h2>
<p>Tokyo is the capital of Japan, the center of the Greater Tokyo Area,
and the most populous metropolitan area in the world.</p>
</div>

</body>
</html>
```

<hr/>

#### 分类行内元素

HTML`<span>`元素是行内元素，能够用作文本的容器。

设置 `<span>`元素的类，能够为相同的` <span>`元素设置相同的样式。

**实例**

```html
<!DOCTYPE html>
<html>
<head>
<style>
  span.red {color:red;}
</style>
</head>
<body>

<h1>My <span class="red">Important</span> Heading</h1>

</body>
```

## 07

### HTML布局

网站常常以多列显示内容（就像杂志和报纸）。

<iframe src="https://www.w3school.com.cn/demo/html_layout_divs.asp" width="680" height="450" style="margin: 0px; padding: 0px; border: 0px;"></iframe>

<hr/>

#### 使用`<div>`元素

**注释：**`<div>`元素常用作布局工具，因为能够轻松地通过`CSS`对其进行定位。

上面那张图的例子使用了四个`<div>`元素来创建多列布局：

```html
<body>
  <div id="header">
    <h1>
      City Gallery
    </h1>
  </div>
  
  <div id="nav">
    London<br>
    Paris<br>
    Tokyo<br>
  </div>
  
  <div id="section">
    <h1>
      London
    </h1>
    <p>
      London is the capital city of England.It is the most populous city in the United Kingdom,with a metropolitan area of over 13 million inhabitants.
    </p>
    <p>
      Standing on the River Thames,London has been a major settlement for two millennia,its history going back to its founding by the Romans,who named it Londinium.
    </p>
  </div>
  
  <div id="footer">
    Copyright W3School.com.cn
  </div>
</body>
```

CSS:

```html
<style>
  #header{
    background-color:black;
    color:white;
    text-align:center;
    padding:5px;
  }
  #nav{
    line-height:30px;
    background-color:#eeeeee;
    height:300px;
    width:100px;
    float:left;
    padding:5px;
  }
  #section{
    width:350px;
    float:left;
    padding:10px;
  }
  #footer{
    background-color:black;
    color:white;
    clear:both;
    text-align:center;
    padding:5px;
  }
</style>
```

<hr/>

#### 使用`HTML5`

`HTML5`提供的新语义元素定义了网页的不同部分：

**HTML5语义元素**

| 元素      | 解释                             |
| --------- | -------------------------------- |
| `header`  | 定义文档或节的页眉               |
| `nav`     | 定义导航链接的容器               |
| `section` | 定义文档中的节                   |
| `article` | 定义独立的自包含文章             |
| `aside`   | 定义你内容之外的内容（比如侧栏） |
| `footer`  | 定义文档或节的页脚               |
| `details` | 定义额外的细节                   |
| `summary` | 定义`details`元素的标题          |

这个例子使用`<header>`,`<nav>`,`<section>`,以及`<footer>`来创建多列布局：

**实例**

```html
<body>

<header>
<h1>City Gallery</h1>
</header>

<nav>
London<br>
Paris<br>
Tokyo<br>
</nav>

<section>
<h1>London</h1>
<p>
London is the capital city of England. It is the most populous city in the United Kingdom,
with a metropolitan area of over 13 million inhabitants.
</p>
<p>
Standing on the River Thames, London has been a major settlement for two millennia,
its history going back to its founding by the Romans, who named it Londinium.
</p>
</section>

<footer>
Copyright W3School.com.cn
</footer>

</body>
```

CSS

```html
<style>
header {
    background-color:black;
    color:white;
    text-align:center;
    padding:5px; 
}
nav {
    line-height:30px;
    background-color:#eeeeee;
    height:300px;
    width:100px;
    float:left;
    padding:5px; 
}
section {
    width:350px;
    float:left;
    padding:10px; 
}
footer {
    background-color:black;
    color:white;
    clear:both;
    text-align:center;
    padding:5px; 
}
</style>
```

<hr/>

#### 使用表格

**注释：**`<table>`元素不是作为布局工具而设计的。

`<table>`元素的作用是显示表格化的数据。

使用`<table>`元素能够取得布局效果，因为能够通过CSS设置表格元素的样式：

```html
<body>
  <table class="lamp">
    <tr>
      <th>
        <img src="" alt="Note" style="height:32px;width:32px">
      </th>
     	<td>
        The table element was not designed to be a layout tool.
      </td>
    </tr>
  </table>
</body>
```

CSS

```html
<style>
  table.lamp{
    width:100%;
    border:1px solid #d4d4d4;
  }
  table.lamp th,td{
    padding:10px;
  }
  table.lamp td{
    width:40px;
  }
</style>
```

### HTML响应式Web设计

**什么是响应式Web设计？**

- RWD指的是响应式Web设计（Responsive Web Design）
- RWD能够以可变尺寸传递网页
- RWD对于平板和移动设备是必需的

<hr/>

#### 创建

创建响应式设计的一个方法，是自己来创建它：

```html
<!doctype html>
<html lang="en-US">
  <head>
    <style>
      .city{
        float:left;
        margin:5px;
        padding:15px;
        width:300px;
        height:300px;
        border:1px solid black;
      }
    </style>
  </head>
  <body>
    <h1>
      W3School Demo
    </h1>
    <h2>
      Resize this responsive page!
    </h2>
    <br>
    
    <div class="city">
      <h2>
        London
      </h2>
      <p>
        London is the capital city of England.
      </p>
      <p>
        It is the most populous city in the United Kingdom,with a metropolitan area of over 13 million inhabitants.
      </p>
    </div>
    
    <div class="city">
      <h2>
        Paris
      </h2>
      <p>
        Paris is the capital and most populous city of France.
      </p>
    </div>
    
    <div class="city">
      <h2>
        Tokyo
      </h2>
      <p>
        Tokyo is the capital of Japan,the center of the Greater Tokyo Area,and the most populous metropolitan area in the world.
      </p>
    </div>
  </body>
</html>
```

<hr/>

#### 使用Bootstrap

另一个创建响应式设计的方法，是使用线程的CSS框架。

Bootstrap是最流行的开发响应式web的HTML，CSS和JS框架。

Bootstrap帮助您开发在任何尺寸都外观出众的站点：显示器、笔记本电脑、平板电脑或手机。

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="http://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
  </head>

  <body>
    <div class="container">
      <div class="jumbotron">
        <h1>W3School Demo</h1> 
        <p>Resize this responsive page!</p> 
      </div>
    </div>

    <div class="container">
      <div class="row">
        <div class="col-md-4">
          <h2>London</h2>
          <p>London is the capital city of England.</p>
          <p>It is the most populous city in the United Kingdom,
          with a metropolitan area of over 13 million inhabitants.</p>
        </div>
        <div class="col-md-4">
          <h2>Paris</h2>
          <p>Paris is the capital and most populous city of France.</p>
        </div>
        <div class="col-md-4">
          <h2>Tokyo</h2>
          <p>Tokyo is the capital of Japan, the center of the Greater Tokyo Area,
          and the most populous metropolitan area in the world.</p>
        </div>
      </div>
    </div>
  </body>
</html>
```

<hr/>

## 08

### HTML框架

通过使用框架，你可以在同一个浏览器窗口中显示不止一个页面。

#### 框架

每份HTML文档称为一个框架，并且每个框架都独立于其他的框架。

使用框架的坏处：

- 开发人员必须同时跟踪更多的HTML文档
- 很难打印整张页面

<hr/>

#### 结构标签

**框架结构标签（`<frameset>`）**

- 框架结构标签（`<frameset>`）定义如何将窗口分割为框架
- 每个`frameset`定义了一系列行或列
- `rows/columns`的值规定了每行或每列占据屏幕的面积

<hr/>

#### 框架标签

**`<frame>`**

Frame标签定义了放置在每个框架中的HTML文档。

在下面的这个例子中，我们设置了一个两列的框架集。第一列被设置为占据浏览器窗口的25%。第二列被设置为占据浏览器窗口的75%。HTML文档"frame_a.htm"被置于第一个列中，而HTML文档"frame_b.htm"被置于第二个列中：

```html
<frameset cols="25%, 75%">
  <frame src="frame_a.html">
  <frame src="frame_b.html">
</frameset>
```

<hr/>

**基本的注意事项 - 有用的提示：**

假如一个框架有可见边框，用户剋一拖动边框来改变它的大小。为了避免这种情况发生，可以在`<frame>`标签中加入：`noresize="noresize"`。

为不支持框架的浏览器添加`<noframes>`标签，为了打印相应字段。

**重要提示：**不能将`<body></body>`标签与`<frameset></frameset>`标签同时使用！不过，假如你添加包含一段文本的`<noframes>`标签，就必须将这段文字嵌套于`<body></body>`标签内。

<hr/>

**实例**

见Day8源代码。

<hr/>

### HTML Iframe

iframe用于在网页内显示网页。

**iframe语法**

```html
<iframe src="URL"></iframe>
```

URL指向隔离页面的位置。

<hr/>

#### Iframe - 设置高度和宽度

`height`和`width`属性用于规定`iframe`的高度和宽度。

属性值的默认单位是像素，但也剋一用百分比来设定（比如“80%”）。

```html
<iframe src="frame_a.html" width="200" height="200"></iframe>
```

<hr/>

#### Iframe - 删除边框

`frameborder`属性规定是否显示`iframe`周围的边框。

蛇追属性值为“0”就可以移除边框：

```html
<iframe src="frame_a.html" frameborder="0"></iframe>
```

<hr/>

#### 使用iframe作为链接的目标

iframe可用作链接的目标（target）。

链接的target属性必须引用iframe的name属性。

```html
<iframe src="frame_a.html" name="iframe_a"></iframe>
<p>
  <a href="http://www.w3school.com.cn" target="iframe_a">W3School.com.cn</a>
</p>
```

## 09

### HTML路径

| 路径                              | 描述                                          |
| --------------------------------- | --------------------------------------------- |
| `<img src="picture.jpg">`         | `picture.jpg`位于与当前网页相同的文件夹       |
| `<img src="images/picture.jpg">`  | `picture.jpg`位于当前文件夹的`images`文件夹中 |
| `<img src="/images/picture.jpg">` | `picture.jpg`当前站点根目录的`images`文件夹中 |
| `img src="../picture.jpg"`        | `picture.jpg`位于当前文件夹的上一级文件夹中   |

<hr/>

#### HTML文件路径

文件路径描述了网站文件夹结构中某个文件的位置。

文件路径会在链接外部文件时被用到：

- 网页
- 图像
- 样式表
- JavaScript

<hr/>

#### 绝对文件路径

绝对文件路径是指向一个因特网文件的完整`URL`：

**实例**

```html
<img src="http://www.w3school.com.cn/images/picture.jpg" alt="flower">
```

`<img>`标签以及`src`和`alt`属性在HTML图像这一章做了讲解。

<hr/>

#### 相对路径

相对路径指向了相对于当前页面的文件。

**实例**

```html
<img src="/images/picture.jpg" alt="flower">
```

在本例中，文件路径指向了位于当前网站根目录中`images`文件夹里的一个文件

**实例**

```html
<img src="images/picture.jpg" alt="flower">
```

在本例中，文件路径指向了位于当前文件夹中`images`文件夹里的一个文件

**实例**

```html
<img src="../images/picture.jpg" alt="flower">
```

在本例中，文件路径指向了位于当前文件夹的上一级文件夹中的`images`文件夹里的一个文件

<hr/>

#### 好习惯

使用相对路径是个好习惯（如果可能）。

如果使用了相对路径，那么您的网页就不会与当前的基准URL进行绑定。所有链接在您的电脑上（localhost）或未来的公共域中均可正常工作。

<hr/>

### HTML头部元素

#### `<head>`元素

`<head>`元素是所有头部元素的容器。`<head>`内的元素可包含脚本，指示浏览器在何处可以找到样式表，提供元信息，等等。

以下标签都可以添加到`head`部分：`<title>`、`<base>`、`<link>`、`<meta>`、`<script>`以及`<style>`。

<hr/>

#### `<title>`元素

`<title>`标签定义文档的标题。

`title`元素在所有HTML文档中都是必需的。

`title`元素能够：

- 定义浏览器工具栏中的标题
- 提供页面被添加到收藏夹时显示的标题
- 显示在搜索引擎结果中的页面标题

一个简化的HTML文档：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Title of the document</title>
  </head>
  
  <body>
    The content of the document...
  </body>
</html>
```

<hr/>

#### `<base>`元素

`<base>`标签为页面上的所有链接规定默认地址或默认目标（target）：

```html
<head>
  <base href="http://www.w3school.com.cn/images/"/>
  <base target="_blank"/>
</head>
```

<hr/>

#### `<link>`元素

`<link>`标签定义文档与外部资源之间的关系。

`<link>`标签最常用于连接样式表：

```html
<head>
  <link rel="stylesheet" type="text/css" href="mystyle.css"/>
</head>
```

<hr/>

#### `<style>`元素

`<style>`标签用于为HTML文档定义样式信息。

您可以在`style`元素内规定HTML元素在浏览器中呈现的样式

```html
<head>
  <style type="text/css">
    body{background-color:yellow}
    p{color:blue}
  </style>
</head>
```

<hr/>

#### `<meta>`元素

元数据（metadata）是关于数据的信息。

`<meta>`标签提供关于HTML文档的元数据。元数据不会显示在页面上，但是对于机器是可读的。

典型的情况是，`meta`元素被用于规定页面的描述、关键词、文档的作者、最后修改时间以及其他元数据。

`<meta>`标签始终位于`head`元素中。

元数据可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他web服务。

**针对搜索引擎的关键词**

一些搜索引擎会使用`meta`元素的`name`和`content`属性来索引您的页面。

下面的`meta`元素定义页面的描述：

```html
<meta name="description" content="Free Web tutorials on HTML,CSS,XML"/>
```

下面的`meta`元素定义页面的关键词：

```html
<meta name="keywords" content="HTML,CSS,XML"/>
```

`name`和`content`属性的作用是描述页面的内容。

<hr/>

#### `<script>`元素

`<script>`标签用于定义客户端脚本，比如JavaScript。

<hr/>

### HTML字符实体

HTML的预留字符必须被替换为字符实体。

#### HTML实体

在HTML中，某些字符是预留的。

在HTML中不能使用小于号（<）和大于号（>），这是因为浏览器会误认为它们是标签。

如果希望正确地显示预留字符，我们必须在HTML源代码中使用字符实体（character entities）

字符实体类似这样：

```html
&entity_name;
或者
&#entity_number;
```

如需显示小于号，我们必须这样写：`&lt`或`&#60`；

**提示：**使用实体名而不是数字的好处是，名称易于记忆。不过坏处是，浏览器也许并不支持所有实体名称（对实体数字的支持却很好）。

<hr/>

#### 不间断空格（non-breaking space）

HTML中的常用字符实体是不间断空格（`&nbsp;`）。

浏览器总是会截短HTML页面中的空格。如果您在文本中写10个空格，在显示该页面之前，浏览器会删除它们中的9个。如需在页面中增加空格的数量，您需要使用`&nbsp;`字符实体

<hr/>

#### 有用的字符实体

**注释：**实体名称对大小写敏感！

| 显示结果 | 描述            | 实体名称           | 实体编号  |
| -------- | --------------- | ------------------ | --------- |
| ` `      | 空格            | `&nbsp;`           | `&#160;`  |
| `<`      | 小于号          | `&lt;`             | `&#60;`   |
| `>`      | 大于号          | `&gt;`             | `&#62;`   |
| `&`      | 和号            | `&amp;`            | `&#38;`   |
| `"`      | 引号            | `&quot;`           | `&#34;`   |
| `'`      | 撇号            | `&apos;`(IE不支持) | `&#39;`   |
| `￠`     | 分(cent)        | `&cent;`           | `&#162;`  |
| `£`      | 磅(pound)       | `&pound;`          | `&#163;`  |
| `¥`      | 元(yen)         | `&yen;`            | `&#165;`  |
| `€`      | 欧元(euro)      | `&euro;`           | `&#8364;` |
| `§`      | 小节            | `&sect;`           | `&#167;`  |
| `©`      | 版权(copyright) | `&copy;`           | `&#169;`  |
| `®`      | 注册商标        | `&reg;`            | `&#174;`  |
| `™`      | 商标            | `&trade;`          | `&#8482;` |
| `×`      | 乘号            | `&times;`          | `&#215;`  |
| `÷`      | 除号            | `&divide;`         | `&#247;`  |

<hr/>

#### 实例

见entity_test.html

<hr/>

## 10

### HTML URL

URL也被称为网址。

URL可以由单词组成，比如 “w3school.com.cn”，或者是因特网协议（IP）地址：192.168.1.253。大多数人在网上冲浪时，会键入网址的域名，因为名称比数字容易记忆。

<hr/>

#### 简介

**URL - Uniform Resource Locator**

当您点击 HTML 页面中的某个链接时，对应的`<a>`标签指向万维网上的一个地址。

统一资源定位器（URL）用于定位万维网上的文档（或其他数据）。

网址，比如 http://www.w3school.com.cn/html/index.asp，遵守以下的语法规则：

```html
scheme://host.domain:port/path/filename
```

解释：

- `scheme` - 定义因特网服务的类型。最常见的类型是`http`
- `host` - 定义域主机（`http`的默认主机是`www`）
- `domain` - 定义因特网域名，比如`w3school.com.cn`
- `:port` - 定义主机上的端口号（`http` 的默认端口号是`80`）
- `path` - 定义服务器上的路径（如果省略，则文档必须位于网站的根目录中）。
- `filename` - 定义文档/资源的名称

<hr/>

#### Schemes

以下是一些最流行的`scheme`：

| Scheme  | 访问               | 用于...                             |
| ------- | ------------------ | ----------------------------------- |
| `http`  | 超文本传输协议     | 以`http://`开头的普通网页。不加密。 |
| `https` | 安全超文本传输协议 | 安全网页。加密所有信息交换。        |
| `ftp`   | 文件传输协议       | 用于将文件下载或上传至网站。        |
| `file`  |                    | 本人计算机上的文件。                |

<hr/>

#### 字符编码

- URL编码会将字符转换为可通过因特网传输的格式。

- URL 只能使用 [ASCII 字符集](https://www.w3school.com.cn/tags/html_ref_ascii.asp)来通过因特网进行发送。

- 由于 URL 常常会包含 ASCII 集合之外的字符，URL 必须转换为有效的 ASCII 格式。

- URL 编码使用 "%" 其后跟随两位的十六进制数来替换非 ASCII 字符。

- URL 不能包含空格。URL 编码通常使用 + 来替换空格。

如需完整的 URL 编码参考，访问的 [URL 编码参考手册](https://www.w3school.com.cn/tags/html_ref_urlencode.html)。

<hr/>

### HTML Web Server

如果希望向世界发布您的网站，那么必须把它存放在`web`服务器上。

#### 托管自己的网站

在自己的服务器上托管网站始终是一个选项。有几点需要考虑：

**硬件支出**

如果要运行“真正”的网站，您不得不购买强大的服务器硬件。不要指望低价的 PC 能够应付这些工作。您还需要稳定的（一天 24 小时）高速连接。

**软件支出**

请记住，服务器授权通常比客户端授权更昂贵。同时请注意，服务器授权也许有用户数量限制。

**人工费**

不要指望低廉的人工费用。您必须安装自己的硬件和软件。您同时要处理漏洞和病毒，以确保您的服务器时刻正常地运行于一个“任何事都可能发生”的环境中。

#### 使用因特网服务提供商（ISP）

从 ISP 租用服务器也很常见。

大多数小公司会把网站存放到由 ISP 提供的服务器上。其优势有以下几点：

**连接速度**

大多数 ISP 都拥有连接因特网的高速连接。

**强大的硬件**

ISP 的 web 服务器通常强大到能够由若干网站分享资源。您还要看一下 ISP 是否提供高效的负载平衡，以及必要的备份服务器。

**安全性和可靠性**

ISP 是网站托管方面的专家。他们应该提供 99% 以上的在线时间，最新的软件补丁，以及最好的病毒防护。

#### 选择 ISP 时的注意事项

**24 小时支持**

确保 ISP 提供 24 小时支持。不要使自己置于无法解决严重问题的尴尬境地，同时还必须等待第二个工作日。如果您不希望支付长途电话费，那么免费电话服务也是必要的。

**每日备份**

确保 ISP 会执行每日备份的例行工作，否则您有可能损失有价值的数据。

**流量**

研究一下 ISP 的流量限制。如果出现由于网站受欢迎而激增的不可预期的访问量，那么您要确保不会因此支付额外费用。

**带宽或内容限制**

研究一下 ISP 的带宽和内容限制。如果您计划发布图片或播出视频或音频，请确保您有此权限。

**E-mail 功能**

请确保 ISP 支持您需要的 e-mail 功能。

**数据库访问**

如果您计划使用网站数据库中的数据，那么请确保您的 ISP 支持您需要的数据库访问。

### HTML颜色

具体见[颜色][https://www.w3school.com.cn/html/html_colors.asp]、[颜色名][https://www.w3school.com.cn/html/html_colornames.asp]

<hr/>

## 11

### HTML XHTML

#### XHTML简介

XHTML是以XML格式编写的HTML。

**什么是XHTML？**

- XHTML指的是可扩展文本标记语言
- XHTML与HTML4.01几乎是相同的
- XHTML是更严格更纯净的HTML版本
- XHTML是以XML应用的方式定义的HTML
- XHTML是2001年1月发布的W3C推荐标准
- XHTML得到所有主流浏览器的支持

<hr/>

**为什么使用XHTML？**

因特网上的很多页面包含了“糟糕”的HTML。

如果在浏览器中查看，下面的HTML代码运行起来非常正常（即使它并未遵守HTML规则）：

```html
<html>
  <head>
    <title>This is bad HTML</title>
  <body>
    <h1>Bad HTML
    <p>This is a paragraph
    </body>
```

XML是一种必须正确标记且格式良好的标记语言。

通过结合XML和HTML的长处，开发出了XHTML。XHTML是作为XML被重新设计的HTML。

与HTML相比最重要的区别是：

- **文档结构**
  - `XHTML DOCTYPE`是**强制性的**。
  - `<html>`中的`XML namespace`属性是**强制性的**。
  - `<html>`、`<head>`、`<title>`以及`<body>`也是**强制性的**。
- **元素语法**
  - XHTML元素必须是**正确嵌套**。
  - XHTML元素必须始终**关闭**。
  - XHTML元素必须**小写**。
  - XHTML文档必须有一个**根元素**。
- **属性语法**
  - XHTML属性必须用**小写**。
  - XHTML属性值必须用**引号包围**。
  - XHTML属性最小化也是**禁止的**。

<hr/>

**`<!DOCTYPE ...>`是强制性的**

XHTML 文档必须进行 XHTML 文档类型声明（XHTML DOCTYPE declaration）。

您可以在 W3School 的标签参考手册中找到完整的 [XHTML 文档类型](https://www.w3school.com.cn/tags/tag_doctype.asp)。

`<html>`、`<head>`、`<title> `以及` <body>` 元素也必须存在，并且必须使用 `<html>` 中的 xmlns 属性为文档规定 xml 命名空间。

下面的例子展示了带有最少的必需标签的 XHTML 文档：

```xhtml
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<html xmlns="http://www.w3.org/1999/xhtml">

<head>
<title>Title of document</title>
</head>

<body>
......
</body>

</html>
```

<hr/>

**如何从HTML转换到XHTML**

1. 向每张页面的第一行添加XHTML`<!DOCTYPE>`
2. 向每张页面的`html`元素添加`xmlns`属性
3. 把所有元素名改为小写
4. 关闭所有空元素
5. 把所有属性名改为小写
6. 为所有属性值加引号

<hr/>

#### XHTML元素

XHTML元素是以XML格式编写的HTML元素。

**XHTML元素 - 语法规则**

- XHTML元素必须**正确嵌套**
- XHTML元素必须始终**关闭**
- XHTML元素必须**小写**
- XHTML文档必须有一个**根元素**

<hr/>

**XHTML 元素必须正确嵌套**

在 HTML 中，某些元素可以不正确地彼此嵌套在一起，就像这样：

```xhtml
<b><i>This text is bold and italic</b></i>
```

在 XHTML 中，所有元素必须正确地彼此嵌套，就像这样：

```xhtml
<b><i>This text is bold and italic</i></b>
```

<hr/>

**XHTML 元素必须始终关闭**

这是错误的：

```xhtml
<p>This is a paragraph
<p>This is another paragraph
```

这是正确的：

```xhtml
<p>This is a paragraph</p>
<p>This is another paragraph</p>
```

<hr/>

**空元素也必须关闭**

这是错误的：

```xhtml
A break: <br>
A horizontal rule: <hr>
An image: <img src="happy.gif" alt="Happy face">
```

这是正确的：

```xhtml
A break: <br />
A horizontal rule: <hr />
An image: <img src="happy.gif" alt="Happy face" />
```

<hr/>

**XHTML 元素必须小写**

这是错误的：

```xhtml
<BODY>
<P>This is a paragraph</P>
</BODY>
```

这是正确的：

```xhtml
<body>
<p>This is a paragraph</p>
</body>
```

#### XHTML属性

XHTML属性是以XML格式编写的HTML属性。

**XHTML属性 - 语法规则**

- XHTML属性必须使用**小写**
- XHTML属性值必须使用**引号包围**
- XHTML属性最小化也是**禁止的**

<hr/>

**XHTML属性必须使用小写**

这是错误的：

```xhtml
<table WIDTH="100%">
```

这是正确的：

```xhtml
<table width="100%">
```

**XHTML 属性值必须用引号包围**

这是错误的：

```xhtml
<table width=100%>
```

这是正确的：

```xhtml
<table width="100%">
```

**禁止属性简写**

这是错误的：

```xhtml
<input checked>
<input readonly>
<input disabled>
<option selected>
```

这是正确的：

```xhtml
<input checked="checked" />
<input readonly="readonly" />
<input disabled="disabled" />
<option selected="selected" />
```

### HTML表单

#### HTML表单

**HTML 表单用于搜集不同类型的用户输入。**

**`<form>` 元素**

HTML 表单用于收集用户输入。

`<form>`元素定义 HTML 表单：

**实例**

```html
<form>
 .
form elements
 .
</form>
```

<hr/>

**HTML 表单包含*表单元素***

表单元素指的是不同类型的`input`元素、复选框、单选按钮、提交按钮等等。

<hr/>

**`<input>`元素**

`<input>`元素是最重要的**表单元素**。

`<input>`元素有很多形态，根据不同的`type`属性。

这是本章中使用的类型：

| 类型     | 描述                                 |
| :------- | :----------------------------------- |
| `text`   | 定义常规文本输入。                   |
| `radio`  | 定义单选按钮输入（选择多个选择之一） |
| `submit` | 定义提交按钮（提交表单）             |

<hr/>

**文本输入**

`<input type="text">`定义用于**文本输入**的单行输入字段：

**实例**

```html
<form>
 First name:<br>
<input type="text" name="firstname">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```

>  **注释：**表单本身并不可见。还要注意文本字段的默认宽度是 20 个字符。

<hr/>

**单选按钮输入**

`<input type="radio">`定义**单选按钮**。

单选按钮允许用户在有限数量的选项中选择其中之一：

**实例**

```html
<form>
<input type="radio" name="sex" value="male" checked>Male
<br>
<input type="radio" name="sex" value="female">Female
</form> 
```

<hr/>

**提交按钮**

`<input type="submit">`定义用于向**表单处理程序**（form-handler）**提交**表单的按钮。

表单处理程序通常是包含用来处理输入数据的脚本的服务器页面。

表单处理程序在表单的`action`属性中指定：

**实例**

```html
<form action="textfile">
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
```

<hr/>



## Action 属性

*action 属性*定义在提交表单时执行的动作。

向服务器提交表单的通常做法是使用提交按钮。

通常，表单会被提交到 web 服务器上的网页。

在上面的例子中，指定了某个服务器脚本来处理被提交表单：

```
<form action="action_page.php">
```

如果省略 action 属性，则 action 会被设置为当前页面。

## Method 属性

*method 属性*规定在提交表单时所用的 HTTP 方法（*GET* 或 *POST*）：

```
<form action="action_page.php" method="GET">
```

或：

```
<form action="action_page.php" method="POST">
```

## 何时使用 GET？

您能够使用 GET（默认方法）：

如果表单提交是被动的（比如搜索引擎查询），并且没有敏感信息。

当您使用 GET 时，表单数据在页面地址栏中是可见的：

```
action_page.php?firstname=Mickey&lastname=Mouse
```

**注释：**GET 最适合少量数据的提交。浏览器会设定容量限制。

## 何时使用 POST？

您应该使用 POST：

如果表单正在更新数据，或者包含敏感信息（例如密码）。

POST 的安全性更加，因为在页面地址栏中被提交的数据是不可见的。

## Name 属性

如果要正确地被提交，每个输入字段必须设置一个 name 属性。

本例只会提交 "Last name" 输入字段：

### 实例

```
<form action="action_page.php">
First name:<br>
<input type="text" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_form_submit_id)

## 用 <fieldset> 组合表单数据

*<fieldset>* 元素组合表单中的相关数据

*<legend>* 元素为 <fieldset> 元素定义标题。

### 实例

```
<form action="action_page.php">
<fieldset>
<legend>Personal information:</legend>
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit"></fieldset>
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_form_legend)

以上 HTML 代码在浏览器中看起来是这样的：

Personal information:
First name:


Last name:



## HTML Form 属性

HTML <form> 元素，已设置所有可能的属性，是这样的：

### 实例

```
<form action="action_page.php" method="GET" target="_blank" accept-charset="UTF-8"
ectype="application/x-www-form-urlencoded" autocomplete="off" novalidate>
.
form elements
 .
</form> 
```

下面是 <form> 属性的列表：

| 属性           | 描述                                                       |
| :------------- | :--------------------------------------------------------- |
| accept-charset | 规定在被提交表单中使用的字符集（默认：页面字符集）。       |
| action         | 规定向何处提交表单的地址（URL）（提交页面）。              |
| autocomplete   | 规定浏览器应该自动完成表单（默认：开启）。                 |
| enctype        | 规定被提交数据的编码（默认：url-encoded）。                |
| method         | 规定在提交表单时所用的 HTTP 方法（默认：GET）。            |
| name           | 规定识别表单的名称（对于 DOM 使用：document.forms.name）。 |
| novalidate     | 规定浏览器不验证表单。                                     |
| target         | 规定 action 属性中地址的目标（默认：_self）。              |

**注释：**您将在下面的章节学到更多关于属性的知识。

**本章描述所有 HTML 表单元素。**

## <input> 元素

最重要的表单元素是 *<input>* 元素。

<input> 元素根据不同的 *type* 属性，可以变化为多种形态。

**注释：**下一章讲解所有 HTML 输入类型。

## <select> 元素（下拉列表）

*<select>* 元素定义*下拉列表*：

### 实例

```
<select name="cars">
<option value="volvo">Volvo</option>
<option value="saab">Saab</option>
<option value="fiat">Fiat</option>
<option value="audi">Audi</option>
</select>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_elements_select)

*<option>* 元素定义待选择的选项。

列表通常会把首个选项显示为被选选项。

您能够通过添加 selected 属性来定义预定义选项。

### 实例

```
<option value="fiat" selected>Fiat</option>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_elements_select_pre)

## <textarea> 元素

*<textarea>* 元素定义多行输入字段（*文本域*）：

### 实例

```
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_headers)

以上 HTML 代码在浏览器中显示为：

```
The cat was playing in the garden.
```

## <button> 元素

*<button>* 元素定义可点击的*按钮*：

### 实例

```
<button type="button" onclick="alert('Hello World!')">Click Me!</button>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_elements_button)

以上 HTML 代码在浏览器中显示为：

Click Me!

## HTML5 表单元素

HTML5 增加了如下表单元素：

- <datalist>
- <keygen>
- <output>

**注释：**默认地，浏览器不会显示未知元素。新元素不会破坏您的页面。

## HTML5 <datalist> 元素

*<datalist>* 元素为 <input> 元素规定预定义选项列表。

用户会在他们输入数据时看到预定义选项的下拉列表。

<input> 元素的 *list* 属性必须引用 <datalist> 元素的 *id* 属性。

### 实例

通过 <datalist> 设置预定义值的 <input> 元素：

```
<form action="action_page.php">
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

#### 输入类型

**本章描述 <input> 元素的输入类型。**

## 输入类型：text

*<input type="text">* 定义供*文本输入*的单行输入字段：

### 实例

```
<form>
 First name:<br>
<input type="text" name="firstname">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_text)

以上 HTML 代码在浏览器中看上去是这样的：

First name:


Last name:

## 输入类型：password

*<input type="password">* 定义*密码字段*：

### 实例

```
<form>
 User name:<br>
<input type="text" name="username">
<br>
 User password:<br>
<input type="password" name="psw">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_password)

以上 HTML 代码在浏览器中看上去是这样的：

User name:


User password:

**注释：**password 字段中的字符会被做掩码处理（显示为星号或实心圆）。

## 输入类型：submit

*<input type="submit">* 定义*提交*表单数据至*表单处理程序*的按钮。

表单处理程序（form-handler）通常是包含处理输入数据的脚本的服务器页面。

在表单的 action 属性中规定表单处理程序（form-handler）：

### 实例

```
<form action="action_page.php">
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_submit)

以上 HTML 代码在浏览器中看上去是这样的：

First name:


Last name:



如果您省略了提交按钮的 value 属性，那么该按钮将获得默认文本：

### 实例

```
<form action="action_page.php">
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_submit_nn)

## Input Type: radio

<input type="radio"> 定义单选按钮。

Radio buttons let a user select ONLY ONE of a limited number of choices:

### 实例

```
<form>
<input type="radio" name="sex" value="male" checked>Male
<br>
<input type="radio" name="sex" value="female">Female
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_radio)

以上 HTML 代码在浏览器中看上去是这样的：

Male

Female

## Input Type: checkbox

<input type="checkbox"> 定义复选框。

复选框允许用户在有限数量的选项中选择零个或多个选项。

### 实例

```
<form>
<input type="checkbox" name="vehicle" value="Bike">I have a bike
<br>
<input type="checkbox" name="vehicle" value="Car">I have a car 
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_checkbox)

以上 HTML 代码在浏览器中看上去是这样的：

I have a bike

I have a car

## Input Type: button

*<input type="button>* 定义*按钮*。

### 实例

```
<input type="button" onclick="alert('Hello World!')" value="Click Me!">
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_button)

以上 HTML 代码在浏览器中看上去是这样的：

## HTML5 输入类型

HTML5 增加了多个新的输入类型：

- color
- date
- datetime
- datetime-local
- email
- month
- number
- range
- search
- tel
- time
- url
- week

**注释：**老式 web 浏览器不支持的输入类型，会被视为输入类型 text。

## 输入类型：number

*<input type="number">* 用于应该包含数字值的输入字段。

您能够对数字做出限制。

根据浏览器支持，限制可应用到输入字段。

### 实例

```
<form>
  Quantity (between 1 and 5):
  <input type="number" name="quantity" min="1" max="5">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_number)

## 输入限制

这里列出了一些常用的输入限制（其中一些是 HTML5 中新增的）：

| 属性      | 描述                               |
| :-------- | :--------------------------------- |
| disabled  | 规定输入字段应该被禁用。           |
| max       | 规定输入字段的最大值。             |
| maxlength | 规定输入字段的最大字符数。         |
| min       | 规定输入字段的最小值。             |
| pattern   | 规定通过其检查输入值的正则表达式。 |
| readonly  | 规定输入字段为只读（无法修改）。   |
| required  | 规定输入字段是必需的（必需填写）。 |
| size      | 规定输入字段的宽度（以字符计）。   |
| step      | 规定输入字段的合法数字间隔。       |
| value     | 规定输入字段的默认值。             |

您将在下一章学到更多有关输入限制的知识。

### 实例

```
<form>
  Quantity:
  <input type="number" name="points" min="0" max="100" step="10" value="30">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_number_step)

## 输入类型：date

*<input type="date">* 用于应该包含日期的输入字段。

根据浏览器支持，日期选择器会出现输入字段中。

### 实例

```
<form>
  Birthday:
  <input type="date" name="bday">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_date)

您可以向输入添加限制：

### 实例

```
<form>
  Enter a date before 1980-01-01:
  <input type="date" name="bday" max="1979-12-31"><br>
  Enter a date after 2000-01-01:
  <input type="date" name="bday" min="2000-01-02"><br>
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_date_max_min)

## 输入类型：color

*<input type="color">* 用于应该包含颜色的输入字段。

根据浏览器支持，颜色选择器会出现输入字段中。

### 实例

```
<form>
  Select your favorite color:
  <input type="color" name="favcolor">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_color)

## 输入类型：range

*<input type="range">* 用于应该包含一定范围内的值的输入字段。

根据浏览器支持，输入字段能够显示为滑块控件。

### 实例

```
<form>
  <input type="range" name="points" min="0" max="10">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_range)

您能够使用如下属性来规定限制：min、max、step、value。

## 输入类型：month

*<input type="month">* 允许用户选择月份和年份。

根据浏览器支持，日期选择器会出现输入字段中。

### 实例

```
<form>
  Birthday (month and year):
  <input type="month" name="bdaymonth">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_month)

## 输入类型：week

*<input type="week">* 允许用户选择周和年。

根据浏览器支持，日期选择器会出现输入字段中。

### 实例

```
<form>
  Select a week:
  <input type="week" name="week_year">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_week)

## 输入类型：time

*<input type="time">* 允许用户选择时间（无时区）。

根据浏览器支持，时间选择器会出现输入字段中。

### 实例

```
<form>
  Select a time:
  <input type="time" name="usr_time">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_time)

## 输入类型：datetime

*<input type="datetime">* 允许用户选择日期和时间（有时区）。

根据浏览器支持，日期选择器会出现输入字段中。

### 实例

```
<form>
  Birthday (date and time):
  <input type="datetime" name="bdaytime">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_datetime)

## 输入类型：datetime-local

*<input type="datetime-local">* 允许用户选择日期和时间（无时区）。

根据浏览器支持，日期选择器会出现输入字段中。

### 实例

```
<form>
  Birthday (date and time):
  <input type="datetime-local" name="bdaytime">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_datetime-local)

## 输入类型：email

*<input type="email">* 用于应该包含电子邮件地址的输入字段。

根据浏览器支持，能够在被提交时自动对电子邮件地址进行验证。

某些智能手机会识别 email 类型，并在键盘增加 ".com" 以匹配电子邮件输入。

### 实例

```
<form>
  E-mail:
  <input type="email" name="email">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_email)

## 输入类型：search

*<input type="search">* 用于搜索字段（搜索字段的表现类似常规文本字段）。

### 实例

```
<form>
  Search Google:
  <input type="search" name="googlesearch">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_search)

## 输入类型：tel

*<input type="tel">* 用于应该包含电话号码的输入字段。

目前只有 Safari 8 支持 tel 类型。

### 实例

```
<form>
  Telephone:
  <input type="tel" name="usrtel">
</form>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_tel)

## 输入类型：url

*<input type="url">* 用于应该包含 URL 地址的输入字段。

根据浏览器支持，在提交时能够自动验证 url 字段。

某些智能手机识别 url 类型，并向键盘添加 ".com" 以匹配 url 输入。

### 实例

```
<form>
  Add your homepage:
  <input type="url" name="homepage">
</form>
```

#### 输入属性

## value 属性

*value* 属性规定输入字段的初始值：

### 实例

```
<form action="">
 First name:<br>
<input type="text" name="firstname" value="John">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_attributes_value)

## readonly 属性

*readonly* 属性规定输入字段为只读（不能修改）：

### 实例

```
<form action="">
 First name:<br>
<input type="text" name="firstname" value="John" readonly>
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_attributes_readonly)

readonly 属性不需要值。它等同于 readonly="readonly"。

## disabled 属性

*disabled* 属性规定输入字段是禁用的。

被禁用的元素是不可用和不可点击的。

被禁用的元素不会被提交。

### 实例

```
<form action="">
 First name:<br>
<input type="text" name="firstname" value="John" disabled>
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_attributes_disabled)

disabled 属性不需要值。它等同于 disabled="disabled"。

## size 属性

*size* 属性规定输入字段的尺寸（以字符计）：

### 实例

```
<form action="">
 First name:<br>
<input type="text" name="firstname" value="John" size="40">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_attributes_size)

## maxlength 属性

*maxlength* 属性规定输入字段允许的最大长度：

### 实例

```
<form action="">
 First name:<br>
<input type="text" name="firstname" maxlength="10">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html_input_attributes_maxlength)

如设置 maxlength 属性，则输入控件不会接受超过所允许数的字符。

该属性不会提供任何反馈。如果需要提醒用户，则必须编写 JavaScript 代码。

**注释：**输入限制并非万无一失。JavaScript 提供了很多方法来增加非法输入。如需安全地限制输入，则接受者（服务器）必须同时对限制进行检查。

## HTML5 属性

HTML5 为 <input> 增加了如下属性：

- autocomplete
- autofocus
- form
- formaction
- formenctype
- formmethod
- formnovalidate
- formtarget
- height 和 width
- list
- min 和 max
- multiple
- pattern (regexp)
- placeholder
- required
- step

并为 <form> 增加如需属性：

- autocomplete
- novalidate

## autocomplete 属性

autocomplete 属性规定表单或输入字段是否应该自动完成。

当自动完成开启，浏览器会基于用户之前的输入值自动填写值。

**提示：**您可以把表单的 autocomplete 设置为 on，同时把特定的输入字段设置为 off，反之亦然。

autocomplete 属性适用于 <form> 以及如下 <input> 类型：text、search、url、tel、email、password、datepickers、range 以及 color。

### 实例

自动完成开启的 HTML 表单（某个输入字段为 off）：

```
<form action="action_page.php" autocomplete="on">
   First name:<input type="text" name="fname"><br>
   Last name: <input type="text" name="lname"><br>
   E-mail: <input type="email" name="email" autocomplete="off"><br>
   <input type="submit">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_autocomplete)

**提示：**在某些浏览器中，您也许需要手动启用自动完成功能。

## novalidate 属性

novalidate 属性属于 <form> 属性。

如果设置，则 novalidate 规定在提交表单时不对表单数据进行验证。

### 实例

指示表单在被提交时不进行验证：

```
<form action="action_page.php" novalidate>
   E-mail: <input type="email" name="user_email">
   <input type="submit">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_form_novalidate)

## autofocus 属性

autofocus 属性是布尔属性。

如果设置，则规定当页面加载时 <input> 元素应该自动获得焦点。

### 实例

使 "First name" 输入字段在页面加载时自动获得焦点：

```
First name:<input type="text" name="fname" autofocus>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_autofocus)

## form 属性

form 属性规定 <input> 元素所属的一个或多个表单。

**提示：**如需引用一个以上的表单，请使用空格分隔的表单 id 列表。

### 实例

输入字段位于 HTML 表单之外（但仍属表单）：

```
<form action="action_page.php" id="form1">
   First name: <input type="text" name="fname"><br>
   <input type="submit" value="Submit">
</form>

 Last name: <input type="text" name="lname" form="form1">
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_form)

## formaction 属性

formaction 属性规定当提交表单时处理该输入控件的文件的 URL。

formaction 属性覆盖 <form> 元素的 action 属性。

formaction 属性适用于 type="submit" 以及 type="image"。

### 实例

拥有两个两个提交按钮并对于不同动作的 HTML 表单：

```
<form action="action_page.php">
   First name: <input type="text" name="fname"><br>
   Last name: <input type="text" name="lname"><br>
   <input type="submit" value="Submit"><br>
   <input type="submit" formaction="demo_admin.asp"
   value="Submit as admin">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_formaction)

## formenctype 属性

formenctype 属性规定当把表单数据（form-data）提交至服务器时如何对其进行编码（仅针对 method="post" 的表单）。

formenctype 属性覆盖 <form> 元素的 enctype 属性。

formenctype 属性适用于 type="submit" 以及 type="image"。

### 实例

发送默认编码以及编码为 "multipart/form-data"（第二个提交按钮）的表单数据（form-data）：

```
<form action="demo_post_enctype.asp" method="post">
   First name: <input type="text" name="fname"><br>
   <input type="submit" value="Submit">
   <input type="submit" formenctype="multipart/form-data"
   value="Submit as Multipart/form-data">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_formenctype)

## formmethod 属性

formmethod 属性定义用以向 action URL 发送表单数据（form-data）的 HTTP 方法。

formmethod 属性覆盖 <form> 元素的 method 属性。

formmethod 属性适用于 type="submit" 以及 type="image"。

### 实例

第二个提交按钮覆盖表单的 HTTP 方法：

```
<form action="action_page.php" method="get">
   First name: <input type="text" name="fname"><br>
   Last name: <input type="text" name="lname"><br>
   <input type="submit" value="Submit">
   <input type="submit" formmethod="post" formaction="demo_post.asp"
   value="Submit using POST">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_formmethod)

## formnovalidate 属性

novalidate 属性是布尔属性。

如果设置，则规定在提交表单时不对 <input> 元素进行验证。

formnovalidate 属性覆盖 <form> 元素的 novalidate 属性。

formnovalidate 属性可用于 type="submit"。

### 实例

拥有两个提交按钮的表单（验证和不验证）：

```
<form action="action_page.php">
   E-mail: <input type="email" name="userid"><br>
   <input type="submit" value="Submit"><br>
   <input type="submit" formnovalidate value="Submit without validation">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_formnovalidate)

## formtarget 属性

formtarget 属性规定的名称或关键词指示提交表单后在何处显示接收到的响应。

formtarget 属性会覆盖 <form> 元素的 target 属性。

formtarget 属性可与 type="submit" 和 type="image" 使用。

### 实例

这个表单有两个提交按钮，对应不同的目标窗口：

```
<form action="action_page.php">
   First name: <input type="text" name="fname"><br>
   Last name: <input type="text" name="lname"><br>
   <input type="submit" value="Submit as normal">
   <input type="submit" formtarget="_blank"
   value="Submit to a new window">
</form> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_formtarget)

## height 和 width 属性

height 和 width 属性规定 <input> 元素的高度和宽度。

height 和 width 属性仅用于 <input type="image">。

**注释：**请始终规定图像的尺寸。如果浏览器不清楚图像尺寸，则页面会在图像加载时闪烁。

### 实例

把图像定义为提交按钮，并设置 height 和 width 属性：

```
<input type="image" src="img_submit.gif" alt="Submit" width="48" height="48">
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_height_width)

## list 属性

list 属性引用的 <datalist> 元素中包含了 <input> 元素的预定义选项。

### 实例

使用 <datalist> 设置预定义值的 <input> 元素：

```
<input list="browsers">

<datalist id="browsers">
   <option value="Internet Explorer">
   <option value="Firefox">
   <option value="Chrome">
   <option value="Opera">
   <option value="Safari">
</datalist> 
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_datalist)

## min 和 max 属性

min 和 max 属性规定 <input> 元素的最小值和最大值。

min 和 max 属性适用于如需输入类型：number、range、date、datetime、datetime-local、month、time 以及 week。

### 实例

具有最小和最大值的 <input> 元素：

```
Enter a date before 1980-01-01:
<input type="date" name="bday" max="1979-12-31">

 Enter a date after 2000-01-01:
<input type="date" name="bday" min="2000-01-02">

 Quantity (between 1 and 5):
<input type="number" name="quantity" min="1" max="5">
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_max_min)

## multiple 属性

multiple 属性是布尔属性。

如果设置，则规定允许用户在 <input> 元素中输入一个以上的值。

multiple 属性适用于以下输入类型：email 和 file。

### 实例

接受多个值的文件上传字段：

```
Select images: <input type="file" name="img" multiple>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_multiple)

## pattern 属性

pattern 属性规定用于检查 <input> 元素值的正则表达式。

pattern 属性适用于以下输入类型：text、search、url、tel、email、and password。

**提示：**请使用全局的 title 属性对模式进行描述以帮助用户。

**提示：**请在我们的 JavaScript 教程中学习更多有关正则表达式的知识。

### 实例

只能包含三个字母的输入字段（无数字或特殊字符）：

```
Country code: 
<input type="text" name="country_code" pattern="[A-Za-z]{3}" title="Three letter country code">
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_pattern)

## placeholder 属性

placeholder 属性规定用以描述输入字段预期值的提示（样本值或有关格式的简短描述）。

该提示会在用户输入值之前显示在输入字段中。

placeholder 属性适用于以下输入类型：text、search、url、tel、email 以及 password。

### 实例

拥有占位符文本的输入字段：

```
<input type="text" name="fname" placeholder="First name">
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_placeholder)

## required 属性

required 属性是布尔属性。

如果设置，则规定在提交表单之前必须填写输入字段。

required 属性适用于以下输入类型：text、search、url、tel、email、password、date pickers、number、checkbox、radio、and file.

### 实例

必填的输入字段：

```
Username: <input type="text" name="usrname" required>
```

[亲自试一试](https://www.w3school.com.cn/tiy/t.asp?f=html5_input_required)

## step 属性

step 属性规定 <input> 元素的合法数字间隔。

示例：如果 step="3"，则合法数字应该是 -3、0、3、6、等等。

**提示：**step 属性可与 max 以及 min 属性一同使用，来创建合法值的范围。

step 属性适用于以下输入类型：number、range、date、datetime、datetime-local、month、time 以及 week。

### 示例

拥有具体的合法数字间隔的输入字段：

```
<input type="number" name="points" step="3">
```


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

## 08


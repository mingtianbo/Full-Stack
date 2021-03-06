

# h-CSS

## Get Start

这篇文档基于TailwindCSS对CSS进行学习，首先需要了解一些HTML的知识，在我看来，CSS就是专门在写HTML中的style样式，只不过把样式全部写到了一个css文档中，所以了解HTML即可，在接下来的一章中，我们将对CSS基础进行一个介绍，然后就可以开始正式学习CSS了！

<hr/>

### 简介

**CSS概述**

- CSS指层叠样式表（**C**ascading **S**tyle **S**heets）
- 样式定义**如何显示**HTML元素
- 样式通常存储在**样式表**中
- 把样式添加到HTML4.0中，是为了**解决内容与表现分离的问题**
- **外部样式表**可以极大提高工作效率
- 外部样式表通常存储在**CSS文件**中
- 多个样式定义可**层叠**为一

<hr/>

### 基础语法

**CSS 语法**

CSS 规则由两个主要的部分构成：选择器，以及一条或多条声明。

```css
selector {declaration1; declaration2; ... declarationN }
```

- 选择器通常是您需要改变样式的 HTML 元素。

- 每条声明由一个属性和一个值组成。

属性（`property`）是您希望设置的样式属性（`style attribute`）。每个属性有一个值。属性和值被冒号分开。

```css
selector {property: value}
```

**实例**

下面这行代码的作用是将`h1`元素内的文字颜色定义为红色，同时将字体大小设置为`14`像素。

在这个例子中，`h1`是选择器，`color`和`font-size`是属性，`red`和`14px`是值。

```css
h1 {color:red; font-size:14px;}
```

下面的示意图为您展示了上面这段代码的结构：

![CSS 语法](https://www.w3school.com.cn/i/ct_css_selector.gif)

>  **提示：**请使用花括号来包围声明。

<hr/>

**值的不同写法和单位**

除了英文单词 red，我们还可以使用十六进制的颜色值 #ff0000：

```css
p { color: #ff0000; }
```

为了节约字节，我们可以使用 CSS 的缩写形式：

```css
p { color: #f00; }
```

我们还可以通过两种方法使用 RGB 值：

```css
p { color: rgb(255,0,0); }
p { color: rgb(100%,0%,0%); }
```

请注意，当使用 RGB 百分比时，即使当值为 0 时也要写百分比符号。但是在其他的情况下就不需要这么做了。比如说，当尺寸为 0 像素时，0 之后不需要使用 px 单位，因为 0 就是 0，无论单位是什么。

<hr/>

**记得写引号**

>  **提示：**如果值为若干单词，则要给值加引号：

```css
p {font-family: "sans serif";}
```

<hr/>

**多重声明：**

**提示：**如果要定义不止一个声明，则需要用分号将每个声明分开。下面的例子展示出如何定义一个红色文字的居中段落。最后一条规则是不需要加分号的，因为分号在英语中是一个分隔符号，不是结束符号。然而，大多数有经验的设计师会在每条声明的末尾都加上分号，这么做的好处是，当你从现有的规则中增减声明时，会尽可能地减少出错的可能性。就像这样：

```css
p {text-align:center; color:red;}	
```

你应该在每行只描述一个属性，这样可以增强样式定义的可读性，就像这样：

```css
p {
  text-align: center;
  color: black;
  font-family: arial;
}
```

<hr/>

**空格和大小写**

大多数样式表包含不止一条规则，而大多数规则包含不止一个声明。多重声明和空格的使用使得样式表更容易被编辑：

```css
body {
  color: #000;
  background: #fff;
  margin: 0;
  padding: 0;
  font-family: Georgia, Palatino, serif;
  }
```

**注意：**是否包含空格不会影响 CSS 在浏览器的工作效果，同样，与 XHTML 不同，CSS 对大小写不敏感。不过存在一个例外：如果涉及到与 HTML 文档一起工作的话，`class` 和` id `名称对大小写是敏感的。

<hr/>

### 高级语法

**选择器的分组**

你可以对选择器进行分组，这样，被分组的选择器就可以分享相同的声明。用逗号将需要分组的选择器分开。在下面的例子中，我们对所有的标题元素进行了分组。所有的标题元素都是绿色的。

```css
h1,h2,h3,h4,h5,h6 {
  color: green;
  }
```

<hr/>

**继承及其问题**

根据 CSS，子元素从父元素继承属性。但是它并不总是按此方式工作。看看下面这条规则：

```css
body {
     font-family: Verdana, sans-serif;
     }
```

根据上面这条规则，站点的` body `元素将使用` Verdana `字体（假如访问者的系统中存在该字体的话）。

通过 CSS 继承，子元素将继承最高级元素（在本例中是` body`）所拥有的属性（这些子元素诸如` p`,` td`,` ul`,` ol`,` ul`,` li`,` dl`,` dt`和` dd`）。不需要另外的规则，所有` body `的子元素都应该显示` Verdana `字体，子元素的子元素也一样。并且在大部分的现代浏览器中，也确实是这样的。

但是在那个浏览器大战的血腥年代里，这种情况就未必会发生，那时候对标准的支持并不是企业的优先选择。比方说，Netscape 4 就不支持继承，它不仅忽略继承，而且也忽略应用于 body 元素的规则。IE/Windows 直到 IE6 还存在相关的问题，在表格内的字体样式会被忽略。我们又该如何是好呢？

<hr/>

**冗余法则**

幸运地是，你可以通过使用我们称为 "Be Kind to Netscape 4" 的冗余法则来处理旧式浏览器无法理解继承的问题。

```css
body  {
     font-family: Verdana, sans-serif;
     }

p, td, ul, ol, li, dl, dt, dd  {
     font-family: Verdana, sans-serif;
     }
```

4.0 浏览器无法理解继承，不过他们可以理解组选择器。这么做虽然会浪费一些用户的带宽，但是如果需要对 Netscape 4 用户进行支持，就不得不这么做。

<hr/>

**摆脱继承**

如果你不希望`Verdana, sans-serif`字体被所有的子元素继承，又该怎么做呢？比方说，你希望段落的字体是` Times`。没问题。创建一个针对` p `的特殊规则，这样它就会摆脱父元素的规则：

```css
body  {
     font-family: Verdana, sans-serif;
     }

td, ul, ol, ul, li, dl, dt, dd  {
     font-family: Verdana, sans-serif;
     }

p  {
     font-family: Times, "Times New Roman", serif;
     }
```

<hr/>

### 派生选择器

**通过依据元素在其位置的上下文关系来定义样式，你可以使标记更加简洁。**

在 CSS1 中，通过这种方式来应用规则的选择器被称为上下文选择器 (`contextual selectors`)，这是由于它们依赖于上下文关系来应用或者避免某项规则。在 CSS2 中，它们称为派生选择器，但是无论你如何称呼它们，它们的作用都是相同的。

派生选择器允许你根据文档的上下文关系来确定某个标签的样式。通过合理地使用派生选择器，我们可以使 HTML 代码变得更加整洁。

比方说，你希望列表中的` strong `元素变为斜体字，而不是通常的粗体字，可以这样定义一个派生选择器：

```css
li strong {
    font-style: italic;
    font-weight: normal;
  }
```

请注意标记为` <strong> `的蓝色代码的上下文关系：

```html
<p><strong>我是粗体字，不是斜体字，因为我不在列表当中，所以这个规则对我不起作用</strong></p>

<ol>
<li><strong>我是斜体字。这是因为 strong 元素位于 li 元素内。</strong></li>
<li>我是正常的字体。</li>
</ol>
```

在上面的例子中，只有` li `元素中的` strong `元素的样式为斜体字，无需为 `strong `元素定义特别的` class `或` id`，代码更加简洁。

再看看下面的 CSS 规则：

```css
strong {
     color: red;
     }

h2 {
     color: red;
     }

h2 strong {
     color: blue;
     }
```

下面是它施加影响的 HTML：

```html
<p>The strongly emphasized word in this paragraph is<strong>red</strong>.</p>
<h2>This subhead is also red.</h2>
<h2>The strongly emphasized word in this subhead is<strong>blue</strong>.</h2>
```

<hr/>

### `id`选择器

**id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。**

**id 选择器以 "#" 来定义。**

下面的两个` id `选择器，第一个可以定义元素的颜色为红色，第二个定义元素的颜色为绿色：

```css
#red {color:red;}
#green {color:green;}
```

下面的 HTML 代码中，`id `属性为` red `的` p `元素显示为红色，而` id `属性为 `green `的` p `元素显示为绿色。

```css
<p id="red">这个段落是红色。</p>
<p id="green">这个段落是绿色。</p>
```

<hr/>

**id 选择器和派生选择器**

**在现代布局中，id 选择器常常用于建立派生选择器。**

```css
#sidebar p {
	font-style: italic;
	text-align: right;
	margin-top: 0.5em;
	}
```

上面的样式只会应用于出现在` id `是` sidebar `的元素内的段落。这个元素很可能是` div `或者是表格单元，尽管它也可能是一个表格或者其他块级元素。它甚至可以是一个内联元素，比如` <em></em> `或者 `<span></span>`，不过这样的用法是非法的，因为不可以在内联元素` <span> `中嵌入` <p> `。

<hr/>

**一个选择器，多种用法**

**即使被标注为 sidebar 的元素只能在文档中出现一次，这个 id 选择器作为派生选择器也可以被使用很多次：**

```css
#sidebar p {
	font-style: italic;
	text-align: right;
	margin-top: 0.5em;
	}

#sidebar h2 {
	font-size: 1em;
	font-weight: normal;
	font-style: italic;
	margin: 0;
	line-height: 1.5;
	text-align: right;
	}
```

在这里，与页面中的其他` p `元素明显不同的是，`sidebar `内的` p `元素得到了特殊的处理，同时，与页面中其他所有` h2 `元素明显不同的是，`sidebar `中的` h2 `元素也得到了不同的特殊处理。

<hr/>

**单独的选择器**

**id 选择器即使不被用来创建派生选择器，它也可以独立发挥作用：**

```css
#sidebar {
	border: 1px dotted #000;
	padding: 10px;
	}
```

根据这条规则，`id `为` sidebar `的元素将拥有一个像素宽的黑色点状边框，同时其周围会有` 10 `个像素宽的内边距（`padding`，内部空白）。老版本的 `Windows/IE `浏览器可能会忽略这条规则，除非你特别地定义这个选择器所属的元素：

```css
div#sidebar {
	border: 1px dotted #000;
	padding: 10px;
	}
```

<hr/>

### 类选择器

**在 CSS 中，类选择器以一个点号显示：**

```css
.center {text-align: center}
```

在上面的例子中，所有拥有` center `类的 HTML 元素均为居中。

在下面的 HTML 代码中，`h1 `和` p `元素都有` center `类。这意味着两者都将遵守 ".center" 选择器中的规则。

```css
<h1 class="center">
This heading will be center-aligned
</h1>

<p class="center">
This paragraph will also be center-aligned.
</p>
```

>  **注意：**类名的第一个字符不能使用数字！它无法在 Mozilla 或 Firefox 中起作用。

**和 id 一样，class 也可被用作派生选择器：**

```css
.fancy td {
	color: #f60;
	background: #666;
	}
```

在上面这个例子中，类名为` fancy `的更大的元素内部的表格单元都会以灰色背景显示橙色文字。（名为` fancy `的更大的元素可能是一个表格或者一个` div`）

**元素也可以基于它们的类而被选择：**

```css
td.fancy {
	color: #f60;
	background: #666;
	}
```

在上面的例子中，类名为` fancy `的表格单元将是带有灰色背景的橙色。

```css
<td class="fancy">
```

你可以将类` fancy `分配给任何一个表格元素任意多的次数。那些以` fancy `标注的单元格都会是带有灰色背景的橙色。那些没有被分配名为` fancy `的类的单元格不会受这条规则的影响。还有一点值得注意，`class `为` fancy `的段落也不会是带有灰色背景的橙色，当然，任何其他被标注为` fancy `的元素也不会受这条规则的影响。这都是由于我们书写这条规则的方式，这个效果被限制于被标注为`fancy `的表格单元（即使用` td `元素来选择` fancy `类）。

<hr/>

### 属性选择器

**对带有指定属性的 HTML 元素设置样式。**

可以为拥有指定属性的 HTML 元素设置样式，而不仅限于 class 和 id 属性。

>  **注释：**只有在规定了 !DOCTYPE 时，IE7 和 IE8 才支持属性选择器。在 IE6 及更低的版本中，不支持属性选择。

**实例**

下面的例子为带有 title 属性的所有元素设置样式：

```css
[title]
{
color:red;
}
```

<hr/>

**属性和值选择器**

下面的例子为 title="W3School" 的所有元素设置样式：

```css
[title=W3School]
{
border:5px solid blue;
}
```

<hr/>

**属性和值选择器 - 多个值**

下面的例子为包含指定值的 title 属性的所有元素设置样式。适用于由空格分隔的属性值：

```css
[title~=hello] { color:red; }
```

下面的例子为带有包含指定值的 lang 属性的所有元素设置样式。适用于由连字符分隔的属性值：

```css
[lang|=en] { color:red; }
```

<hr/>

**设置表单的样式**

属性选择器在为不带有 class 或 id 的表单设置样式时特别有用：

```css
input[type="text"]
{
  width:150px;
  display:block;
  margin-bottom:10px;
  background-color:yellow;
  font-family: Verdana, Arial;
}

input[type="button"]
{
  width:120px;
  margin-left:35px;
  display:block;
  font-family: Verdana, Arial;
}
```

<hr/>

**CSS 选择器参考手册**

| 选择器                                                       | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [[*attribute*\]](https://www.w3school.com.cn/cssref/selector_attribute.asp) | 用于选取带有指定属性的元素。                                 |
| [[*attribute*=*value*\]](https://www.w3school.com.cn/cssref/selector_attribute_value.asp) | 用于选取带有指定属性和值的元素。                             |
| [[*attribute*~=*value*\]](https://www.w3school.com.cn/cssref/selector_attribute_value_contain.asp) | 用于选取属性值中包含指定词汇的元素。                         |
| [[*attribute*\|=*value*\]](https://www.w3school.com.cn/cssref/selector_attribute_value_start.asp) | 用于选取带有以指定值开头的属性值的元素，该值必须是整个单词。 |
| [[*attribute*^=*value*\]](https://www.w3school.com.cn/cssref/selector_attr_begin.asp) | 匹配属性值以指定值开头的每个元素。                           |
| [[*attribute*$=*value*\]](https://www.w3school.com.cn/cssref/selector_attr_end.asp) | 匹配属性值以指定值结尾的每个元素。                           |
| [[*attribute**=*value*\]](https://www.w3school.com.cn/cssref/selector_attr_contain.asp) | 匹配属性值中包含指定值的每个元素。                           |

<hr/>

### CSS创建

**如何插入样式表**

**当读到一个样式表时，浏览器会根据它来格式化 HTML 文档。插入样式表的方法有三种：**

#### 外部样式表

当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用 `<link> `标签链接到样式表。`<link> `标签在（文档的）头部：

```css
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
</head>
```

浏览器会从文件` mystyle.css `中读到样式声明，并根据它来格式文档。

外部样式表可以在任何文本编辑器中进行编辑。文件不能包含任何的` html `标签。样式表应该以` .css `扩展名进行保存。下面是一个样式表文件的例子：

```css
hr {color: sienna;}
p {margin-left: 20px;}
body {background-image: url("images/back40.gif");}
```

不要在属性值与单位之间留有空格。假如你使用 “margin-left: 20 px” 而不是 “margin-left: 20px” ，它仅在 IE 6 中有效，但是在 Mozilla/Firefox 或 Netscape 中却无法正常工作。

<hr/>

#### 内部样式表

当单个文档需要特殊的样式时，就应该使用内部样式表。你可以使用` <style> `标签在文档头部定义内部样式表，就像这样:

```html
<head>
<style type="text/css">
  hr {color: sienna;}
  p {margin-left: 20px;}
  body {background-image: url("images/back40.gif");}
</style>
</head>
```

<hr/>

#### 内联样式

由于要将表现和内容混杂在一起，内联样式会损失掉样式表的许多优势。请慎用这种方法，例如当样式仅需要在一个元素上应用一次时。

要使用内联样式，你需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性。本例展示如何改变段落的颜色和左外边距：

```html
<p style="color: sienna; margin-left: 20px">
This is a paragraph
</p>
```

<hr/>

**多重样式**

如果某些属性在不同的样式表中被同样的选择器定义，那么属性值将从更具体的样式表中被继承过来。

例如，外部样式表拥有针对 h3 选择器的三个属性：

```css
h3 {
  color: red;
  text-align: left;
  font-size: 8pt;
  }
```

而内部样式表拥有针对 h3 选择器的两个属性：

```css
h3 {
  text-align: right; 
  font-size: 20pt;
  }
```

假如拥有内部样式表的这个页面同时与外部样式表链接，那么 h3 得到的样式是：

```css
color: red; 
text-align: right; 
font-size: 20pt;
```

即颜色属性将被继承于外部样式表，而文字排列（text-alignment）和字体尺寸（font-size）会被内部样式表中的规则取代。

### 附：[CSS 参考手册](https://www.w3school.com.cn/cssref/index.asp)

<hr/>

### 开始使用TailwindCSS

在html文档中引入下面的代码即可开始使用TailwindCSS。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet">
</head>
<body>

    <div class="md:flex">
        <div class="md:flex-shrink-0">
          <img class="rounded-lg md:w-56" src="https://images.unsplash.com/photo-1556740738-b6a63e27c4df?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=448&q=80" alt="Woman paying for a purchase">
        </div>
        <div class="mt-4 md:mt-0 md:ml-6">
          <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">Marketing</div>
          <a href="#" class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline">Finding customers for your new business</a>
          <p class="mt-2 text-gray-600">Getting a new business off the ground is a lot of hard work. Here are five ideas you can use to find your first customers.</p>
        </div>
      </div>
</body>
</html>
```

<hr/>



## 布局概述

### 容器

用于将元素的宽度固定到当前断点的组件。

<table>
  <tr>
    <td>类</td>
    <td>断点</td>
    <td>属性</td>
  </tr>
  <tr>
    <td rowspan="5">.container</td>
    <td>None</td>
    <td>width:100%</td>
  </tr>
  <tr>
    <td>sm(640px)</td>
    <td>max-width:640px;</td>
  </tr>
  <tr>
    <td>md(768px)</td>
    <td>max-width:768px;</td>
  </tr>
  <tr>
    <td>lg(1024px)</td>
    <td>max-width:1024px;</td>
  </tr>
  <tr>
    <td>xl(1280px)</td>
    <td>max-width:1280px;</td>
  </tr>
</table>

<hr/>

#### 用法

`.container`类将元素的`max-width`与当前断点的`min-width`进行匹配。如果希望设计一组固定的屏幕尺寸，而不是一个可变尺寸的窗口，这将很有用。

请注意，与其他框架中的容器不同，Tailwind的容器**不会自动居中**，**也没有任何内置的水平填充**。

要使容器居中，请使用`.mx-auto`实用程序：

```html
<div class="container mx-auto">
  <!-- ... -->
</div>
```

要添加水平填充，请使用`.px-{size}`实用程序：

```html
<div class="container mx-auto px-4">
  <!-- ... -->
</div>
```

<hr/>

#### 响应式

本`container`类还默认包含诸如`md:container`之类的响应变量，可以使某些行为仅在特定断点的情况下位容器：

```html
<!-- Full-width fluid until the 'lg' breakpoint, then lock to container -->
<div class="lg:container lg:mx-auto">
  <!-- ... -->
</div>
```

<hr/>

#### 客制化

**默认居中**

要使容器默认居中，请在配置文件中将`center`选项设置为：`true theme.container`

```js
//tailwind.config.js
module.exports = {
  theme:{
    container:{
      center:true,
    },
  },
}
```

**水平填充**

要默认添加水平填充，请在配置文件中将`padding`选项指定所需的填充量`theme.container`:

```js
// tailwind.config.js
module.exports = {
  theme:{
    container:{
      padding:'2rem',
    },
  },
}
```

如果要为每个断点指定不同的填充量，请为每个对象提供一个`default`值以及任何特定断点的替代：

```js
// tailwind.config.js
module.exports = {
  theme:{
    container:{
      padding:{
        default:'1rem',
        sm:'2rem',
        lg:'4rem',
        xl:'5rem',
      },
    },
  },
};
```

**禁用响应变量**

如果要禁用响应变量，可以通过`container`在文件`tailwind.config.js`中的`variants`部分将其设置为空数组来使用：

```js
//tailwind.config.js
module.exports = {
  variants:{
    // ...
+		container:[],    
  }
}
```

**完全禁用**

如果您不打算在项目中使用`.container`类，则可以通过在配置文件中更改设置来完全禁用该类：`false corePlugins`

```js
// tailwind.config.js
module.exports = {
  corePlugins:{
    // ...
+		container:false,    
  }
}
```

<hr/>

### 盒子尺寸

用于控制浏览器应如何计算元素总大小的实用程序。

| 类           | 属性                     |
| ------------ | ------------------------ |
| .box-border  | box-sizing: border-box;  |
| .box-content | box-sizing: content-box; |

<hr/>

#### 包含边框和内边距

使用`box-border`设置元素`box-sizing`到`border-box`，告诉浏览器在给其高度或宽度时包含元素的边框和内边距。

这就意味着一个`100px*100px`的元素（具有`2px`的边框和所有侧面都有`4px`的内边距）将被渲染为`100px*100px`，内部内容区域为`88px*88px`。

> Tailwind makes this the default for all elements in our [preflight base styles](https://tailwindcss.com/docs/preflight).

```html
<div class="box-border h-20 w-32 p-4 border-4 border-gray-400 bg-gray-200">
  <div class="h-full w-full bg-gray-400"></div>
</div>
```

![](/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/CSSmd图片/截屏2020-11-21 下午1.50.08.png)

<hr/>

#### 排除边框和内边距

使用`box-content`设置元素的`box-sizing`到`content-box`，告诉浏览器在元素的指定宽度或高度上添加边框和内边距。

这意味着一个`100px * 100px`的元素具有`2px`的边框和在所有边上都有`4px`的填充实际上将被渲染为`112px * 112px`，内部内容区域为`100px × 100px`。

```html
<div class="box-content h-20 w-32 p-4 border-4 border-gray-400 bg-gray-200">
  <div class="h-full w-full bg-gray-400"></div>
</div>
```

![](/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/CSSmd图片/截屏2020-11-21 下午1.50.01.png)

<hr/>

#### 反应灵敏

要控制特定断点处的框大小，请在`{screen}:`任何现有的框大小实用程序中添加前缀。例如，用于仅在中等屏幕尺寸及以上的屏幕上`md:box-content`应用该`box-content`实用程序。

```html
<div class="box-border md:box-content ...">
  <!-- ... -->
</div>
```

> For more information about Tailwind's responsive design features, check out the [Responsive Design](https://tailwindcss.com/docs/responsive-design) documentation.

<hr/>

#### 客制化

**响应和伪类变量**

默认情况下，仅对`box-sizing`使用程序生成响应变量。

你可以通过修改配置文件中的`variants`部分中的`boxSizing`属性来控制为`box-sizing`实用程序生成哪些变量。

例如，此配置还将生成悬停和焦点变量：

```js
// tailwind.config.js
  module.exports = {
    variants: {
      // ...
-     boxSizing: ['responsive'],
+     boxSizing: ['responsive', 'hover', 'focus'],
    }
  }
```

**禁用**

如果不打算在项目中使用盒子尺寸这个类，则可以通过更改配置文件中的属性设置为完全禁用他们：`boxSizing` `false` `corePlugins`

```js
 // tailwind.config.js
  module.exports = {
    corePlugins: {
      // ...
+     boxSizing: false,
    }
  }
```

<hr/>

### 显示

用于控制元素的显示框类型的实用程序。

| 类                   | 属性                          |
| -------------------- | ----------------------------- |
| `block`              | `display:block;`              |
| `inline-block`       | `display:inline-block;`       |
| `inline`             | `display:inline;`             |
| `flex`               | `display:flex;`               |
| `inline-flex`        | `display:inline-flex;`        |
| `table`              | `display:table;`              |
| `table-caption`      | `display:table-caption;`      |
| `table-cell`         | `display:table-cell;`         |
| `table-column`       | `display:table-column;`       |
| `table-column-group` | `display:table-column-group;` |
| `table-footer-group` | `display:table-footer-group;` |
| `table-header-group` | `display:table-header-group;` |
| `table-row-group`    | `display:table-row-group;`    |
| `table-row`          | `display:table-row;`          |
| `flow-root`          | `display:flow-root;`          |
| `grid`               | `display:grid;`               |
| `inline-grid`        | `display:inline-grid;`        |
| `contents`           | `display:contents;`           |
| `hidden`             | `display:none;`               |

<hr/>

#### Block

使用`block`创造一个块级元素。

```html
<div class="space-y-4 ...">
  <span class="block ...">1</span>
  <span class="block ...">2</span>
  <span class="block ...">3</span>
</div>
```

> **说明：**省略号可以写其他的属性用来修饰这个块。

<hr/>

#### Flow-Root

使用`flow-root`创建具有自己的块格式设置上下文的块级元素。

```html
<div class="space-y-4">
  <div class="flow-root ...">
    <div class="my-4 ...">1</div>
  </div>
  <div class="flow-root ...">
    <div class="my-4 ...">2</div>
  </div>
</div>
```

<hr/>

#### Inline Block

用`inline-block`创建一个内联块级元素。

```html
<div class="space-x-4 ...">
  <div class="inline-block ...">1</div>
  <div class="inline-block ...">2</div>
  <div class="inline-block ...">3</div>
</div>
```

<hr/>

#### Inline

用`inline`创建一个内联元素。

```html
<div>
  <div class="inline ...">1</div>
  <div class="inline ...">2</div>
  <div class="inline ...">3</div>
</div>
```

<hr/>

#### Flex

用`flex`创建一个块级灵活可伸缩容器。

```html
<div class="flex space-x-4 ...">
  <div class="flex-1 ...">1</div>
  <div class="flex-1 ...">2</div>
  <div class="flex-1 ...">3</div>
</div>
```

<hr/>

#### Inline flex

用`inline-flex`创建一个灵活的内联容器。

```html
<div class="inline-flex space-x-4 ...">
  <div class="flex-1 ...">1</div>
  <div class="flex-1 ...">2</div>
  <div class="flex-1 ...">3</div>
</div>
```

<hr/>

#### Grid

用`grid`创建一个网格容器。

```html
<div class="grid gap-4 grid-cols-3">
  <!-- ... -->
</div>
```

<hr/>

#### Inline Grid

用`inline-grid`创建一个内联网格容器。

```html
<span class="inline-grid grid-cols-3 gap-x-4">
  <span>1</span>
  <span>1</span>
  <span>1</span>
</span>
<span class="inline-grid grid-cols-3 gap-x-4">
  <span>2</span>
  <span>2</span>
  <span>2</span>
</span>
```

<hr/>

#### Contents

使用`contents`创建一个“幻影”容器，其子级充当父级的直接子级。

```html
<div class="flex ...">
  <div class="flex-1 ...">1</div>
  <div class="contents">
    <div class="flex-1 ...">2</div>
    <div class="flex-1 ...">3</div>
  </div>
  <div class="flex-1 ...">4</div>
</div>
```

<hr/>

#### Table

使用`table`, `.table-row`, `.table-cell`, `.table-caption`, `.table-column`, `.table-column-group`, `.table-header-group`, `.table-row-group`，还有 `.table-footer-group` 创建行为类似各自表元素的额元素的实用程序。

```html
<div class="table w-full ...">
  <div class="table-row-group">
    <div class="table-row">
      <div class="table-cell ...">A cell with more content</div>
      <div class="table-cell ...">Cell 2</div>
      <div class="table-cell ...">Cell 3</div>
    </div>
    <div class="table-row">
      <div class="table-cell ...">Cell 4</div>
      <div class="table-cell ...">A cell with more content</div>
      <div class="table-cell ...">Cell 6</div>
    </div>
  </div>
</div>
```

<hr/>

#### Hidden

用`hidden`设置一个元素的属性为`display:none`，并将其从页面布局中删除（与可见性文档中的`.invisible`比较）。

```html
<div class="flex ...">
  <div class="hidden ...">1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

### 浮动

用于控制内容在元素周围的环绕的实用程序。

| 类            | 属性值         |
| ------------- | -------------- |
| `float-right` | `float:right;` |
| `float-left`  | `float:left;`  |
| `float-none`  | `float:none;`  |

<hr/>

#### 向右浮动

使用`float-right`将元素浮动到其容器的右侧。

```html
<img class="float-right ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam venenatis et lorem sit amet vehicula. Etiam vel nibh nec nisi euismod mollis ultrices condimentum velit. Proin velit libero, interdum ac rhoncus sit amet, pellentesque ac turpis. Quisque ac luctus turpis, vel efficitur ante. Cras convallis risus vel vehicula dapibus. Donec eget neque fringilla, faucibus mi quis, porttitor magna. Cras pellentesque leo est, et luctus neque rutrum eu. Aliquam consequat velit sed sem posuere, vitae sollicitudin mi consequat. Mauris eget ipsum sed dui rutrum fringilla. Donec varius vehicula magna sit amet auctor. Ut congue vehicula lectus in blandit. Vivamus suscipit eleifend turpis, nec sodales sem vulputate a. Curabitur pulvinar libero viverra, efficitur odio eu, finibus justo. Etiam eu vehicula felis.
</p>
```

<hr/>

#### 向左浮动

使用`float-left`将元素浮动到其容器的左侧。

```html
<img class="float-left ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam venenatis et lorem sit amet vehicula. Etiam vel nibh nec nisi euismod mollis ultrices condimentum velit. Proin velit libero, interdum ac rhoncus sit amet, pellentesque ac turpis. Quisque ac luctus turpis, vel efficitur ante. Cras convallis risus vel vehicula dapibus. Donec eget neque fringilla, faucibus mi quis, porttitor magna. Cras pellentesque leo est, et luctus neque rutrum eu. Aliquam consequat velit sed sem posuere, vitae sollicitudin mi consequat. Mauris eget ipsum sed dui rutrum fringilla. Donec varius vehicula magna sit amet auctor. Ut congue vehicula lectus in blandit. Vivamus suscipit eleifend turpis, nec sodales sem vulputate a. Curabitur pulvinar libero viverra, efficitur odio eu, finibus justo. Etiam eu vehicula felis.</p>
```

<hr/>

#### 不浮动

使用`float-none`重置应用于元素的所有浮动。这是`float`属性的默认值。

```html
<img class="float-none ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam venenatis et lorem sit amet vehicula. Etiam vel nibh nec nisi euismod mollis ultrices condimentum velit. Proin velit libero, interdum ac rhoncus sit amet, pellentesque ac turpis. Quisque ac luctus turpis, vel efficitur ante. Cras convallis risus vel vehicula dapibus. Donec eget neque fringilla, faucibus mi quis, porttitor magna. Cras pellentesque leo est, et luctus neque rutrum eu. Aliquam consequat velit sed sem posuere, vitae sollicitudin mi consequat. Mauris eget ipsum sed dui rutrum fringilla. Donec varius vehicula magna sit amet auctor. Ut congue vehicula lectus in blandit. Vivamus suscipit eleifend turpis, nec sodales sem vulputate a. Curabitur pulvinar libero viverra, efficitur odio eu, finibus justo. Etiam eu vehicula felis.</p>
```

<hr/>

### 清除

用于控制内容在元素周围的环绕的实用程序。

| 类            | 属性值         |
| ------------- | -------------- |
| `clear-left`  | `clear:left;`  |
| `clear-right` | `clear:right;` |
| `clear-both`  | `clear:both;`  |
| `clear-none`  | `clear:none;`  |

<hr/>

#### 左清除

使用`clear-left`将元素放置在任何先前的左浮动元素下方。

```html
<img class="float-left ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<img class="float-right ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<p class="clear-left ...">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam venenatis et lorem sit amet vehicula. Etiam vel nibh nec nisi euismod mollis ultrices condimentum velit. Proin velit libero, interdum ac rhoncus sit amet, pellentesque ac turpis. Quisque ac luctus turpis, vel efficitur ante. Cras convallis risus vel vehicula dapibus. Donec eget neque fringilla, faucibus mi quis, porttitor magna. Cras pellentesque leo est, et luctus neque rutrum eu. Aliquam consequat velit sed sem posuere, vitae sollicitudin mi consequat. Mauris eget ipsum sed dui rutrum fringilla. Donec varius vehicula magna sit amet auctor. Ut congue vehicula lectus in blandit. Vivamus suscipit eleifend turpis, nec sodales sem vulputate a. Curabitur pulvinar libero viverra, efficitur odio eu, finibus justo. Etiam eu vehicula felis.</p>
```

<hr/>

#### 右清除

使用`clear-right`将元素放置在任何先前的右浮动元素下方。

```html
<img class="float-left ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<img class="float-right ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<p class="clear-right ...">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam venenatis et lorem sit amet vehicula. Etiam vel nibh nec nisi euismod mollis ultrices condimentum velit. Proin velit libero, interdum ac rhoncus sit amet, pellentesque ac turpis. Quisque ac luctus turpis, vel efficitur ante. Cras convallis risus vel vehicula dapibus. Donec eget neque fringilla, faucibus mi quis, porttitor magna. Cras pellentesque leo est, et luctus neque rutrum eu. Aliquam consequat velit sed sem posuere, vitae sollicitudin mi consequat. Mauris eget ipsum sed dui rutrum fringilla. Donec varius vehicula magna sit amet auctor. Ut congue vehicula lectus in blandit. Vivamus suscipit eleifend turpis, nec sodales sem vulputate a. Curabitur pulvinar libero viverra, efficitur odio eu, finibus justo. Etiam eu vehicula felis.</p>
```

<hr/>

#### 清除所有

使用`clear-both`将元素放置在任何先前浮动的元素下方。

```html
<img class="float-left ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<img class="float-right ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<p class="clear-both ...">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam venenatis et lorem sit amet vehicula. Etiam vel nibh nec nisi euismod mollis ultrices condimentum velit. Proin velit libero, interdum ac rhoncus sit amet, pellentesque ac turpis. Quisque ac luctus turpis, vel efficitur ante. Cras convallis risus vel vehicula dapibus. Donec eget neque fringilla, faucibus mi quis, porttitor magna. Cras pellentesque leo est, et luctus neque rutrum eu. Aliquam consequat velit sed sem posuere, vitae sollicitudin mi consequat. Mauris eget ipsum sed dui rutrum fringilla. Donec varius vehicula magna sit amet auctor. Ut congue vehicula lectus in blandit. Vivamus suscipit eleifend turpis, nec sodales sem vulputate a. Curabitur pulvinar libero viverra, efficitur odio eu, finibus justo. Etiam eu vehicula felis.</p>
```

<hr/>

#### 取消清除

使用`clear-none`重置所有应用于元素的清除。这是`clear`属性的默认值。

```html
<img class="float-left ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<img class="float-right ..." src="/Users/ming/Documents/learning/Full-Stack/Front_Basic/css/Day2/image.jpg">
<p class="clear-none ...">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam venenatis et lorem sit amet vehicula. Etiam vel nibh nec nisi euismod mollis ultrices condimentum velit. Proin velit libero, interdum ac rhoncus sit amet, pellentesque ac turpis. Quisque ac luctus turpis, vel efficitur ante. Cras convallis risus vel vehicula dapibus. Donec eget neque fringilla, faucibus mi quis, porttitor magna. Cras pellentesque leo est, et luctus neque rutrum eu. Aliquam consequat velit sed sem posuere, vitae sollicitudin mi consequat. Mauris eget ipsum sed dui rutrum fringilla. Donec varius vehicula magna sit amet auctor. Ut congue vehicula lectus in blandit. Vivamus suscipit eleifend turpis, nec sodales sem vulputate a. Curabitur pulvinar libero viverra, efficitur odio eu, finibus justo. Etiam eu vehicula felis.</p>
```

<hr/>

### 对象拟合

用于控制应如何调整替换元素内容大小的实用程序。

| 类                  | 属性                     |
| ------------------- | ------------------------ |
| `object-contain`    | `object-fit:contain;`    |
| `object-cover`      | `object-fit:cover;`      |
| `object-fill`       | `object-fit:fill;`       |
| `object-none`       | `object-fit:none;`       |
| `object-scale-down` | `object-fit:scale-down;` |

<hr/>

#### 包含

使用`.object-contain`调整元素内容的大小以使其包含在其容器中。

```html
<div class="bg-rose-300 ...">
  <img class="object-contain h-48 w-full ..."> 
</div>
```

<hr/>

#### 覆盖

使用`.object-cover`调整元素内容的大小以使其覆盖其容器。

```html
<div class="bg-indigo-300 ...">
  <img class="object-cover h-48 w-full ...">
</div>
```

<hr/>

#### 填充

使用`.object-fill`拉伸元素内容使其适合其容器的尺寸。

```html
<div class="bg-light-blue-300 ...">
  <img class="object-fill h-48 w-full ...">
</div>
```

<hr/>

#### 清除

使用`.object-none`使元素忽略容器尺寸而显示元素原始尺寸。

```html
<div class="bg-yellow-300 ...">
  <img class="object-none h-48 w-full ...">
</div>
```

<hr/>

#### 缩小

以其原始大小显示元素的内容，但必要时可以使用`.object-scale-down`将该元素缩小以适合其容器。

```html
<div class="bg-green-300">
  <img class="object-scale-down h-48 w-full ...">
</div>
```

<hr/>

### 对象位置

用于控制替换元素的内容应如何放置在其容器中的实用程序。

| 类                    | 属性                            |
| --------------------- | ------------------------------- |
| `object-bottom`       | `object-position:bottom;`       |
| `object-center`       | `object-position:center;`       |
| `object-left`         | `object-position:left;`         |
| `object-left-bottom`  | `object-position:left bottom;`  |
| `object-left-top`     | `object-position:left top;`     |
| `object-right`        | `object-position:right;`        |
| `object-right-bottom` | `object-position:right bottom;` |
| `object-right-top`    | `object-position:right top;`    |
| `object-top`          | `object-position:top;`          |

<hr/>

#### 用法

使用`object-{side}`实用程序来指定替换元素的内容应如何放置在其容器中。

```html
<img class="object-none object-left-top bg-yellow-300 w-24 h-24 ..." src="...">
<img class="object-none object-top bg-yellow-300 w-24 h-24 ..." src="...">
<img class="object-none object-right-top bg-yellow-300 w-24 h-24 ..." src="...">
<img class="object-none object-left bg-yellow-300 w-24 h-24 ..." src="...">
<img class="object-none object-center bg-yellow-300 w-24 h-24 ..." src="...">
<img class="object-none object-right bg-yellow-300 w-24 h-24 ..." src="...">
<img class="object-none object-left-bottom bg-yellow-300 w-24 h-24 ..." src="...">
<img class="object-none object-bottom bg-yellow-300 w-24 h-24 ..." src="...">
<img class="object-none object-right-bottom bg-yellow-300 w-24 h-24 ..." src="...">
```

<hr/>

### 溢出

用于控制元素如何处理对于容器而言太大的内容的实用程序。

| 类                   | 属性                  |
| -------------------- | --------------------- |
| `overflow-auto`      | `overflow:auto;`      |
| `overflow-hidden`    | `overflow:hidden;`    |
| `overflow-visible`   | `overflow:visible;`   |
| `overflow-scroll`    | `overflow:scroll;`    |
| `overflow-x-auto`    | `overflow-x:auto;`    |
| `overflow-y-auto`    | `overflow-y:auto;`    |
| `overflow-x-hidden`  | `overflow-x:hidden;`  |
| `overflow-y-hidden`  | `overflow-y:hidden;`  |
| `overflow-x-visible` | `overflow-x:visible;` |
| `overflow-y-visible` | `overflow-y:visible;` |
| `overflow-x-scroll`  | `overflow-x:scroll;`  |
| `overflow-y-scroll`  | `overflow-y:scroll;`  |

<hr/>

#### 可见

使用`overflow-visible`可以防止元素中的内容被剪裁。请注意，任何超出元素范围的内容都将可见。

```html
<div class="overflow-visible h-24 h- ...">Lorem ipsum dolor sit amet...</div>
```

<hr/>

#### 自动

如果元素的内容溢出该元素的边界，请使用`.overflow-auto`将滚动条添加到该元素。 与始终显示滚动条的`.overflow-scroll`不同，此实用程序仅在需要滚动时才显示它们。

```html
<div class="overflow-auto h-32 ...">Lorem ipsum dolor sit amet...</div>
```

<hr/>

#### 隐藏

使用`overflow-hidden`去裁剪超出元素边界的内容。

```html
<div class="overflow-hidden h-32 ...">Lorem ipsum dolor sit amet...</div>
```

<hr/>

#### 水平滚动

使用`overflow-x-auto`允许**需要时**水平滚动。

```html
<div class="overflow-x-auto ...">QrLmmW69vMQD...</div>
```

使用`overflow-x-scroll`允许**水平滚动并始终显示滚动条**，除非操作系统禁用了始终可见的滚动条。

```html
<div class="overflow-x-scroll ...">QrLmmW69vMQD...</div>
```

<hr/>

#### 垂直滚动

使用`overflow-y-auto`允许**需要时**垂直滚动。

```html
<div class="overflow-y-auto h-32 ...">Lorem ipsum dolor sit amet...</div>
```

使用`overflow-y-scroll`允许**垂直滚动并始终显示滚动条**，除非操作系统禁用了始终可见的滚动条。

```html
<div class="overflow-y-scroll h-32 ...">Lorem ipsum dolor sit amet...</div>
```

<hr/>

#### 全方位滚动

使用`overflow-scroll`将滚动条添加到元素。 与`.overflow-auto`（仅在必要时显示滚动条）不同，此实用程序始终显示它们。 请注意，无论此设置如何，某些操作系统（如macOS）都会隐藏不必要的滚动条。

```html
<div class="overflow-scroll h-32 ...">Lorem ipsum dolor sit amet...</div>
```

<hr/>

### 过度滚动行为

用于控制浏览器到达滚动区域边界时的行为的实用程序。

| 类                     | 属性                             |
| ---------------------- | -------------------------------- |
| `overscroll-auto`      | `overscroll-behavior:auto;`      |
| `overscroll-contain`   | `overscroll-behavior:contain;`   |
| `overscroll-none`      | `overscroll-behavior:none;`      |
| `overscroll-y-auto`    | `overscroll-behavior-y:auto;`    |
| `overscroll-y-contain` | `overscroll-behavior-y:contain;` |
| `overscroll-y-none`    | `overscroll-behavior-y:none;`    |
| `overscroll-x-auto`    | `overscroll-behavior-x:auto;`    |
| `overscroll-x-contain` | `overscroll-behavior-x:contain;` |
| `overscroll-x-none`    | `overscroll-behavior-x:none;`    |

<hr/>

#### 自动

使用`overscroll-auto`可让用户在到达原始滚动区域的边界时继续滚动父滚动区域。

```html
<div class="overscroll-auto ...">Lorem ipsum dolor sit amet...</div>
```

<hr/>

#### 牵制

使用`overscroll-contain`可以防止在到达原始滚动区域的边界时继续滚动父滚动区域，但是在支持容器的操作系统中滚动经过容器的末尾时可以保留“反弹”效果。

```html
<div class="overscroll-contain ...">Lorem ipsum dolor sit amet...</div>
```

<hr/>

#### 清除

使用`overscroll-none`可以防止在到达原始滚动区域的边界时继续滚动父滚动区域，并且还可以防止在滚动超过容器末端时出现“反弹”效果。

```html
<div class="overscroll-none ...">Lorem ipsum dolor sit amet...</div>
```

<hr/>

### 定位

用于控制元素在DOM中的位置的实用程序。

| 类         | 属性                 |
| ---------- | -------------------- |
| `static`   | `position:static;`   |
| `fixed`    | `position:fixed;`    |
| `absolute` | `position:absolute;` |
| `relative` | `position:relative;` |
| `sticky`   | `position:sticky;`   |

<hr/>

#### 静态定位

使用`static`根据文档的正常流程放置元素。

任何偏移量都将被忽略，并且该元素将不会充当绝对定位的子代的位置参考。

```html
<div class="static ...">
  <p>Static parent</p>
  <div class="absolute bottom-0 left-0 ...">
    <p>Absolute child</p>
  </div>
</div>
```

<hr/>

#### 相对定位

使用`relative`根据文档的正常流程放置元素。

相对于元素的正常位置计算偏移，并且元素将充当绝对定位的子代的位置参考。

```html
<div class="relative ...">
  <p>Static parent</p>
  <div class="absolute bottom-0 left-0 ...">
    <p>Absolute child</p>
  </div>
</div>
```

<hr/>

#### 绝对定位

使用`absolute`将元素放置在文档的常规流程之外，从而使相邻元素的行为就像该元素不存在一样。

偏移是相对于最近的父节点（其定位不是`static`）计算的，并且该元素将用作其他绝对定位子节点的位置参考。

```html
<div class="static ...">
  <!-- Static parent -->
  <div class="static ..."><p>Static child</p></div>
  <div class="inline-block ..."><p>Static sibling</p></div>
  <!-- Static parent -->
  <div class="absolute ..."><p>Absolute child</p></div>
  <div class="inline-block ..."><p>Static sibling</p></div>
</div>
```

<hr/>

#### 固定定位

使用`fixed`将元素相对于浏览器窗口定位。

偏移是相对于视口计算的，该元素将充当绝对定位的子代的位置参考。

```html
<div>
  <div class="fixed ...">
    Fixed child
  </div>

  Scroll me!

  Lorem ipsum...
</div>
```

<hr/>

#### 粘滞定位

使用`sticky`将元素定位为`relative`，直到超过指定的阈值，然后将其视为固定元素，直到其父级离开屏幕。

相对于元素的正常位置计算偏移，并且元素将充当绝对定位的子代的位置参考。

```html
<div>
  <div class="sticky top-0 ...">Sticky Heading 1</div>
  <p class="py-4">Quisque cursus...</p>
</div>
<div>
  <div class="sticky top-0 ...">Sticky Heading 2</div>
  <p class="py-4">Integer lacinia...</p>
</div>
<div>
  <div class="sticky top-0 ...">Sticky Heading 3</div>
  <p class="py-4">Nullam mauris...</p>
</div>
<!-- etc. -->
```

<hr/>

### 上/右/下/左

用于控制定位元素放置的实用程序。

[具体类与其属性](https://tailwindcss.com/docs/top-right-bottom-left)

**用法**

使用`{top|right|bottom|left|inset} -0`实用程序将绝对定位的元素锚定在最接近的父对象的任何边缘上。

结合`Tailwind`的`padding`和`margin`工具，您可能会发现这些都是精确控制绝对定位的元素所需要的。

```html
<!-- Span top edge -->
<div class="relative h-32 w-32 ...">
  <div class="absolute inset-x-0 top-0 h-16 w-16 ...">1</div>
</div>

<!-- Span right edge -->
<div class="relative h-32 w-32 ...">
  <div class="absolute inset-y-0 right-0 w-16 ...">2</div>
</div>

<!-- Span bottom edge -->
<div class="relative h-32 w-32 ...">
  <div class="absolute inset-x-0 bottom-0 h-16 w-16 ...">3</div>
</div>

<!-- Span left edge -->
<div class="relative h-32 w-32 ...">
  <div class="absolute inset-y-0 left-0 w-16 ...">4</div>
</div>

<!-- Fill entire parent -->
<div class="relative h-32 w-32 ...">
  <div class="absolute inset-0 ...">5</div>
</div>

<!-- Pin to top left corner -->
<div class="relative h-32 w-32 ...">
  <div class="absolute left-0 top-0 h-16 w-16 ...">6</div>
</div>

<!-- Pin to top right corner -->
<div class="relative h-32 w-32 ...">
  <div class="absolute top-0 right-0 h-16 w-16 ...">7</div>
</div>

<!-- Pin to bottom right corner -->
<div class="relative h-32 w-32 ...">
  <div class="absolute bottom-0 right-0 h-16 w-16 ...">8</div>
</div>

<!-- Pin to bottom left corner -->
<div class="relative h-32 w-32 ...">
  <div class="absolute bottom-0 left-0 h-16 w-16 ...">9</div>
</div>
```

<hr/>

### 可见性

用于控制元素可见性的实用程序。

| 类          | 属性                  |
| ----------- | --------------------- |
| `visible`   | `visibility:visible;` |
| `invisible` | `visibility:hidden;`  |

<hr/>

#### 不可见

使用`invisible`隐藏元素，但仍保留其在`DOM中`的位置，从而影响其他元素的布局（与显示布局中的`.hidden`比较）。

```html
<div class="flex justify-center space-x-4">
  <div>1</div>
  <div class="invisible ...">2</div>
  <div>3</div>
</div>
```

<hr/>

#### 可见

使用`visible`使元素可见。 这对于在不同屏幕尺寸下撤消`invisible`属性很有用。

```html
<div class="flex justify-center space-x-4">
  <div>1</div>
  <div class="visible ...">2</div>
  <div>3</div>
</div>
```

<hr/>

### Z-Index

用于控制元素的堆栈顺序的实用程序。

| Class  | Properties     |
| ------ | -------------- |
| z-0    | z-index: 0;    |
| z-10   | z-index: 10;   |
| z-20   | z-index: 20;   |
| z-30   | z-index: 30;   |
| z-40   | z-index: 40;   |
| z-50   | z-index: 50;   |
| z-auto | z-index: auto; |

**用法**

使用`z- {index}`实用程序控制`Tailwind`中元素的堆栈顺序（或三维定位），无论其显示顺序如何。

```html
<div class="z-40 ...">5</div>
<div class="z-30 ...">4</div>
<div class="z-20 ...">3</div>
<div class="z-10 ...">2</div>
<div class="z-0 ...">1</div>
```

<hr/>

## 弹性盒

### 弹性方向

用于控制弹性项目方向的实用程序。

| 类                 | 属性                             |
| ------------------ | -------------------------------- |
| `flex-row`         | `flex-direction:row;`            |
| `flex-row-reverse` | `flex-direction:row-reverse;`    |
| `flex-col`         | `flex-direction:column;`         |
| `flex-col-reverse` | `flex-direction:column-reverse;` |

<hr/>

#### Row

使用`flex-row`在与文本相同的方向上水平放置弹性项目。

```html
<div class="flex flex-row ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Row-Reverse

使用`flex-row-reverse`在相反的方向上水平放置弹性项目。

```html
<div class="flex flex-row-reverse ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Col

使用`flex-col`垂直放置弹性项目。

```html
<div class="flex flex-col ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Rol-Reverse

使用`flex-col-reverse`在相反的方向上垂直放置弹性项目。

```html
<div class="flex flex-col-reverse ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

### 弹性包装

用于控制弹性项目包装方式的实用程序。

| 类                  | 属性                      |
| ------------------- | ------------------------- |
| `flex-wrap`         | `flex-wrap:wrap;`         |
| `flex-wrap-reverse` | `flex-wrap:wrap-reverse;` |
| `flex-nowrap`       | `flex-wrap:nowrap;`       |

<hr/>

#### No-Wrap

使用`flex-nowrap`防止弹性包装，必要时使非弹性项目溢出容器。

```html
<div class="flex flex-nowrap">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Wrap

使用`flex-wrap`允许弹性项目被包装。

```html
<div class="flex flex-wrap">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Wrap-Reverse

使用`flex-wrap-reverse`以相反的方向包装弹性项。

```html
<div class="flex flex-wrap-reverse">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

### 弹性

用于控制弹性项目如何增长和收缩的实用程序。

| 类             | 属性             |
| -------------- | ---------------- |
| `flex-1`       | `flex:1 1 0%`    |
| `flex-auto`    | `flex:1 1 auto;` |
| `flex-initial` | `flex:0 1 auto;` |
| `flex-none`    | `flex:none;`     |

<hr/>

#### Initial

考虑到其初始大小，请使用`flex-initial`使其收缩但不使其增长。

```html
<div class="flex">
  <div class="flex-initial ...">
    <!-- Won't grow, but will shrink if needed -->
  </div>
  <div class="flex-initial ...">
    <!-- Won't grow, but will shrink if needed -->
  </div>
  <div class="flex-initial ...">
    <!-- Won't grow, but will shrink if needed -->
  </div>
</div>
```

<hr/>

#### Flex 1

使用`flex-1`允许弹性项目根据需要增长和收缩，而忽略其初始大小。

```html
<div class="flex">
  <div class="flex-1 ...">
    <!-- Will grow and shrink as needed without taking initial size into account -->
  </div>
  <div class="flex-1 ...">
    <!-- Will grow and shrink as needed without taking initial size into account -->
  </div>
  <div class="flex-1 ...">
    <!-- Will grow and shrink as needed without taking initial size into account -->
  </div>
</div>
```

<hr/>

#### Auto

考虑到其初始大小，请使用`flex-auto`使弹性项目增长和收缩。

```html
<div class="flex ...">
  <div class="flex-auto ...">
    <!-- Will grow and shrink as needed taking initial size into account -->
  </div>
  <div class="flex-auto ...">
    <!-- Will grow and shrink as needed taking initial size into account -->
  </div>
  <div class="flex-auto ...">
    <!-- Will grow and shrink as needed taking initial size into account -->
  </div>
</div>
```

<hr/>

#### None

使用`flex-none`防止弹性项增长或收缩。

```html
<div class="flex ...">
  <div class="flex-1 ...">
    <!-- Will grow and shrink as needed -->
  </div>
  <div class="flex-none ...">
    <!-- Will grow and shrink as needed taking initial size into account -->
  </div>
  <div class="flex-1 ...">
    <!-- Will grow and shrink as needed -->
  </div>
</div>
```

<hr/>

### 弹性增长

用于控制弹性项目增长方式的实用程序。

| 类            | 属性           |
| ------------- | -------------- |
| `flex-grow-0` | `flex-grow:0;` |
| `flex-grow`   | `flex-grow:1;` |

<hr/>

#### Grow

使用`flex-grow`允许弹性项目增长以填充任何可用空间。

```html
<div class="flex ...">
  <div class="flex-none w-16 h-16 ...">
    <!-- This item will not grow -->
  </div>
  <div class="flex-grow h-16 ...">
    <!-- This item will grow -->
  </div>
  <div class="flex-none w-16 h-16 ...">
    <!-- This item will not grow -->
  </div>
</div>
```

<hr/>

#### Don't grow

使用`flex-grow-0`防止弹性项目增长。

```html
<div class="flex ...">
  <div class="flex-grow h-16 ...">
    <!-- This item will grow -->
  </div>
  <div class="flex-grow-0 h-16 ...">
    <!-- This item will not grow -->
  </div>
  <div class="flex-grow h-16 ...">
    <!-- This item will grow -->
  </div>
</div>
```

<hr/>

### 弹性收缩

用于控制弹性项目收缩方式的实用程序。

| 类              | 属性             |
| --------------- | ---------------- |
| `flex-shrink-0` | `flex-shrink:0;` |
| `flex-shrink`   | `flex-shrink:1;` |

<hr/>

#### Shrink

使用`flex-shrink`允许弹性项目在需要时收缩。

```html
<div class="flex ...">
  <div class="flex-grow w-16 h-16 ...">
    <!-- This item will grow or shrink as needed -->
  </div>
  <div class="flex-shrink w-64 h-16 ...">
    <!-- This item will shrink -->
  </div>
  <div class="flex-grow w-16 h-16 ...">
    <!-- This item will grow or shrink as needed -->
  </div>
</div>
```

<hr/>

#### Don't shrink

使用`flex-shrink-0`防止弹性项目收缩。

```html
<div class="flex ...">
  <div class="flex-1 h-16 ...">
    <!-- This item will grow or shrink as needed -->
  </div>
  <div class="flex-shrink-0 h-16 w-32 ...">
    <!-- This item will not shrink below its initial size-->
  </div>
  <div class="flex-1 h-16 ...">
    <!-- This item will grow or shrink as needed -->
  </div>
</div>
```

<hr/>

### 顺序

用于控制弹性项目顺序的实用程序。

| 类            | 属性           |
| ------------- | -------------- |
| `order-1`     | `order:1;`     |
| `order-2`     | `order:2;`     |
| `order-...`   | `order:...`    |
| `order-first` | `order:-9999;` |
| `order-last`  | `order:9999;`  |
| `order-none`  | `order:0;`     |

**用法**

使用`order- {order}`可以按照与`DOM`中不同的顺序渲染弹性项目。

```html
<div class="flex justify-between ...">
    <div class="order-last">1</div>
    <div>2</div>
    <div>3</div>
</div>
```

<hr/>

## 网格

### 网格模板列

用于指定网格布局中的列的实用程序。

| 类                   | 属性                                                    |
| -------------------- | ------------------------------------------------------- |
| `grid-cols-1`        | `grid-template-columns:repeat(1,minmax(0,1fr));`        |
| `grid-cols-{number}` | `grid-template-columns:repeat({number},minmax(0,1fr));` |
| `grid-cols-none`     | `grid-template-columns:none;`                           |

**用法**

使用`grid-cols- {n}`实用程序创建具有`n`个大小相等的行的网格。

```html
<div class="grid grid-cols-3 gap-4">
  <div>1</div>   
  <!-- ... -->   
  <div>9</div> 
</div>
```

<hr/>

### 网格列开始/结束

用于控制如何在网格列之间调整大小和放置元素的实用程序。

| 类               | 属性                           |
| ---------------- | ------------------------------ |
| `col-auto`       | `grid-column:auto;`            |
| `col-span-{n}`   | `grid-column:span{n}/span{n};` |
| `col-span-full`  | `grid-column:1/-1;`            |
| `col-start-{n}`  | `grid-column-start:{n};`       |
| `col-start-auto` | `grid-column-start:auto;`      |
| `col-end-{n}`    | `grid-column-end:{n};`         |
| `col-end-auto`   | `grid-column-end:auto;`        |

#### Spanning columns

使用`col-span- {n}`实用程序使元素跨越`n`列。

```html
<div class="grid grid-cols-3 gap-4">
  <div class="...">1</div>
  <div class="...">2</div>
  <div class="...">3</div>
  <div class="col-span-2 ...">4</div>
  <div class="...">5</div>
  <div class="...">6</div>
  <div class="col-span-2 ...">7</div>
</div>
```

<hr/>

####  Starting and ending lines

使用`col-start- {n}`和`col-end- {n}`实用程序使元素在第n个网格线处开始或结束。 这些也可以与`col-span- {n}`实用程序结合使用以跨越特定数量的列。

请注意，CSS网格线从1开始，而不是0，因此6列网格中的全宽元素将从第1行开始，到第7行结束。

```html
<div class="grid grid-cols-6 gap-4">
  <div class="col-start-2 col-span-4 ...">1</div>
  <div class="col-start-1 col-end-3 ...">2</div>
  <div class="col-end-7 col-span-2 ...">3</div>
  <div class="col-start-1 col-end-7 ...">4</div>
</div>
```

<hr/>

### 网格模版行

用于指定网格布局中的行的实用程序。

| 类               | 属性                                            |
| ---------------- | ----------------------------------------------- |
| `grid-rows-{n}`  | `grid-template-rows:repeat({n},minmax(0,1fr));` |
| `grid-rows-none` | `grid-template-rows:none;`                      |

**用法**

使用`grid-rows- {n}`实用程序创建具有`n`个大小相等的行的网格。

```html
<div class="h-64 grid grid-rows-3 grid-flow-col gap-4">
  <div>1</div>
  <!-- ... -->
  <div>9</div>
</div>
```

<hr/>

### 网格行开始/结束

| 类               | 属性                        |
| ---------------- | --------------------------- |
| `row-auto`       | `grid-row:auto;`            |
| `row-span-{n}`   | `grid-row:span{n}/span{n};` |
| `row-span-full`  | `grid-row:1/-1;`            |
| `row-start-{n}`  | `grid-row-start:{n};`       |
| `row-start-auto` | `grid-row-start:auto;`      |
| `row-end-{n}`    | `grid-row-end:{n};`         |
| `row-end-auto`   | `grid-row-end:auto;`        |

<hr/>

#### Spanning rows

使用`row-span-{n}`使用程序使元素横跨n行。

```html
<div class="grid grid-rows-3 grid-flow-col gap-4">
  <div class="row-span-3 ...">1</div>
  <div class="col-span-2 ...">2</div>
  <div class="row-span-2 col-span-2 ...">3</div>
</div>
```

<hr/>

#### Starting and ending lines

使用`row-start- {n}`和`row-end- {n}`实用程序使元素在第`n`个网格线处开始或结束。 这些也可以与`row-span- {n}`实用程序结合使用，以跨越特定数量的行。

请注意，CSS网格线从1开始，而不是0，因此3行网格中的全高元素将从第1行开始，到第4行结束。

```html
<div class="grid grid-rows-3 grid-flow-col gap-4">
  <div class="row-start-2 row-span-2 ...">1</div>
  <div class="row-end-3 row-span-2 ...">2</div>
  <div class="row-start-1 row-end-4 ...">3</div>
</div>
```

<hr/>

### 网格自动漂浮

用于控制如何自动放置网格中的元素的实用程序。

| 类                    | 属性                            |
| --------------------- | ------------------------------- |
| `grid-flow-row`       | `grid-auto-flow: row;`          |
| `grid-flow-col`       | `grid-auto-flow: column;`       |
| `grid-flow-row-dense` | `grid-auto-flow: row dense;`    |
| `grid-flow-col-dense` | `grid-auto-flow: column dense;` |

<hr/>

**用法**

使用`grid-flow- {keyword}`实用程序来控制自动放置算法对网格布局的工作方式。

```html
<div class="grid grid-flow-col grid-cols-3 grid-rows-3 gap-4">
  <div>1</div>
  <!-- ... -->
  <div>9</div>
</div>
```

<hr/>

### 网格自动列

用于控制隐式创建的网格列的大小的实用程序。

| 类               | 属性                               |
| ---------------- | ---------------------------------- |
| `auto-cols-auto` | `grid-auto-columns:auto;`          |
| `auto-cols-min`  | `grid-auto-columns:min-content;`   |
| `auto-cols-max`  | `grid-auto-columns:max-content;`   |
| `auto-cols-fr`   | `grid-auto-columns:minmax(0,1fr);` |

<hr/>

**用法**

使用`auto-cols-{size}`实用程序控制隐式创建的网格列的大小。

```html
<div class="grid grid-flow-col auto-cols-max">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

### 网格自动行

用于控制隐式创建的网格行的大小的实用程序。

| 类               | 属性                            |
| ---------------- | ------------------------------- |
| `auto-rows-auto` | `grid-auto-rows:auto;`          |
| `auto-rows-min`  | `grid-auto-rows:min-content;`   |
| `auto-rows-max`  | `grid-auto-rows:max-content;`   |
| `auto-rows-fr`   | `grid-auto-rows:minmax(0,1fr);` |

<hr/>

**用法**

使用`auto-rows-{size}`实用程序控制隐式创建的网格行的大小。

```html
<div class="grid grid-flow-row auto-rows-max">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

### 间隙

用于控制网格行和列之间的装订线的实用程序。

[具体类和属性][https://tailwindcss.com/docs/gap]

#### gap-{size}

使用`gap- {size}`更改网格布局中行和列之间的间隙。

```html
<div class="grid gap-4 grid-cols-2">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
```

#### gap-x-{size} and gap-y-{size}

使用`gap-x- {size}`和`gap-y- {size}`分别更改行和列之间的间隙。

```html
<div class="grid gap-x-8 gap-y-4 grid-cols-3">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

## 框对齐

### Justify Content

用于控制如何沿容器的主轴放置`flex`和`grid`项目的实用程序。

| 类                | 属性                             |
| ----------------- | -------------------------------- |
| `justify-start`   | `justify-content:flex-start;`    |
| `justify-end`     | `justify-content:flex-end;`      |
| `justify-center`  | `justify-content:center;`        |
| `justify-between` | `justify-content:space-between;` |
| `justify-around`  | `justify-content:space-around;`  |
| `justify-evenly`  | `justify-content:space-evenly;`  |

<hr/>

#### Start

使用`justify-start`可以使项目相对于容器主轴的起点进行对齐：

```html
<div class="flex justify-start ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Center

使用`justify-center`可以使沿着容器主轴中心的项目对齐：

```html
<div class="flex justify-center ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### End

使用`justify-end`来使项目相对于容器主轴的末端对齐：

```html
<div class="flex justify-end ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Space between

使用`justify-between`沿着容器的主轴对齐项目，以使每个项目之间有相等的空间：

```html
<div class="flex justify-between ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Space around

使用`justify-around`沿容器的主轴对齐项目，以便每个项目的每一侧都有相等的空间：

```html
<div class="flex justify-around ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Space evenly

使用`justify-evenly`沿容器的主轴对齐项目，以使每个项目周围有相等的空间，但也要考虑到当您使用`justify-around`时，通常会在每个项目之间看到的空间增加一倍：

```html
<div class="flex justify-evenly ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

### Justify Items

用于控制`grid`项如何沿其内联轴对齐的实用程序。

| 类                      | 属性                     |
| ----------------------- | ------------------------ |
| `justify-items-auto`    | `justify-items:auto;`    |
| `justify-items-start`   | `justify-items:start;`   |
| `justify-items-end`     | `justify-items:end;`     |
| `justity-items-center`  | `justify-items:center;`  |
| `justify-items-stretch` | `justify-items:stretch;` |

<hr/>

#### Auto

使用`justify-items-auto`在其内联轴上自动对齐网格项目：

```html
<div class="grid justify-items-auto ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Start

使用`justify-items-start`相对于其内联轴的起点来对齐网格项目：

```html
<div class="grid justify-items-start ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### End

使用`justify-items-end`相对于其内联轴的末端对齐网格项目：

```html
<div class="grid justify-items-end ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Center

使用`justify-items-center`沿其内联轴对齐网格项目：

```html
<div class="grid justify-items-center ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Stretch

使用`justify-items-stretch`沿其内联轴拉伸项目：

```html
<div class="grid justify-items-stretch ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

### Justify Self

用于控制单个`grid`项如何沿其内联轴对齐的实用程序。

| 类                     | 属性                    |
| ---------------------- | ----------------------- |
| `justify-self-auto`    | `justify-self:auto;`    |
| `justify-self-start`   | `justify-self:start;`   |
| `justify-self-end`     | `justify-self:end;`     |
| `justify-self-center`  | `justify-self:center;`  |
| `justify-self-stretch` | `justify-self:stretch;` |

<hr/>

#### Auto

使用`justify-self-auto`根据网格的`justify-items`属性的值对齐项目：

```html
<div class="grid justify-items-stretch ...">
  <!-- ... -->
  <div class="justify-self-auto ...">1</div>
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
</div>
```

<hr/>

#### Start

使用`justify-self-start`将网格项与其内联轴的起点对齐：

```html
<div class="grid justify-items-stretch ...">
  <!-- ... -->
  <div class="justify-self-start ...">1</div>
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
</div>
```

#### Center

使用`justify-self-center`将网格项沿其内联轴的中心对齐：

```html
<div class="grid justify-items-stretch ...">
  <!-- ... -->
  <div class="justify-self-center ...">1</div>
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
</div>
```

<hr/>

#### End

使用`justify-self-end`将网格项与其内联轴的末端对齐：

```html
<div class="grid justify-items-stretch ...">
  <!-- ... -->
  <div class="justify-self-end ...">1</div>
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
</div>
```

<hr/>

#### Stretch

使用`justify-self-stretch`拉伸网格项目以填充其内联轴上的网格区域：

```html
<div class="grid justify-items-start ...">
  <!-- ... -->
  <div class="justify-self-stretch ...">1</div>
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
  <!-- ... -->
</div>
```

<hr/>

### Align Content

用于控制如何在多行`flex`和`grid`容器中放置行的实用程序。

| 类                | 属性                           |
| ----------------- | ------------------------------ |
| `content-center`  | `align-content:center;`        |
| `content-start`   | `align-content:flex-start;`    |
| `content-end`     | `align-content:flex-end;`      |
| `content-between` | `align-content:space-between;` |
| `content-around`  | `align-content:space-around;`  |
| `content-evenly`  | `align-content:space-evenly;`  |

<hr/>

#### Start

使用`content-start`可以将容器中的行相对于横轴的起点打包：

```html
<div class="h-48 flex flex-wrap content-start ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>
```

<hr/>

#### Center

使用`content-center`将容器中的行相对于横轴中心打包：

```html
<div class="h-48 flex flex-wrap content-center ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>
```

<hr/>

#### End

使用`content-start`可以将容器中的行相对于横轴的终点打包：

```html
<div class="h-48 flex flex-wrap content-end ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>
```

<hr/>

#### Space between

使用`content-between`来分布容器中的行，以使每行之间有相等的空间：

```html
<div class="h-48 flex flex-wrap content-between ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>
```

<hr/>

#### Space around

使用`content-around`来分布容器中的行，以便每行周围有相等的空间：

```html
<div class="h-48 flex flex-wrap content-around ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
</div>
```

<hr/>

### Align Items

用于控制`flex`和`grid`项目如何沿容器的横轴放置的实用程序。

| 类               | 属性                      |
| ---------------- | ------------------------- |
| `items-start`    | `align-items:flex-start;` |
| `items-end`      | `align-items:flex-end;`   |
| `items-center`   | `align-items:center;`     |
| `items-baseline` | `align-items:baseline;`   |
| `items-stretch`  | `align-items:stretch;`    |

<hr/>

#### Stretch

使用`items-stretch`拉伸项目以填充容器的横轴：

```html
<div class="flex items-stretch ...">
  <div class="py-4">1</div>
  <div class="py-12">2</div>
  <div class="py-8">3</div>
</div>
```

<hr/>

#### Start

使用`items-start`将项目与容器横轴的起点对齐：

```html
<div class="flex items-start ...">
  <div class="h-12">1</div>
  <div class="h-24">2</div>
  <div class="h-16">3</div>
</div>
```

<hr/>

#### Center

使用`items-center`沿着容器的横轴中心对齐项目：

```html
<div class="flex items-center ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### End

使用`items-end`将项目与容器横轴的末端对齐：

```html
<div class="flex items-end ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### Baseline

使用`items-baseline`沿容器的横轴对齐项目，以使所有基线对齐：

```html
<div class="flex items-baseline ...">
  <div class="pt-4 pb-6 ...">1</div>
  <div class="pt-6 pb-10 ...">2</div>
  <div class="pt-8 pb-4 ...">3</div>
</div>
```

<hr/>

### Align Self

用于控制单个`flex`或`grid`项目如何沿其容器的横轴放置的实用程序。

| 类             | 属性                     |
| -------------- | ------------------------ |
| `self-auto`    | `align-self:auto;`       |
| `self-start`   | `align-self:flex-start;` |
| `self-end`     | `align-self:flex-end;`   |
| `self-center`  | `align-self:center;`     |
| `self-stretch` | `align-self:stretch;`    |

<hr/>

#### Auto

使用`self-auto`将项目根据容器的`align-items`属性的值进行对齐：

```html
<div class="flex items-stretch ...">
  <div>1</div>
  <div class="self-auto ...">2</div>
  <div>3</div>
</div>
```

<hr/>

#### Start

尽管容器具有`align-items`值，但也可以使用`self-start`将项目与容器的横轴的起点对齐：

```html
<div class="flex items-stretch ...">
  <div>1</div>
  <div class="self-start ...">2</div>
  <div>3</div>
</div>
```

<hr/>

#### Center

尽管容器具有`align-items`值，也可以使用`self-center`沿容器的横轴中心对齐项目：

```html
<div class="flex items-stretch ...">
  <div>1</div>
  <div class="self-center ...">2</div>
  <div>3</div>
</div>
```

<hr/>

#### End

尽管容器具有`align-items`值，也可以使用`self-end`将项目与容器横轴的末端对齐：

```html
<div class="flex items-stretch ...">
  <div>1</div>
  <div class="self-end ...">2</div>
  <div>3</div>
</div>
```

<hr/>

#### Stretch

尽管容器的`align-items`值，使用自拉伸来拉伸项目以填充容器的横轴：

```html
<div class="flex items-stretch ...">
  <div>1</div>
  <div class="self-stretch ...">2</div>
  <div>3</div>
</div>
```

<hr/>

### Place Content

用于控制内容同时用`justified`和`aligned`对齐方式的实用程序。

| 类                      | 属性                           |
| ----------------------- | ------------------------------ |
| `place-content-center`  | `place-content:center;`        |
| `place-content-start`   | `place-content:start;`         |
| `place-content-end`     | `place-content:end;`           |
| `place-content-between` | `place-content:space-between;` |
| `place-content-around`  | `place-content:space-around;`  |
| `place-content-evenly`  | `place-content:space-evenly;`  |
| `place-content-stretch` | `place-content:stretch;`       |

<hr/>

#### Center

使用`place-content-center`将项目打包在块轴的中心：

```html
<div class="grid grid-cols-3 gap-2 place-content-center h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Start

使用`place-content-start`相对于块轴的起点打包项目：

```html
<div class="grid grid-cols-3 gap-2 place-content-start h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### End

使用`place-content-end`相对于块轴的末端打包项目：

```html
<div class="grid grid-cols-3 gap-2 place-content-end h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Space between

使用`place-content-between`在块轴上分配网格项，以使块轴上的每一行之间有相等的空间。

```html
<div class="grid grid-cols-3 gap-2 place-content-between h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Space around

使用`place-content-around`分布的网格项目，以使块轴上的每一行周围有相等的空间：

```html
<div class="grid grid-cols-3 gap-2 place-content-around h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Space-evenly

均匀使用`place-content`来分布网格项目，以使它们在块轴上均匀分布：

```html
<div class="grid grid-cols-3 gap-2 place-content-evenly h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Stretch

使用`place-content-stretch`沿着网格块轴上的网格区域拉伸网格项目：

```html
<div class="grid grid-cols-3 gap-2 place-content-stretch h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

### Place Items

用于控制项目同时用`justified`和`aligned`对齐方式的实用程序。

| 类                    | Properties              |
| --------------------- | ----------------------- |
| `place-items-auto`    | `place-items: auto;`    |
| `place-items-start`   | `place-items: start;`   |
| `place-items-end`     | `place-items: end;`     |
| `place-items-center`  | `place-items: center;`  |
| `place-items-stretch` | `place-items: stretch;` |

<hr/>

#### Auto

使用`place-items-auto`将网格项目自动放置在其网格区域中：

```html
<div class="grid grid-cols-3 gap-2 place-items-auto h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Start

使用`place-items-start`将网格项目放置在两个轴上其网格区域的开始处：

```html
<div class="grid grid-cols-3 gap-2 place-items-start h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### End

使用`place-items-end`将网格项放置在两个轴上其网格区域的末端：

```html
<div class="grid grid-cols-3 gap-2 place-items-end h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Center

使用`place-items-center`在两个轴上将网格项放置在其网格区域的中心：

```html
<div class="grid grid-cols-3 gap-2 place-items-center h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Stretch

使用`place-items-stretch`在两个轴上沿其网格区域拉伸项目：

```html
<div class="grid grid-cols-3 gap-2 place-items-stretch h-48 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

### Place Self

用于控制单个项目同时用`justified`和`aligned`对齐方式的实用程序。

| 类                   | 属性                   |
| -------------------- | ---------------------- |
| `place-self-auto`    | `place-self: auto;`    |
| `place-self-start`   | `place-self: start;`   |
| `place-self-end`     | `place-self: end;`     |
| `place-self-center`  | `place-self: center;`  |
| `place-self-stretch` | `place-self: stretch;` |

<hr/>

#### Auto

使用`place-self-auto`可以根据容器的`place-items`属性的值来对齐项目：

```html
<div class="grid grid-cols-3 gap-2 ...">
  <div>1</div>
  <div class="place-self-auto ...">2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Start

使用`place-self-start`来使项目与两个轴上的起点对齐：

```html
<div class="grid grid-cols-3 gap-2 ...">
  <div>1</div>
  <div class="place-self-start ...">2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Center

使用`place-self-center`来使项目在两个轴的中心对齐：

```html
<div class="grid grid-cols-3 gap-2 ...">
  <div>1</div>
  <div class="place-self-center ...">2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### End

使用`place-self-end`将项目与两个轴的末端对齐：

```html
<div class="grid grid-cols-3 gap-2 ...">
  <div>1</div>
  <div class="place-self-end ...">2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

#### Stretch

使用`place-self-stretch`在两个轴上拉伸项目：

```html
<div class="grid grid-cols-3 gap-2 ...">
  <div>1</div>
  <div class="place-self-stretch ...">2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

<hr/>

## 间距

### 内边距

用于控制元素内边距的实用程序。

| 类          | 属性                                              |
| ----------- | ------------------------------------------------- |
| `p-{size}`  | `padding:{size};`                                 |
| `py-{size}` | `padding-top:{size};`<br>`padding-bottom:{size};` |
| `px-{size}` | `padding-left:{size};`<br>`padding-right:{size};` |
| `pt-{size}` | `padding-top:{size};`                             |
| `pr-{size}` | `padding-right:{size};`                           |
| `pb-{size}` | `padding-bottom:{size};`                          |
| `pl-{size}` | `padding-left:{size};`                            |

<hr/>

#### 将内边距添加到单面

使用`p {t | r | b | l}-{size}`实用程序控制元素一侧的内边距。

例如，`pt-6`将在元素顶部添加`1.5rem`的内边距，`pr-4`将在元素右侧添加`1rem`的内边距，`pb-8`将在元素底部添加`2rem`的内边距，` pl-2`将在元素的左侧添加`0.5rem`的内边距。

```html
<div class="pt-6 ...">pt-6</div>
<div class="pr-4 ...">pr-4</div>
<div class="pb-8 ...">pb-8</div>
<div class="pl-2 ...">pl-2</div>
```

<hr/>

#### 水平添加内边距

使用`px-{size}`实用程序控制元素水平内边距。

```html
<div class="px-8 ...">px-8</div>
```

<hr/>

#### 垂直添加内边距

使用`py-{size}`实用程序控制元素垂直内边距。

```html
<div class="py-8 ...">py-8</div>
```

<hr/>

#### 在所有面添加内边距

使用`p-{size}`实用程序控制元素所有面的内边距。

```html
<div class="p-8 ...">p-8</div>
```

<hr/>

### 外边距

用于控制元素外边距的实用程序。

| 类                                  | 属性                                            |
| ----------------------------------- | ----------------------------------------------- |
| `m-{size}`                          | `margin:{size};`                                |
| `-m-{size}`(后面每一种都可以加负号) | `margin:-{size};`                               |
| `my-{size}`                         | `margin-top:{size};`<br>`margin-bottom:{size};` |
| `mx-{size}`                         | `margin-left:{size};`<br>`margin-right:{size};` |
| `mt-{size}`                         | `margin-top:{size};`                            |
| `mr-{size}`                         | `margin-right:{size};`                          |
| `mb-{size}`                         | `margin-bottom:{size};`                         |
| `ml-{size}`                         | `margin-left:{size};`                           |

<hr/>

#### 将外边距添加到单面

使用`m {t | r | b | l}-{size}`实用程序控制元素一侧的外边距。

例如，`mt-6`将在元素顶部添加`1.5rem`的外边距，`mr-4`将在元素右侧添加`1rem`的外边距，`mb-8`将在元素底部添加`2rem`的外边距， `ml-2`将在元素左侧增加`0.5rem`的外边距。

```html
<div class="mt-8 ...">mt-8</div>
<div class="mr-8 ...">mr-8</div>
<div class="mb-8 ...">mb-8</div>
<div class="ml-8 ...">ml-8</div>
```

<hr/>

#### 水平添加外边距

使用`mx-{size}`控制元素水平外边距。

```html
<div class="mx-8 ...">mx-8</div>
```

<hr/>

#### 垂直添加外边距

使用`my-{size}`控制元素垂直外边距。

```html
<div class="my-8 ...">my-8</div>
```

<hr/>

#### 在所有面添加外边距

使用`m-{size}`控制元素所有面的外边距。

```html
<div class="m-8 ...">m-8</div>
```

<hr/>

### 元素间间距

用于控制子元素之间间距的实用程序。

| 类                 | 属性                                                         |
| ------------------ | ------------------------------------------------------------ |
| `space-y-{amount}` | `--tw-space-y-reverse:0`<br>`margin-top:calc({amount}*calc(1-var(--tw-space-y-reverse)));`<br>`margin-bottom:calc({amount}*var(--tw-space-y-reverse));` |
| `space-y-reverse`  | `--tw-space-y-reverse:1;`                                    |
| `space-x-{amount}` | `--tw-space-x-reverse: 0; `<br>`margin-right: calc({amount} * var(--tw-space-x-reverse)); `<br>`margin-left: calc({amount} * calc(1 - var(--tw-space-x-reverse)));` |
| `space-x-reverse`  | `--tw-space-x-reverse: 1;`                                   |

<hr/>

 #### 添加水平元素间间距

使用`space-x-{amount}`控制水平元素间间距。

```html
<div class="flex space-x-4 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### 添加垂直元素间间距

使用`space-y-{amount}`控制垂直元素间间距。

```html
<div class="flex space-y-6 ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

#### 倒置子元素顺序

如果您的元素顺序相反（使用`flex-row-reverse`或`flex-col-reverse`），请使用`space-x-reverse`或`space-y-reverse`实用程序以确保将空格添加到每个元素的正确边 。

```html
<div class="flex flex-row-reverse space-x-4 space-x-reverse ...">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

<hr/>

## 尺寸

### Width

用于设置元素宽度的实用程序。

| 类             | 属性                      |
| -------------- | ------------------------- |
| `w-{number}`   | `width:{number*0.25}rem;` |
| `w-auto`       | `width:auto;`             |
| `w-px`         | `width:1px;`              |
| `w-{fraction}` | `width:{fraction}%;`      |
| `w-full`       | `width:100%;`             |
| `w-screen`     | `width:100vw;`            |
| `w-min`        | `width:min-content;`      |
| `w-max`        | `width:max-content;`      |

<hr/>

#### Auto

使用`w-auto`让浏览器计算并选择元素的宽度。 您可以使用它来取消设置特定的宽度：

```html
<div class="w-24 md:w-auto ..."></div>
```

<hr/>

#### Screen Width

使用`w-screen`使元素跨越视口的整个宽度。

```html
<div class="h-12 w-screen">
  
</div>
```

<hr/>

#### Fixed Width

使用`w-{number}`或`w-px`设置元素固定宽度。

```html
<div>
  <div class="w-8 ..."></div>
  <div class="w-12 ..."></div>
  <div class="w-16 ..."></div>
  <div class="w-24 ..."></div>
</div>
```

<hr/>

#### Fluid Width

使用`w- {fraction}`或`w-full`将元素设置为基于百分比的宽度。

```html
<div class="flex ...">
  <div class="w-1/2 ...">w-1/2</div>
  <div class="w-1/2 ...">w-1/2</div>
</div>
<div class="flex ...">
  <div class="w-2/5 ...">w-2/5</div>
  <div class="w-3/5 ...">w-3/5</div>
</div>
<div class="flex ...">
  <div class="w-1/3 ...">w-1/3</div>
  <div class="w-2/3 ...">w-2/3</div>
</div>
<div class="flex ...">
  <div class="w-1/4 ...">w-1/4</div>
  <div class="w-3/4 ...">w-3/4</div>
</div>
<div class="flex ...">
  <div class="w-1/5 ...">w-1/5</div>
  <div class="w-4/5 ...">w-4/5</div>
</div>
<div class="flex ...">
  <div class="w-1/6 ...">w-1/6</div>
  <div class="w-5/6 ...">w-5/6</div>
</div>
<div class="w-full ...">w-full</div>
```

<hr/>

### Min-Width

用来设置元素最小宽度的实用程序。

| 类           | 属性                     |
| ------------ | ------------------------ |
| `min-w-0`    | `min-width:0px;`         |
| `min-w-full` | `min-width:100%;`        |
| `min-w-min`  | `min-width:min-content;` |
| `min-w-max`  | `min-width:max-content;` |

<hr/>

#### Usage

使用`min-w-0`或`min-w-full`实用程序设置元素的最小宽度。

```html
<div class="w-24 min-w-full ...">
  min-w-full
</div>
```

<hr/>

### Max-Width

用来设置元素最大宽度的实用程序。

| 类                 | 属性                     |
| ------------------ | ------------------------ |
| `max-w-0`          | `max-width:0rem;`        |
| `max-w-none`       | `max-width:none;`        |
| `max-w-xs`         | `max-width:20rem;`       |
| `max-w-sm`         | `max-width:24rem;`       |
| `max-w-md`         | `max-width:28rem;`       |
| `max-w-lg`         | `max-width:32rem;`       |
| `max-w-xl`         | `max-width:36rem;`       |
| `max-w-2xl`        | `max-width:42rem;`       |
| `max-w-3xl`        | `max-width:48rem;`       |
| `max-w-4xl`        | `max-width:56rem;`       |
| `max-w-5xl`        | `max-width:64rem;`       |
| `max-w-6xl`        | `max-width:72rem;`       |
| `max-w-7xl`        | `max-width:80rem;`       |
| `max-w-full`       | `max-width:100%;`        |
| `max-w-min`        | `max-width:min-content;` |
| `max-w-max`        | `max-width:max-content;` |
| `max-w-prose`      | `max-width:65ch;`        |
| `max-w-screen-sm`  | `max-width:640px;`       |
| `max-w-screen-md`  | `max-width:768px;`       |
| `max-w-screen-lg`  | `max-width:1024px;`      |
| `max-w-screen-xl`  | `max-width:1280px;`      |
| `max-w-screen-2xl` | `max-width:1536px;`      |

<hr/>

#### Usage

使用`max-w-{size}`实用程序来设置元素的最大宽度。

```html
<div class="max-w-md mx-auto ...">
  max-w-md
</div>
```

<hr/>

#### Prose

默认情况下，我们添加了一个新的最大宽度`max-w-prose`。 如果您熟悉`typography plugin`，您可能会认识到这一点。 这个类的目的是让您拥有最佳的阅读宽度。

```html
<div class="max-w-prose ...">
  <p class="font-bold">Why do you never see elements hiding in trees?</p>
  <p>Because they're so good at it. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas cupiditate laboriosam fugiat.</p>
</div>
```

<hr/>

### Height

用于设置元素高度的实用程序。

| 类             | 属性                       |
| -------------- | -------------------------- |
| `h-{number}`   | `height:{number*0.25}rem;` |
| `h-auto`       | `height:auto;`             |
| `h-px`         | `height:1px;`              |
| `h-{fraction}` | `height:{fraction}%;`      |
| `h-full`       | `height:100%;`             |
| `h-screen`     | `height:100vh;`            |

<hr/>

#### Auto

使用`h-auto`让浏览器自动决定元素的高度。

```html
<div class="h-auto ...">h-auto</div>
```

<hr/>

#### Screen height

使用`h-screen`让元素充满整个视口的高度。

```html
<div class="h-screen p-6 ...">h-screen</div>
```

<hr/>

#### Fixed height

使用`h-{number}`或`h-px`设置固定高度的元素。

```html
<div>
    <div class="h-8 ..."></div>
    <div class="h-12 ..."></div>
    <div class="h-16 ..."></div>
    <div class="h-24 ..."></div>
</div>
```

<hr/>

#### Full height

如果父元素的高度已定义，使用`h-full`将元素的高度设置为其父元素的高度的100％。

```html
<div class="h-48">
  <div class="h-full ...">h-full</div>
</div>
```

<hr/>

### Min-Height

用于设置元素最小高度的实用程序。

| 类             | 属性                |
| -------------- | ------------------- |
| `min-h-0`      | `min-height:0px;`   |
| `min-h-full`   | `min-height:100%;`  |
| `min-h-screen` | `min-height:100vh;` |

<hr/>

#### Usage

使用`min-h-0`，`min-h-full`或`min-h-screen`实用程序设置元素的最小高度。

```html
<div class="h-48 ...">
  <div class="h-24 min-h-full ...">
    .min-h-full
  </div>
</div>
```

<hr/>

### Max-Height

用于设置元素最大高度的实用程序。

| 类               | 属性                      |
| ---------------- | ------------------------- |
| `max-h-{number}` | `max-height:{number}rem;` |
| `max-h-px`       | `max-height:1px;`         |
| `max-h-full`     | `max-height:100%;`        |
| `max-h-screen`   | `max-height:100vh;`       |

<hr/>

#### Usage

使用`max-h-full`或`max-h-screen`实用程序来设置元素的最大高度。

```html
<div class="h-24 ...">
  <div class="h-48 max-h-full ...">
    .max-h-full
  </div>
</div>
```

<hr/>

## 板式

### Font Family

用于控制元素的字体。

| 类           | 属性                                                         |
| ------------ | ------------------------------------------------------------ |
| `font-sans`  | `font-family:ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";` |
| `font-serif` | `font-family: ui-serif, Georgia, Cambria, "Times New Roman", Times, serif;` |
| `font-mono`  | `font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;` |

<hr/>

#### Sans-serif

使用`font-sans`来应用`Web`安全的`sans-serif`字体家族：

```html
<p class="font-sans ...">
  The quick brown fox jumps over the lazy dog.
</p>
```

<hr/>

#### Serif

使用`font-serif`来应用`Web`安全`serif`字体家族：

```html
<p class="font-serif ...">
  The quick brown fox jumps over the lazy dog.
</p>
```

<hr/>

#### Monospaced

使用`font-mono`可以应用`Web`安全`monospaced`字体家族：

```html
<p class="font-mono ...">
  The quick brown fox jumps over the lazy dog.
</p>
```

<hr/>

### Font Size

用于控制元素字体大小的实用程序。

| 类          | 属性                                             |
| ----------- | ------------------------------------------------ |
| `text-xs`   | `font-size:0.75rem;`<br/>`line-height:1rem;`     |
| `text-sm`   | `font-size:0.875rem;`<br/>`line-height:1.25rem;` |
| `text-base` | `font-size:1rem;`<br/>`line-height:1.5rem;`      |
| `text-lg`   | `font-size:1.125rem;`<br/>`line-height:1.75rem;` |
| `text-xl`   | `font-size:1.25rem;`<br/>`line-height:1.75rem;`  |

<hr/>

#### Usage

使用`text-{size}`实用程序来控制元素字体大小。

```html
<p class="text-xs ...">The quick brown fox ...</p>
<p class="text-sm ...">The quick brown fox ...</p>
<p class="text-base ...">The quick brown fox ...</p>
<p class="text-lg ...">The quick brown fox ...</p>
<p class="text-xl ...">The quick brown fox ...</p>
<p class="text-2xl ...">The quick brown fox ...</p>
<p class="text-3xl ...">The quick brown fox ...</p>
<p class="text-4xl ...">The quick brown fox ...</p>
<p class="text-5xl ...">The quick brown fox ...</p>
<p class="text-6xl ...">The quick brown fox ...</p>
<p class="text-7xl ...">The quick brown fox ...</p>
<p class="text-8xl ...">The quick brown fox ...</p>
<p class="text-9xl ...">The quick brown fox ...</p>
```

<hr/>


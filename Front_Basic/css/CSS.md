# CSS

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



## 布局

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


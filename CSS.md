# CSS









## 样式

1. 内联样式：通过HTML元素的style属性来设置CSS样式，写在header里面。语法如下:

```css
/*内联样式1*/
style="css属性:css属性值;"
/*内联样式2*/
<style type="text/css">
	选择器 {
		属性名 : 属性值;
	}
</style>
```

2. 外联样式：通过HTML页面的link元素来引入外部CSS样式，语法如下:

```html
<link href="css文件路径" rel="stylesheet" type="text/css" />
```

## 语法格式

```html
选择器 {属性名称 : 属性值; 属性名称 : 属性值;...}

- CSS声明总是以键值对(key\value)形式存在。
- CSS声明总是以分号(;)结束。
- 声明组以大括号({})括起来。
- 为了让CSS可读性更强，每行只描述一个属性。
```

## 设置颜色值

```css
/*第一种方式*/
#show1 {color : red;}

/*第二种方式*/
#show2 {color : #ff0000;}
/*像上面这种使用十六进制设置颜色时，如果两两相同，可以写成如下格式:*/
#show2 {color : #f00;}

/*第三种方式*/
#show3 {color : rgb(255,0,0);}
/*上面的格式还可以写成如下格式:*/
#show3 {color : rgb(100%,0%,0%);}
```



> **值得注意的是:** 当使用 RGB 百分比时，即使当值为 0 时也要写百分比符号。但是在其他的情况下就不需要这么做了。



## 块级元素和内联元素



### 值为若干单词，记得写引号

```
div {font-family : Courier, "Courier New", monospace;}
```

### 多重声明

如果要定义不止一个声明，则需要用分号将每个声明分开。

### 空格和大小写

大多数样式表包含不止一条规则，而大多数规则包含不止一个声明。多重声明和空格的使用使得样式表更容易被编辑。



大多数 HTML 元素被定义为**块级元素**或**内联元素**。

### 10. 块级元素

块级元素在浏览器显示时，通常会以新行来开始（和结束）。

我们已经学习过的块级元素有: `<h1>`, `<p>`, `<ul>`, `<table>` 等。

> **值得注意的是:** `<p>` 标签中不能包含任何块级元素。

## `<div>` 元素

`<div>` 元素是块级元素，它可用于组合其他 HTML 元素的容器。

`<div>` 元素没有特定的含义。除此之外，由于它属于块级元素，浏览器会在其前后显示折行。

如果与 CSS 一同使用，`<div>` 元素可用于对大的内容块设置样式属性。

`<div>` 元素的另一个常见的用途是文档布局。

> **值得注意的是:** `<div>` 取代了使用表格定义布局的老式方法。

## 内联元素

内联元素在显示时通常不会以新行开始。

我们已经学习过的内联元素有: `<td>`, `<a>`, `<img>` 等。

> **值得注意的是:** `<a>` 标签中不能包含 `<a>` 标签，但可以包含其他任何元素。

## `<span>` 元素

`<span>` 元素是内联元素，可用作文本的容器。`<span>` 元素也没有特定的含义。

当与 CSS 一同使用时，`<span>` 元素可用于为部分文本设置样式属性。

> **值得注意的是:** 内联元素中不能包含块级元素。一般都是块级元素中包含内联元素。



## 元素选择器

元素选择器就是通过 HTML 页面的元素名称来设置 CSS 样式。具体语法如下:

```
元素名称 { 属性名 : 属性值; }
```

示例代码:

```
div {color : red; }
```

## 类选择器

类选择器就是通过 HTML 元素的 class 属性值来设置 CSS 样式。具体语法如下:

```
.class属性值 { 属性名 : 属性值; }
```

示例代码:

```
.myDiv {color : red; }
```

## ID选择器

ID选择器就是通过 HTML 元素的 id 属性值来设置 CSS 样式。具体语法如下:

```
#id属性值 { 属性名 : 属性值; }
```

示例代码:

```
#show1 {color : red; }
```

## 属性选择器

属性选择器就是通过 HTML 元素的属性名称来设置 CSS 样式。具体语法如下:

```
[属性名称] { 属性名 : 属性值; }
```

示例代码:

```
[name] {color : red; }
```

| 选择器             | 描述                                 |
| ------------------ | ------------------------------------ |
| [attribute]        | 用于选取带有指定属性的元素。         |
| [attribute=value]  | 用于选取带有指定属性和值的元素。     |
| [attribute~=value] | 用于选取属性值中包含指定词汇的元素。 |
| [attribute^=value] | 匹配属性值以指定值开头的每个元素。   |
| [attribute$=value] | 匹配属性值以指定值结尾的每个元素。   |
| [attribute*=value] | 匹配属性值中包含指定值的每个元素。   |

## 后代选择器

后代选择器就是设置 HTML 页面的指定元素的后代元素（中间使用空格）的 CSS 样式。具体语法如下:

```
祖先元素 后代元素 { 属性名 : 属性值; }
```

示例代码:

```
div em {color : red; }
```

## 子元素选择器

子选择器就是设置 HTML 页面的指定元素的子元素的 CSS 样式。具体语法如下:

```
祖先元素 > 子元素{ 属性名 : 属性值; }
```

示例代码:

```
div > em {color : red; }
```

## 相邻元素选择器

相邻元素选择器就是设置 HTML 页面的指定元素的下一个兄弟元素的 CSS 样式。具体语法如下:

```
指定元素 + 兄弟元素 { 属性名 : 属性值; }
```

示例代码:

```
div + div {color : red; }
```

## 其他内容

### 选择器分组

选择器分组就是将不同选择器相同声明的内容“压缩”在一起，得到更简洁的样式表。

```
/* no grouping */
h1 {color:blue;}
h2 {color:blue;}
h3 {color:blue;}
h4 {color:blue;}
h5 {color:blue;}
h6 {color:blue;}

/* grouping */
h1, h2, h3, h4, h5, h6 {color:blue;}
```

### 通配符选择器

CSS2 引入了一种新的简单选择器 - 通配选择器（universal selector），显示为一个星号（*）。该选择器可以与任何元素匹配，就像是一个通配符。

```
* {color:red;}
```

> **值得注意的是:** 通配符选择器的性能并不好。

 

 CSS 伪类用于向某些选择器添加特殊的效果。

| 属性         | 描述                                     |
| ------------ | ---------------------------------------- |
| :active      | 向被激活的元素添加样式。                 |
| :focus       | 向拥有键盘输入焦点的元素添加样式。       |
| :hover       | 当鼠标悬浮在元素上方时，向元素添加样式。 |
| :link        | 向未被访问的链接添加样式。               |
| :visited     | 向已被访问的链接添加样式。               |
| :first-child | 向元素的第一个子元素添加样式。           |

## 锚伪类

```
a:link {color: #FF0000}		/* 未访问的链接 */
a:visited {color: #00FF00}	/* 已访问的链接 */
a:hover {color: #FF00FF}	/* 鼠标移动到链接上 */
a:active {color: #0000FF}	/* 选定的链接 */
```

## :first-child伪类

```
p:first-child {font-weight: bold;}
```

## 选择器的优先级

在实际开发中，经常会为同一个标签设置多个样式。使用不同方式的选择器，由于其优先级不同，导致最终的效果也会不同。

选择器的优先级，具体如下:

- 内联样式的优先级为 1000
- ID 选择器的优先级为 100
- 类选择器的优先级为 10
- 元素选择器的优先级为 1
- 通配符选择器的优先级为 0
- 继承的样式没有任何优先级

> **值得注意的是:**
>
> - 当一个样式中包含多个选择器时，需要将所有的选择器的优先级进行相加。
> - 优先级高的选择器优先显示，选择器的计算不会超过其最大的数量级。
> - 如果两个选择器的优先级相同，则哪个选择器最后定义才有效。
> - 如果某个选择器使用了 `!important`，则改选择器的优先级最高。

 

 什么是盒子模型

盒子模型，也可以称为框模型。

所有 HTML 元素可以看作盒子。在 CSS 中，"box model" 这一术语是用来设计和布局时使用。

CSS 盒模型本质上是一个盒子，封装周围的 HTML 元素，它包括：边距，边框，填充，和实际内容。

[![img](https://github.com/jyl/front-end-notes/raw/master/css-basics/01.png)](https://github.com/jyl/front-end-notes/blob/master/css-basics/01.png)

不同部分的说明:

- Margin（外边距）: 清除边框区域。Margin没有背景颜色，它是完全透明。
- Border（边框）: 边框周围的填充和内容。边框是受到盒子的背景颜色影响。
- Padding（内边距）: 清除内容周围的区域。会受到框中填充的背景颜色影响。
- Content（内容）: 盒子的内容，显示文本和图像。

为了在所有浏览器中的元素的宽度和高度设置正确的话，你需要知道的盒模型是如何工作的。

### 元素的宽度和高度

下面的例子中的元素的总宽度为 300px:

```
width:250px;
padding:10px;
border:5px solid gray;
margin:10px;
```

完整的 HTML 代码如下:

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8"> 
	<title></title>
<style>
	div.ex
	{
		width:220px;
		padding:10px;
		border:5px solid gray;
		margin:0px;
	}
</style>
</head>

<body>

	<div class="ex">The picture above is 250px wide.
					The total width of this element is also 250px.</div>

</body>
</html>
```

上述示例运行的结果如下:

[![img](https://github.com/jyl/front-end-notes/raw/master/css-basics/02.png)](https://github.com/jyl/front-end-notes/blob/master/css-basics/02.png)

> **值得注意的是:** 当指定一个 CSS 元素的宽度和高度属性时，只是设置内容区域的宽度和高度。要知道，完全大小的元素，还必须添加填充，边框和边距。

## 边框

CSS 边框属性允许指定一个元素边框的样式和颜色。

CSS 边框属性常见如下:

- border-width: 设置边框的宽度
- border-color: 设置边框的颜色
- border-style: 边框的样式

### 设置边框的宽度

如果设置一个值，则同时设置边框的四个方向的宽度。如下代码:

```
border-width: 10px;
```

上述代码则表示同时四个方向的边框宽度为 10px。

如果设置两个值，则第一个值表示设置边框的上下方向宽度，第二个值表示设置边框的左右方向宽度。

```
border-width: 10px 20px;
```

如果设置三个值，则第一个值表示设置边框的上边宽度，第二个值表示设置边框的左右方向宽度，第三个值表示设置边框的下边宽度。

```
border-width: 10px 20px 30px;
```

如果设置四个值，则分别表示设置上、右、下和左四个方向的边框宽度。

```
border-width: 10px 20px 30px 40px;
```

除了上述方式设置边框宽度，CSS 还提供如下方式分别设置上、右、下和左边框的宽度。

| 属性名称            | 描述                           |
| ------------------- | ------------------------------ |
| border-top-width    | 设置一个元素的顶部边框的宽度。 |
| border-right-width  | 设置一个元素的右边框的宽度。   |
| border-bottom-width | 设置一个元素的底部边框的宽度。 |
| border-left-width   | 设置一个元素的左边框的宽度。   |

### 设置边框的颜色

如果设置一个值，则同时设置边框的四个方向的颜色。如下代码:

```
border-color: red;
```

上述代码则表示同时四个方向的边框颜色为 red。

如果设置两个值，则第一个值表示设置边框的上下方向颜色，第二个值表示设置边框的左右方向颜色。

```
border-color: red orange;
```

如果设置三个值，则第一个值表示设置边框的上边颜色，第二个值表示设置边框的左右方向颜色，第三个值表示设置边框的下边颜色。

```
border-color: red orange yellow;
```

如果设置四个值，则分别表示设置上、右、下和左四个方向的边框颜色。

```
border-color: red orange yellow blue;
```

除了上述方式设置边框颜色，CSS 还提供如下方式分别设置上、右、下和左边框的颜色。

| 属性名称            | 描述                           |
| ------------------- | ------------------------------ |
| border-top-color    | 设置一个元素的顶部边框的颜色。 |
| border-right-color  | 设置一个元素的右边框的颜色。   |
| border-bottom-color | 设置一个元素的底部边框的颜色。 |
| border-left-color   | 设置一个元素的左边框的颜色。   |

### 设置边框的样式

边框样式的常用备选想如下:

| 边框样式 | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| none     | 定义无边框。                                                 |
| hidden   | 与 "none" 相同。不过应用于表时除外，对于表，hidden 用于解决边框冲突。 |
| dotted   | 定义点状边框。在大多数浏览器中呈现为实线。                   |
| dashed   | 定义虚线。在大多数浏览器中呈现为实线。                       |
| solid    | 定义实线。                                                   |
| double   | 定义双线。双线的宽度等于 border-width 的值。                 |
| inherit  | 规定应该从父元素继承边框样式。                               |

如果设置一个值，则同时设置边框的四个方向的样式。如下代码:

```
border-style: dotted;
```

如果设置两个值，则第一个值表示设置边框的上下方向样式，第二个值表示设置边框的左右方向样式。

```
border-style: dotted solid;
```

如果设置三个值，则第一个值表示设置边框的上边样式，第二个值表示设置边框的左右方向样式，第三个值表示设置边框的下边样式。

```
border-style: dotted solid dashed;
```

如果设置四个值，则分别表示设置上、右、下和左四个方向的边框样式。

```
border-style: dotted solid dashed double;
```

除了上述方式设置边框样式，CSS 还提供如下方式分别设置上、右、下和左边框的样式。

| 属性名称            | 描述                           |
| ------------------- | ------------------------------ |
| border-top-style    | 设置一个元素的顶部边框的样式。 |
| border-right-style  | 设置一个元素的右边框的样式。   |
| border-bottom-style | 设置一个元素的底部边框的样式。 |
| border-left-style   | 设置一个元素的左边框的样式。   |

### 简写设置边框

CSS 提供了 `border` 属性允许同时设置边框的宽度、颜色和样式。

```
border: 5px solid red;
```

> **值得注意的是:** 设置的顺序没有明确要求。

除了上述方式设置边框，CSS 还提供如下方式分别设置上、右、下和左边框。

| 属性名称      | 描述                     |
| ------------- | ------------------------ |
| border-top    | 设置一个元素的顶部边框。 |
| border-right  | 设置一个元素的右边框。   |
| border-bottom | 设置一个元素的底部边框。 |
| border-left   | 设置一个元素的左边框。   |

## 内边距

CSS Padding（内边距）属性定义元素边框与元素内容之间的距离。

如果设置一个值，则同时设置内边距的四个方向。如下代码:

```
padding: 25px;
```

如果设置两个值，则第一个值表示设置内边距的上下方向，第二个值表示设置内边距的左右方向。

```
padding: 25px 50px;
```

如果设置三个值，则第一个值表示设置内边距的上边，第二个值表示设置内边距的左右方向，第三个值表示设置内边距的下边。

```
padding: 25px 50px 75px;
```

如果设置四个值，则分别表示设置上、右、下和左四个方向的内边距。

```
padding: 25px 50px 75px 100px;
```

除了上述方式设置内边距，CSS 还提供如下方式分别设置上、右、下和左边的内边距。

| 属性名称       | 描述                       |
| -------------- | -------------------------- |
| padding-top    | 设置一个元素的顶部内边距。 |
| padding-right  | 设置一个元素的右边内边距。 |
| padding-bottom | 设置一个元素的底部内边距。 |
| padding-left   | 设置一个元素的左边内边距。 |

## 外边距

CSS Margin（外边距）属性定义元素周围的距离。

外边距不会影响元素的可见大小，但是会影响元素的位置。

| 属性名称      | 描述                 |
| ------------- | -------------------- |
| margin-top    | 设置元素的上外边距。 |
| margin-right  | 设置元素的右外边距。 |
| margin-left   | 设置元素的左外边距。 |
| margin-bottom | 设置元素的下外边距。 |

### 设置上和左外边距

```
margin-top: 100px;
margin-left: 50px;
```

由于元素在 HTML 页面中默认是靠左靠上显示的。所以默认情况下，修改左外边距和上外边距时，会影响当前元素的位置。

### 设置下和右外边距

```
margin-bottom: 100px;
margin-right: 50px;
```

修改右和下外边距时会影响其他元素相对于当前元素的位置。

### 简写设置外边距

如果设置一个值，则同时设置外边距的四个方向。如下代码:

```
margin: 25px;
```

如果设置两个值，则第一个值表示设置外边距的上下方向，第二个值表示设置外边距的左右方向。

```
margin: 25px 50px;
```

如果设置三个值，则第一个值表示设置外边距的上边，第二个值表示设置外边距的左右方向，第三个值表示设置外边距的下边。

```
margin: 25px 50px 75px;
```

如果设置四个值，则分别表示设置上、右、下和左四个方向的外边距。

```
margin: 25px 50px 75px 100px;
```

### 外边距重叠

当同时为两个相邻的 `<div>` 标签设置外边距，为第一个 `<div>` 标签设置下外边距，为第二个 `<div>` 标签设置上外边距。具体代码如下:

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style type="text/css">
			.box1{
				width: 100px;
				height: 100px;
				background-color: red;
				/*为上边的元素设置一个下外边距*/
				margin-bottom: 100px;
			}		
			.box2{
				width: 100px;
				height: 100px;
				background-color: blue;
				/*为下边的元素设置一个上外边距*/
				margin-top: 100px;
			}
		</style>
	</head>
	<body>
		<div class="box1"></div>
		<div class="box2"></div>	
	</body>
</html>
```

上述示例代码，最终运行的结果是: 两个 `<div>` 之间的距离为 100px。

垂直方向的相邻的外边距会发生外边距的重叠现象，兄弟元素的相邻外边距会取最大值。

> **值得注意的是:** 外边距的重叠现象只会出现在垂直方向，而水平方向并不存在外边距重叠现象。

如果定义两个 `<div>` 标签是父子关系的话，当为作为子元素的 `<div>` 设置上外边距，该上外边距会传递给作为父元素的 `<div>`。具体代码如下:

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>		
		<style type="text/css">		
			.box3{
				width: 300px;
				height: 200px;
				background-color: skyblue;
			}
			
			.box4{
				width: 100px;
				height: 100px;
				background-color: red;
				/*设置一个margin-top*/
				margin-top: 100px;
			}			
		</style>
	</head>
	<body>		
		<div class="box3">
			<div class="box4"></div>
		</div>
	</body>
</html>
```

上述外边距的重叠现象，可以通过为作为父元素的 `<div>` 下内边距解决。

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>		
		<style type="text/css">		
			.box3{
				width: 300px;
				height: 100px;
				background-color: skyblue;
				padding-top: 100px;
			}
			
			.box4{
				width: 100px;
				height: 100px;
				background-color: red;
			}			
		</style>
	</head>
	<body>		
		<div class="box3">
			<div class="box4"></div>
		</div>
	</body>
</html>
```

## 内联元素的盒子模型

### 内联元素的宽度和高度

内联元素不支持设置宽和高，内联元素元素的大小由内容决定。

### 内联元素的内边距

- 内联元素支持水平方向的内边距。
- 内联元素可以设置垂直方向的内边距，但是不会影响布局。

### 内联元素的边框

- 内联元素支持水平方向的边框。
- 内联元素可以设置垂直方向的边框，但是不会影响布局。

### 内联元素的外边距

内联元素支持水平方向的外边距 , 不支持垂直方向的外边距。

 

 CSS 中的 display 和 visibility 都可以设置一个元素在浏览器中的显示或隐藏效果。

- display: 隐藏某个元素时，不会占用任何空间。换句话讲，不会影响布局。
- visibility: 隐藏某个元素时，仍需占用与未隐藏之前一样的空间。换句话讲，会影响布局。

## display 属性

| 属性值 | 描述               |
| ------ | ------------------ |
| none   | 此元素不会被显示。 |

当将一个元素的 CSS 属性 display 设置为 none 时，该元素会被隐藏。并且被隐藏的元素不会占用 HTML 页面的任何空间。

在 HTML 页面中定义两个 `<div>` 标签，并设置 CSS 样式，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #d1 {
        width: 300px;
        height: 300px;
        background-color: lightskyblue;
      }
      #d2 {
        width: 300px;
        height: 300px;
        background-color: green;
      }
    </style>
  </head>
  <body>
    <div id="d1"></div>
    <div id="d2"></div>
  </body>
</html>
```

当为第一个 `<div>` 标签设置 display 属性值为 none 时，该 `<div>` 标签会被隐藏。

| 属性值 | 描述                     |
| ------ | ------------------------ |
| block  | 此元素将显示为块级元素。 |

该值主要作用于**内联元素**。如果将内联元素的 CSS 属性 display 设置为 block 时，该内联元素将在浏览器中显示成块级元素效果。

在 HTML 页面中定义两个 `<div>` 标签，并设置 CSS 样式，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #s1 {
        width: 300px;
        height: 300px;
        background-color: lightskyblue;
      }
      #s2 {
        width: 300px;
        height: 300px;
        background-color: green;
      }
    </style>
  </head>
  <body>
    <span id="s1">这是一个span</span>
    <span id="s2">这是一个span</span>
  </body>
</html>
```

当为第一个 `<span>` 标签设置 display 属性值为 block 时，该 `<span>` 标签会呈现块级元素效果。

| 属性值 | 描述                               |
| ------ | ---------------------------------- |
| inline | 默认值，此元素会被显示为内联元素。 |

该值主要作用于**块级元素**。如果将内联元素的 CSS 属性 display 设置为 inline 时，该内联元素将在浏览器中显示成内联元素效果。

在 HTML 页面中定义两个 `<div>` 标签，并设置 CSS 样式，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #d1 {
        width: 300px;
        height: 300px;
        background-color: lightskyblue;
      }
      #d2 {
        width: 300px;
        height: 300px;
        background-color: green;
      }
    </style>
  </head>
  <body>
    <div id="d1">这是一个div</div>
    <div id="d2">这是一个div</div>
  </body>
</html>
```

当为第一个 `<div>` 标签设置 display 属性值为 inline 时，该 `<div>` 标签会呈现内联元素样式。

| 属性值       | 描述         |
| ------------ | ------------ |
| inline-block | 行内块元素。 |

当将 CSS 属性 display 设置为 inline-block 时，该元素在浏览器中显示为内联块级效果。即每个元素呈现块级元素效果，元素之间呈现内联元素效果。

在 HTML 页面中定义两个 `<div>` 标签，并设置 CSS 样式，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #d1 {
        width: 300px;
        height: 300px;
        background-color: lightskyblue;
      }
      #d2 {
        width: 300px;
        height: 300px;
        background-color: green;
      }
    </style>
  </head>
  <body>
    <div id="d1">这是一个div</div>
    <div id="d2">这是一个div</div>
  </body>
</html>
```

分别为两个 `<div>` 标签设置 display 属性值为 inline-block 时，这两个 `<div>` 会显示在一行中。

### visibility 属性

visibility 属性指定一个元素是否是可见的。

> **值得注意的是:** visibility 属性设置元素不可见的元素，但会占据页面上的空间。请使用 display 属性来创建不占据页面空间的不可见元素。

| 属性值  | 描述                   |
| ------- | ---------------------- |
| visible | 默认值，元素是可见的。 |
| hidden  | 元素是不可见的。       |

在 HTML 页面中定义两个 `<div>` 标签，并设置 CSS 样式，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #d1 {
        width: 300px;
        height: 300px;
        background-color: lightskyblue;
      }
      #d2 {
        width: 300px;
        height: 300px;
        background-color: green;
      }
    </style>
  </head>
  <body>
    <div id="d1">这是一个div</div>
    <div id="d2">这是一个div</div>
  </body>
</html>
```

当为第一个 `<div>` 标签设置 visibility 属性值为 hidden 时，该 `<div>` 会被隐藏。



overflow 属性用于设置当元素中的内容溢出后的情况。

> **值得注意的是:** 所谓溢出，是指子元素的大小（包括文本、元素或图片等）超出父元素的区域，会有一部分内容显示在父元素所在的区域外。

| 属性值  | 描述                                         |
| ------- | -------------------------------------------- |
| visible | 默认值。内容不会被修剪，会呈现在元素框之外。 |
| hidden  | 内容会被修剪，并且其余内容是不可见的。       |

上述两个值，要么设置溢出的内容默认显示在父元素的区域之外，要么设置溢出的内容隐藏不可见。这两种结果都是很好的效果。所以，在实际开发中，很少使用这两个值。

在 HTML 页面中定义一个 `<div>` 标签，设置 CSS 样式，并设置较多的文本内容，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      div {
        width: 300px;
        height: 300px;
        background-color: lightskyblue;
      }
    </style>
  </head>
  <body>
    <div>
      在我的后园，可以看见墙外有两株树，一株是枣树，还有一株也是枣树。
这上面的夜的天空，奇怪而高，我生平没有见过这样奇怪而高的天空。他仿佛要离开人间而去，使人们仰面不再看见。然而现在却非常之蓝，闪闪地䀹着几十个星星的眼，冷眼。他的口角上现出微笑，似乎自以为大有深意，而将繁霜洒在我的园里的野花草上。
我不知道那些花草真叫什么名字，人们叫他们什么名字。我记得有一种开过极细小的粉红花，现在还开着，但是更极细小了，她在冷的夜气中，瑟缩地做梦，梦见春的到来，梦见秋的到来，梦见瘦的诗人将眼泪擦在她最末的花瓣上，告诉她秋虽然来，冬虽然来，而此后接着还是春，蝴蝶乱飞，蜜蜂都唱起春词来了。她于是一笑，虽然颜色冻得红惨惨地，仍然瑟缩着。
枣树，他们简直落尽了叶子。先前，还有一两个孩子来打他们，别人打剩的枣子，现在是一个也不剩了，连叶子也落尽了。他知道小粉红花的梦，秋后要有春；他也知道落叶的梦，春后还是秋。他简直落尽叶子，单剩干子，然而脱了当初满树是果实和叶子时候的弧形，欠伸得很舒服。但是，有几枝还低亚着，护定他从打枣的竿梢所得的皮伤，而最直最长的几枝，却已默默地铁似的直刺着奇怪而高的天空，使天空闪闪地鬼䀹眼；直刺着天空中圆满的月亮，使月亮窘得发白。
鬼䀹眼的天空越加非常之蓝，不安了，仿佛想离去人间，避开枣树，只将月亮剩下。然而月亮也暗暗地躲到东边去了。而一无所有的干子，却仍然默默地铁似的直刺着奇怪而高的天空，一意要制他的死命，不管他各式各样地䀹着许多蛊惑的眼睛。
哇的一声，夜游的恶鸟飞过了。
我忽而听到夜半的笑声，吃吃地，似乎不愿意惊动睡着的人，然而四围的空气都应和着笑。夜半，没有别的人，我即刻听出这声音就在我嘴里，我也即刻被这笑声所驱逐，回进自己的房。灯火的带子也即刻被我旋高了。
后窗的玻璃上丁丁地响，还有许多小飞虫乱撞。不多久，几个进来了，许是从窗纸的破孔进来的。他们一进来，又在玻璃的灯罩上撞得丁丁地响。一个从上面撞进去了，他于是遇到火，而且我以为这火是真的。两三个却休息在灯的纸罩上喘气。那罩是昨晚新换的罩，雪白的纸，折出波浪纹的叠痕，一角还画出一枝猩红色的栀子。
猩红的栀子开花时，枣树又要做小粉红花的梦，青葱地弯成弧形了……我又听到夜半的笑声；我赶紧砍断我的心绪，看那老在白纸罩上的小青虫，头大尾小，向日葵子似的，只有半粒小麦那么大，遍身的颜色苍翠得可爱，可怜。
我打一个呵欠，点起一支纸烟，喷出烟来，对着灯默默地敬奠这些苍翠精致的英雄们。
一九二四年九月十五日。
    </div>
  </body>
</html>
```

当为第一个 `<div>` 标签设置 overflow 属性值为 hidden 时，该 `<div>` 中的溢出文本内容会被隐藏。

| 属性值 | 描述                                                     |
| ------ | -------------------------------------------------------- |
| scroll | 内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。 |
| auto   | 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。 |

在 HTML 页面中定义一个 `<div>` 标签，设置 CSS 样式，并设置较多的文本内容，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      div {
        width: 300px;
        height: 300px;
        background-color: lightskyblue;
      }
    </style>
  </head>
  <body>
    <div>
      在我的后园，可以看见墙外有两株树，一株是枣树，还有一株也是枣树。
这上面的夜的天空，奇怪而高，我生平没有见过这样奇怪而高的天空。他仿佛要离开人间而去，使人们仰面不再看见。然而现在却非常之蓝，闪闪地䀹着几十个星星的眼，冷眼。他的口角上现出微笑，似乎自以为大有深意，而将繁霜洒在我的园里的野花草上。
我不知道那些花草真叫什么名字，人们叫他们什么名字。我记得有一种开过极细小的粉红花，现在还开着，但是更极细小了，她在冷的夜气中，瑟缩地做梦，梦见春的到来，梦见秋的到来，梦见瘦的诗人将眼泪擦在她最末的花瓣上，告诉她秋虽然来，冬虽然来，而此后接着还是春，蝴蝶乱飞，蜜蜂都唱起春词来了。她于是一笑，虽然颜色冻得红惨惨地，仍然瑟缩着。
枣树，他们简直落尽了叶子。先前，还有一两个孩子来打他们，别人打剩的枣子，现在是一个也不剩了，连叶子也落尽了。他知道小粉红花的梦，秋后要有春；他也知道落叶的梦，春后还是秋。他简直落尽叶子，单剩干子，然而脱了当初满树是果实和叶子时候的弧形，欠伸得很舒服。但是，有几枝还低亚着，护定他从打枣的竿梢所得的皮伤，而最直最长的几枝，却已默默地铁似的直刺着奇怪而高的天空，使天空闪闪地鬼䀹眼；直刺着天空中圆满的月亮，使月亮窘得发白。
鬼䀹眼的天空越加非常之蓝，不安了，仿佛想离去人间，避开枣树，只将月亮剩下。然而月亮也暗暗地躲到东边去了。而一无所有的干子，却仍然默默地铁似的直刺着奇怪而高的天空，一意要制他的死命，不管他各式各样地䀹着许多蛊惑的眼睛。
哇的一声，夜游的恶鸟飞过了。
我忽而听到夜半的笑声，吃吃地，似乎不愿意惊动睡着的人，然而四围的空气都应和着笑。夜半，没有别的人，我即刻听出这声音就在我嘴里，我也即刻被这笑声所驱逐，回进自己的房。灯火的带子也即刻被我旋高了。
后窗的玻璃上丁丁地响，还有许多小飞虫乱撞。不多久，几个进来了，许是从窗纸的破孔进来的。他们一进来，又在玻璃的灯罩上撞得丁丁地响。一个从上面撞进去了，他于是遇到火，而且我以为这火是真的。两三个却休息在灯的纸罩上喘气。那罩是昨晚新换的罩，雪白的纸，折出波浪纹的叠痕，一角还画出一枝猩红色的栀子。
猩红的栀子开花时，枣树又要做小粉红花的梦，青葱地弯成弧形了……我又听到夜半的笑声；我赶紧砍断我的心绪，看那老在白纸罩上的小青虫，头大尾小，向日葵子似的，只有半粒小麦那么大，遍身的颜色苍翠得可爱，可怜。
我打一个呵欠，点起一支纸烟，喷出烟来，对着灯默默地敬奠这些苍翠精致的英雄们。
一九二四年九月十五日。
    </div>
  </body>
</html>
```

当为第一个 `<div>` 标签设置 overflow 属性值为 scroll 时，该 `<div>` 中的溢出文本内容会显示滚动条。

上述两个值，当有溢出的内容出现时，都会显示滚动条以便查看其余的内容。但不同是:

- scroll: 无论是否有溢出的内容，始终显示滚动条。
- auto: 当有溢出的内容出现时，才显示滚动条。如果没有溢出的内容时，会自动隐藏滚动条。



CSS 的 position 定位属性允许自定义元素在 HTML 页面的位置，但需要先开启元素在 HTML 页面中的定位。

> **值得注意的是:** 元素在 HTML 页面中默认是不开启定位的。

CSS 定位属性提供了四种方式的定位效果:

- static: 默认值，表示元素为静态定位。
- absolute: 表示元素为绝对定位。
- fixed: 表示元素为固定定位。
- relative: 表示元素为相对定位。

当设置元素的 position 定位属性为**非默认值**时，CSS 提供了上、右、下和左四个方向的偏移量完成元素的位置设置。

- top: 表示当前元素到上边的距离。
- right: 表示当前元素到右边的距离。
- bottom: 表示当前元素到下边的距离。
- left: 表示当前元素到左边的距离。

[![img](https://github.com/jyl/front-end-notes/raw/master/css-basics/03.png)](https://github.com/jyl/front-end-notes/blob/master/css-basics/03.png)

## 绝对定位

| 属性值   | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| absolute | 生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。 |

> 元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。

元素开启绝对定位后，与浮动效果类似:

- 元素会脱离文档流。
- 元素会呈现块级元素效果。
- 如果不设置偏移量，元素的位置不会发生变化。

### 如果元素的父元素是 `<body>` 的话，绝对定位会相对于当前页面

在 HTML 页面中定义两个 `<div>` 标签，并且为相邻的兄弟元素，并设置其 CSS 样式，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #d1 {
        width: 300px;
        height: 300px;
        background-color: lightskyblue;

      }
      #d2 {
        width: 300px;
        height: 300px;
        background-color: green;
      }
    </style>
  </head>
  <body>
    <div id="d1"></div>
    <div id="d2"></div>
  </body>
</html>
```

为第二个 `<div>` 元素开启绝对定位，并设置偏移量，具体代码如下:

```
position: absolute;
left: 0px;
top: 0px;
```

> **值得注意的是:** 如果开启绝对定位的元素的父元素并不是 `<body>` 标签，但父元素没有开启任何定位的话，开启绝对定位的元素还是相对于当前页面。

### 如果元素的父元素不是 `<body>` 标签，并且开启定位的话，绝对定位会相对于父元素

在 HTML 页面中定义两个 `<div>` 标签，并且为父元素与子元素的关系，并设置其 CSS 样式，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #d1 {
        width: 500px;
        height: 400px;
        background-color: lightskyblue;
      }
      #d2 {
        width: 300px;
        height: 300px;
        background-color: green;
      }
    </style>
  </head>
  <body>
    <div id="d1">
      <div id="d2"></div>
    </div>
  </body>
</html>
```

为两个 `<div>` 元素开启绝对定位，并设置偏移量，具体代码如下:

```
#d1 {
  width: 500px;
  height: 400px;
  background-color: lightskyblue;
  
  position: absolute;
  left: 100px;
  top: 0px;
}
#d2 {
  width: 300px;
  height: 300px;
  background-color: green;
  
  position: absolute;
  left: 100px;
  top: 0px;
}
```

## 固定定位

| 属性值 | 描述                                           |
| ------ | ---------------------------------------------- |
| fixed  | 生成绝对定位的元素，相对于浏览器窗口进行定位。 |

> 元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。

固定定位是一种特殊的绝对定位，固定定位与绝对定位的区别在于:

- 固定定位始终相对于当前页面进行定位。
- 绝对定位相对于最近的祖先元素进行定位。

例如上述效果就是固定定位的一种应用方式。实现上述效果的具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      body {
        margin: 0px;
        height: 2000px;
      }
      #d1 {
        width: 100%;
        height: 100px;
        background-color: lightskyblue;
        position: fixed;
        bottom: 0px;
      }
    </style>
  </head>
  <body>
    <div id="d1"></div>
  </body>
</html>
```

## 相对定位

| 属性值   | 描述                                           |
| -------- | ---------------------------------------------- |
| relative | 生成相对定位的元素，相对于其正常位置进行定位。 |

> **值得注意的是:**
>
> - 开启相对定位的元素，不会脱离文档流。
> - 开启相对定位的元素，是相对于该元素在文档流中的定位效果。
> - 开启相对定位的元素，不会改变元素的性质。（块级元素呈现块级元素效果，内联元素呈现内联元素效果）

在 HTML 页面中定义两个 `<div>` 标签，并且为相邻的兄弟元素，并设置其 CSS 样式，具体代码如下:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      #d1 {
        width: 500px;
        height: 400px;
        background-color: lightskyblue;
      }
      #d2 {
        width: 300px;
        height: 300px;
        background-color: green;
      }
    </style>
  </head>
  <body>
    <div id="d1"></div>
    <div id="d2"></div>
  </body>
</html>
```

为第二个 `<div>` 元素开启相对定位，并设置偏移量，具体代码如下:

```
position: absolute;
left: 0px;
top: 0px;
```


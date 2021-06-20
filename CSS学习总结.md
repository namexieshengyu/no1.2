# CSS学习总结

## CSS简介与特征

**简介：**

​	CSS是级联样式表（Cascading Style Sheets）的缩写。HTML 用于撰写页面的内容，而 CSS 将决定这些内容该如何在屏幕上呈现。网页的内容是由 HTML的元素构建的，这些元素如何呈现，涉及许多方面，如整个页面的布局，元素的位置、距离、颜色、大小、是否显示、是否浮动、透明度等等。

**特征**

- 层叠性：最近的CSS
- 继承性：子标签继承父标签的css样式
- 优先级

## CSS生效的方法

### 外部样式表

语法：

<head>
  <link href="CSS文件的路径" type="text/CSS" rel="stylesheet" />
</head>
该语法中，link标签需要放在head头部标签中，并且必须指定link标签的三个属性，具体如下：

- href：定义所链接外部样式表文件的URL，可以是相对路径，也可以是绝对路径。

- type：定义所链接文档的类型，在这里需要指定为“text/CSS”，表示链接的外部文件为CSS样式表。
- rel：定义当前文档与被链接文档之间的关系，在这里需要指定为“stylesheet”，表示被链接的文档是一个样式表文件。

### 内部样式表

将CSS代码集中写在HTML文档的head头部标签中，并且用style标签定义，其基本语法格式如下：
<head>
   <style type="text/css">
		input{border:blue solid 1px;background-color: brown}
		a{border:blue solid 1px;background-color: brown}
   </style>
</head>

### 内联样式

- 通过标签的style属性来设置元素的样式，其基本语法格式如下：

```html
<h1 style="color:red;">style属性的应用</h1>
<p  style="font-size:14px;color:green;">直接在HTML标签中设置的样式</p>
```

## CSS选择器

### 1.基本选择器

#### 1.1标签选择器

每个html页面都由很多个标签组成，通过标签选择器可以对某类标签应用相应的样式，如对p标签应用下面的样式，则页面中所有的p标签都会生效。 
`p{ font-size:12px; color:red; background:blue; }` 

#### 1.2类选择器

类选择器是css非常常用的选择器，在html中可以为某个标签增加class属性。类选择器可以复用，如对页面中的p标签也可以应用此样式 。除此以外，一个标签可以有多个类选择器，不同的值用空格隔开，这样多个样式便可以应用的一个标签上。 

#### 1.3 id选择器

id选择器和类选择器一样，用的也很频繁，但是id在每个html页面的值必须是唯一的，所以它不可以复用。

#### 1.4 通用选择器

不同于上面的三种选择器，通用选择器要强大的多，它可以对页面中的所有html标签应用样式，当然也正是因为如此强大，反而限制了它的灵活性，在实际应用中用的较少。

### 2.组合选择器

#### 2.1 子选择器

也称为直接后代选择器，以`>`作为分隔，如：`.haha > p` 代表在有`.haha`类的元素内的直接`<p>`元素。

#### 2.2 后代选择器

以空格作为分隔，如：`.haha p` 代表在`div`元素内有`.haha`这种类的所有元素。

## CSS语法

CSS 规则由两个主要的部分构成：选择器，以及一条或多条声明。

## CSS背景属性

background-attachment	设置背景图像是否固定或者随着页面的其余部分滚动
background-color	设置元素的背景颜色
background-image	设置元素的背景图像
background-position	设置背景图像的开始位置
background-repeat	设置是否及如何重复背景图像
background-clip	规定背景的绘制区域
background-origin	规定背景图片的定位区域
background-size	规定背景图片的尺寸

### 背景色半透明

```cs
background-color: rgba(0, 0, 0, 0.5);  //最后一个代表透明度50%
```

## 盒子模型

在使用CSS进行网页布局时，我们一定离不开的一个东西——盒子模型。盒子模型，顾名思义，盒子就是用来装东西的，它装的东西就是HTML元素的内容。或者说，每一个可见的 HTML 元素都是一个盒子，下面所说的盒子都等同于 HTML 元素。

### 盒子的组成

一个盒子由外到内可以分成四个部分：margin（外边距）、border（边框）、padding（内边距）、content（内容）。会发现margin、border、padding是CSS属性，因此可以通过这三个属性来控制盒子的这三个部分。而content则是HTML元素的内容。

### 盒子的大小

盒子的大小指的是盒子的宽度和高度。大多数初学者容易将宽度和高度误解为width和height属性，然而默认情况下width和height属性只是设置content（内容）部分的宽和高。盒子真正的宽和高按下面公式计算：

- 盒子的宽度 = width + padding-left + padding-right + border-left + border-right + margin-left + margin-right


- 盒子的高度 = height + padding-top + padding-bottom + border-top + border-bottom + margin-top + margin-bottom
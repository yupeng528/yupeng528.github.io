# Day03—CSS样式表和基本选择器的使用

# 一、CSS的概念

​	大家都知道我们前两章的课程中，我们在写标签时候，在浏览器中显示的效果跟我们需要的效果有很大差距，比如我们要改变一下文字的颜色，改变一下背景颜色，改变一下字体等，那应该办呢？

​	我们天天说HTML是结构，CSS是表现，应该怎么解释这两个概念呢？

​	HTML是结构，也就是如是需要写一个网页了，得先看看要生成这个网页需要那些标签，也就是搭建一下页面结构，结构是搭好了，就是我们买了房子一样，房子就是结构，如果房子搭建好了，如果不装修，觉得还是不美观，那应该怎么办呢？

​	那就得用CSS来修饰一下我们HTML标签，所以CSS的主要作用就是修饰HTML标签的。那我们一起来了解一下什么是CSS吧！

​	***CSS：层叠样式表(Cascading StyleSheet)*** 

# 二、CSS的作用

​	用于控制网页的外观，修饰和美化html标签的,实现了结构和形式的分离。 另外大家注意我们采用的是DIV+CSS布局页面，那相对以前传统的TABLE网页布局页面有什么优势呢？有以下三点：

​	1：表现和内容相分离 

​	2：提高页面浏览速度 

​	3：易于维护和改版 

      

# 三、CSS的发展简史

| 时间        | 简介                                       |
| --------- | ---------------------------------------- |
| 1996年12月  | CSS第一版诞生，主要定义了网页的基本属性如：字体、颜色、补白、基本选择器等。  |
| 1998年5月   | CSS2正式发布 ，在CSS1的基础上添加了高级功能，如：浮动和定位、高级选择器（子选择器、相邻选择器、通用选择） |
| 2004年     | CSS2.1发布                                 |
| CSS3的发布…… | 不是一个时间而是一个时间段                            |

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/83085464-file_1488014294243_126dc.png)

​	![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/46728782-file_1488014326515_6255.png)

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/96262488-file_1488014367614_118e5.png)

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/57611850-file_1488014397249_16cc6.png)

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/94162622-file_1488014424037_6413.png)

# 四、CSS样式的定义方法

CSS样式定义在样式表中 ,然后再定义样式：

​	`选择器{样式1：样式值1；样式2：样式值2；……}`

写到这里大家应该猜到我们接下来要讲什么了吧，猜对了，就是要讲CSS样式表了！我们一起来看吧

# 五、CSS样式表

> **一共有4种CSS样式表**

## 5.1	行内样式表

> 在HTML标记内，使用style属性定义CSS样式。
>
>   语法：`<p style=”color:red;”></p>`
>
>   style=” ”   这句话就是行内样式表，双引号里面写的就CSS样式（或者叫CSS属性）及样式值（CSS属性值），这里的color是CSS属性，red是CSS属性值。这种样式表用的比较少，因为没有实现结构与表现的分离。

```css
<h3 style="color:red;">行内样式表实现我变了颜色！</h3>
<p style="color:red;">行内样式表实现我变了颜色！</p>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/71099688-file_1488014675080_1247.png)

## 5.2	内嵌样式表

> 就是将CSS添加到<head>与</head>之间，并用<style></style>标记声明的一种样式表。这种样式表用的比较少，因为没有实现结构与表现的分离。
>
> 语法：
>
> `<style>`
>
> 　　                     /*这里写css内容*/
>
> `</style>`

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS样式表</title>
		<style type="text/css">
			h3{
				color:red;/*这里color是CSS属性，red是CSS属性值*/
			}
			p{
				color:red;
			}
		</style>
	</head>
	<body>
		<h3>内部样式表实现我变了颜色！</h3>
		<p>内部样式表实现我变了颜色！</p>
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/94895710-file_1488014804685_ebf7.png)

## 5.3	外部链接样式表

> 在外部定义CSS样式表，通过<link/>链接标记链接到页面中的一种样式表。经常使用，这种样式表非常常用，不仅实现了结构与表现的分离，而且易于维护和改版。
>
> 语法：
>
>  `<link href="style.css" rel="stylesheet" type="text/css" /> `

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS样式表</title>
		<link rel="stylesheet" type="text/css" href="css/style.css"/>
	</head>
	<body>
		<h3>外部链接式样式表实现我变了颜色！</h3>
		<p>外部链接式样式表实现我变了颜色！</p>
	</body>
</html>
```

> **style.css文件的内容：**

```css
h3 {
	color: red;/*这里color是CSS属性，red是CSS属性值*/
}

p {
	color: red;
}
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/74123499-file_1488014943712_125af.png)

## 5.4	外部导入样式表

> 在外部定义css样式表，通过导入方式链接到页面中的一种样式表，使用不多，因为语法不如链接式样式表简单。
>
> 语法： 
>
> `<style>`
>
> 　　        @import url(CSS路径);
>
> ` </style>`

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS样式表</title>
		<style>
			@import url("css/style.css");
		</style>
	</head>
	<body>
		<h3>外部导入式样式表实现我变了颜色！</h3>
		<p>外部导入式样式表实现我变了颜色！</p>
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/41304624-file_1488015107275_11490.png)



## 5.5	各种样式表的优先级

> 如果多个样式表中都对同一个元素使用同一个属性，那么到底谁的优先级高呢？
>
> ***当然是谁离所修饰的HTML标签近，谁就高。（遵循的原则就是就近原则）***

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS样式表</title>
		<style>
			h3{color: blue;}
		</style>
		<link rel="stylesheet" type="text/css" href="css/style.css"/>
	</head>
	<body>
		<h3>内部样式表和外部样式表，谁离我近我识别谁的颜色！</h3>
	</body>
</html>

```

> style.css文件的内容：

```css
h3 {
	color: red;/*这里color是CSS属性，red是CSS属性值*/
}
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/24250815-file_1488015326657_17ebf.png)

# 六、选择器种类

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/31660219-file_1488015438508_e0e1.png)

# 七、基本选择器

|         |        |
| :------ | :----: |
| **选择器** | **功能** |
| *       | 全局选择器  |
| element | 标签选择器  |
| id      | id选择器  |
| class   | 类别选择器  |



## 7.1	全局选择器

> 设置所有标签使用同一样式，用*来表示;
>
> 语法：
>
> `*{ `
>
> ` }`

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS选择器</title>
		<style type="text/css">
			*{
				color: red;/*color是CSS属性，red是CSS属性值*/
			}
		</style>
	</head>
	<body>
		<h3>我是h3标签</h3>
		<p>我是段落标签</p>
		<input type="button" value="提交" />
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/24056845-file_1488015741682_8bac.png)

## 7.2	标签选择器

> 设置相同的标签使用相同的样式。直接写标签的名字+大括号就可以了，但是标签名不区分大小写，但是尽量使用小写。
>
> 语法：
>
> 标签名{
>
> }

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/321528-file_1488015826163_153c5.png)

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS选择器</title>
		<style type="text/css">
			h3{
				color:green;
			}
			p{
				color:red ;
			}
			input{
				color:blue;
			}
		</style>
	</head>
	<body>
		<h3>我是h3标签</h3>
		<h3>我是h3标签</h3>
		<h3>我是h3标签</h3>
		<p>我是段落标签</p>
		<p>我是段落标签</p>
		<p>我是段落标签</p>
		<input type="button" value="提交" />
		<input type="button" value="提交" />
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/98515487-file_1488015883381_6fb3.png)

## 7.4	id选择器

> ​	我们知道class选择器，在一个同一个页面中可以使用多次，但是如果我想找到页面中唯一的元素怎么办，尤其是我们学习到后面的知识点，比如在js语言中，我们使用id的这种方式比较多。
>
> ​	所以我来看一下id选择器的使用及其特点，id选择器的特点就是**具有唯一性，这意味着同一** id 在同一文档页面中只能出现一次。
>
> ​	那他的使用也是先定义后使用，定义的时候使用特殊符号“#”号+id名的方式定义的，使用id这个关键字进行引用。
>
> ​	注意id名的规范：使用驼峰式命名（idName），或使用下划线式（id_name）命名,不能使用中文，不要以数字开头及区分大小写的规范好了，我们来看一下他的语法。

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/3274783-file_1488016303007_7a07.png)

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS选择器</title>
		<style type="text/css">
			#myColor{
				color:red;
			}
		</style>
	</head>
	<body>
		<h3>我是h3标签</h3>
		<h3>我是h3标签</h3>
		<h3 id="myColor">我是h3标签</h3>
		<p>我是段落标签</p>
		<p>我是段落标签</p>
		<p>我是段落标签</p>
		<input type="button" value="提交" />
		<input type="button" value="提交" />
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/83539174-file_1488016367166_9a37.png)



## 7.5	类选择器

> 大家都知道我们全局选择器是让页面中所有的标签具有相同的样式，标签选择器是让页面中相同的标签具有了相同的样式，
>
> **那如果我们让相同的标签具有不同的样式或者不同的标签具有相同的样式怎么办呢**？
>
> 那就是定义我们的类别选择器，**类别选择器的特点是先声明，后使用，一次定义多次使用，使用特殊符号 `*.类名` 的方式定义，**
>
> **用class这个关键字在标签中引用，注意类名的规范：使用驼峰式命名（className），或使用下划线式（class_name）命名,不能使用中文，不要以数字开头及区分大小写的规范**，

> 语法：
>
>  ` .className{}     `
>
> `<h3 class=”className”>内容一</h3>`
>
> `<h3 class=”className”>内容二</h3>`
>
> `<p class=”className”>内容三</p>`

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS选择器</title>
		<style type="text/css">
			.myColor{
				color:red;
			}
		</style>
	</head>
	<body>
		<h3>我是h3标签</h3>
		<h3 class="myColor">我是h3标签</h3>
		<h3 class="myColor">我是h3标签</h3>
		<p>我是段落标签</p>
		<p class="myColor">我是段落标签</p>
		<p>我是段落标签</p>
		<input type="button" value="提交" class="myColor" />
		<input type="button" value="提交" />
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/65365538-file_1488016161033_9de4.png)

## 7.6	复合选择器

> 根据元素的名称、id、类名，使符合条件的元素共同拥有样式;各选择器条件要以**分号****(,)**隔开。
>
> 语法: 
>
> h2 , #subid , .subclass {color:blue;}

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style type="text/css">
			#box,.mytitle,input{
				color:blue;
			}
		</style>
	</head>
	<body>
		<div id="box">我是内容部分</div>
		<h2 class="mytitle">我是2级标题</h2>
		<h3 class="mytitle">我是3级标题</h3>
		<h3>我是3级标题</h3>
		<input type="button" value="按钮" />
		<input type="button" value="按钮" />
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/6451716-file_1488018336895_da6e.png)

# 八、选择器的优先级及权重

> 先来比较一下行内样式表及id选择器

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS选择器</title>
		<style type="text/css">
			#myColor{
				color: blue;
			}
		</style>
	</head>
	<body>
		<h3 style="color:red;" id="myColor">我是内容部分</h3>
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/18865007-file_1488019440876_1355b.png)

==**结论1：很明显,行内的样式比id选择器的优先级要高，**==

> 接下来我们再来比较一下id选择器及类别选器的样式。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS选择器</title>
		<style type="text/css">
			.myStyle{
				color: orange;	
			}
			#myColor{
				color: blue;
			}
		</style>
	</head>
	<body>
		<h3 id="myColor" class="myStyle">我是内容部分</h3>
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/84085415-file_1488019634908_af56.png)

==**结论2：很明显，不难看出，id选择器比类别选别器的优先级要高**==

> .那我们再来比较一下类别选择器和标签选择器。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS选择器</title>
		<style type="text/css">
			.myStyle{
				color: orange;	
			}
			h3{
				color: deepskyblue;
			}
		</style>
	</head>
	<body>
		<h3  class="myStyle">我是内容部分</h3>
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/88003470-file_1488019755039_1709d.png)

==**结论3:大家也看了吧，明显的类别选择器比标签选择器的优先级要高**==

> ，那我们再来看一下标签选择器和全局选择器谁的优先级高！

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>CSS选择器</title>
		<style type="text/css">
			*{
				color: orange;	
			}
			h3{
				color: deepskyblue;
			}
		</style>
	</head>
	<body>
		<h3 >我是内容部分</h3>
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/24089987-file_1488019869707_44a2.png)

==**结论4：很明显，标签选择器比全局选择器的优先级要高。综上述，我们就知道了选择器的优先级了！**==



==***最终结论：***

==***行内样式表>id选择器>类别选择器>标签选择器>全局选择器***==

```tex
在CSS中，会根据选择器的特殊性来决定所定义的样式规则的次序，具有更特殊选择器的规则优先于具有一般选择器的规则，如果两个规则的特殊性相同，那么后定义的规则优先。

那么，又怎么来计算选择器的特殊性呢？

我们把特殊性分为4个等级，每个等级代表一类选择器，每个等级的值为其所代表的选择器的个数乘以这一等级的权值，最后把所有等级的值相加得出选择器的特殊值。

4个等级的定义如下：
1.	第一等：代表行内样式，如: style=””，权值为1000。
2.	第二等：代表ID选择器，如：#content，权值为100。
3.	第三等：代表类，伪类和属性选择器，如.content，权值为10。
4.	第四等：代表类型选择器和伪元素选择器，如div p，权值为1。

注意：通用选择器（*），子选择器（>）和相邻同胞选择器（+）并不在这四个等级中，所以他们的权值都为0。
理解选择器的特殊性很重要，特别是在修复bug的时候，因为你需要了解哪些规则优先及其原因。至于具体的应用，我们放到后面的再做具体的讲解。

最后我们再说一下选择器如何使用，原则有三点：
1.	选择可以准确的找到要控制的标签； 
2.	使用最合理的优先级的选择器； 
3.	还要是html和css看起来简洁美观可读性强。 

好了，我们了解了选择器，我们一直在使用一个样式那就是文字颜色（color）,觉得有些厌烦了，我们再看一下其它的常用的样式。

```

# 九、一些CSS基本样式

> 1. color：颜色；规定颜色值为颜色单词名称例如（red）或者十六进制值得颜色例如（#ff0000）或者为rgb值得颜色例如（rgb(255,0,0)）；
>
> 2.       width:宽度；设置元素的宽度值，值为数字；单位为px（像素)、em（字符）、%（百分比）；默认值为auto（自动，通过浏览器自动计算出宽度值单位为像素）
> 3.        height：高度；设置元素的高度值，值为数字；单位为px（像素)、em（字符）、%（百分比）；默认值为auto（自动，通过浏览器自动计算出宽度值单位为像素）
> 4.        background-color:背景颜色；规定颜色值为颜色单词名称例如（red）或者十六进制值得颜色例如（#ff0000）或者为rgb值得颜色例如（rgb(255,0,0)）；
> 5.        inherit：属性值，大部分属性都有该属性值意义为继承。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style type="text/css">
			.box{
				width: 300px;
				height: 200px;
				color:red;
				background-color:yellow;
			}
		</style>
	</head>
	<body>
		<div class="box">我是内容部分</div>
	</body>
</html>
```

![](http://o7cqr8cfk.bkt.clouddn.com/17-2-25/7903175-file_1488024510878_a9ec.png)

# 十、CSS的尺寸单位介绍

> 1. px：为像素单位。它是显示屏上显示的每一个小点，为显示的最小单位。它是一个绝对尺寸单位；是固定单位。
> 2. em：它是描述相对于应用在当前元素的字体尺寸，所以它也是相对长度单位。一般浏览器字体大小默认为16px，则2em == 32px；是相对于其父元素来设置字体大小的.
> 3. %： 百分比，它是一个更纯粹的相对长度单位。它描述的是相对于父元素的百分比值。如50%，则为父元素的一半。 
> 4. rem**：**是相对单位;** **是相对于根元素<html>改变大小。 

# 十一、CSS的颜色值表示法

> 1. 单词表示法 
>
> red green blue black white grey yellow pink orange…
>
> 2. 十六进制表示法 
>
> \#ff0000 #00ff00 #0000ff #000000 #ffffff   #111111
>
> \#f00 #0f0  #00f  #000 #fff #111
>
> 3. rgb表示法 
>
> (255,0,0)
>
> 4. rgba表示法 
>
> (255,255,0,0.3)
>
> 5. CSS3新支持的HSL和HSLA颜色


















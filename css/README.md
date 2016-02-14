##样式表
可以对文档进行格式化
- 外部插入
 - 在html文档的`<head> </head>`中插入添加
  
  ```bash
  <link rel="stylesheet" type="text/css" href="mystyle.css">
  ```
- 内部样式表
 - 可以在head部分通过`<style>`标签定义

 ```bash
<style type="text/css">
	body {
		background-color: red
	}
	p {
		margin-left: 20px
	}
</style>
 ```
- 内联样式表
 - 特殊的样式应用到个别元素
 
 ```bash
 <p style="color: red; margin-left: 20px">
This is a paragraph
</p>
 ```

- 其他常用样式
| 标签 | 描述 |
|--------|--------|
|`<style>`| 定义样式定义    |
|`<link>` | 定义资源应用|
|`<div>`| 定义文档中的节或区域(块级)|
|`<span>`|定义文档中行内小块或区域|
|`<font>`|字体|
|`<basefont>`|基准字体|
|`<center>`|居中显示|

- background-color 属性为元素设置背景色
- background-image 属性把图像放入背景

 ```bash
 body {background-image: url(img/eg_bg_04.gif);}
 ```

- background-repeat 属性背景重复
 - repeat-x 和 repeat-y 分别导致图像只在水平或垂直方向上重复
 - no-repeat 则不允许图像在任何方向上平铺。

   ```bash
   body {
     background-image:url(img/eg_bg_03.gif);
     background-repeat: repeat-y;
   }
   ```

- background-position 属性,给背景定位
 
 ```bash
 body {
	background-image:url('/i/eg_bg_03.gif');
	background-repeat:no-repeat;
	background-position:center;
 }
 ```

- 关键字
 - 图像放置关键字最容易理解， 其作用如其名称所表明的。 例如， top right 使图像放置在元素内边距区的右上角。
 - 根据规范， 位置关键字可以按任何顺序出现， 只要保证不超过两个关键字 - 一个对应水平方向， 另一个对应垂直方向。
 - 如果只出现一个关键字， 则认为另一个关键字是 center。

- 背景关联
 - 如果文档比较长， 那么当文档向下滚动时， 背景图像也会随之滚动。 当文档滚动到超过图像的位置时， 图像就会消失。
 - 可以通过 background-attachment 属性防止这种滚动,属性的默认值是 scroll， 也就是说， 在默认的情况下， 背景会随文档滚动。
 
 ```bash
 body {
	 background-image:url(img/eg_bg_02.gif);
	 background-repeat:no-repeat;
	 background-attachment:fixed
 }
 ```

- 缩进文本
 - 把 Web 页面上的段落的第一行缩进， 这是一种最常用的文本格式化效果。CSS 提供了 text-indent 属性， 该属性可以方便地实现文本缩进。

 ```bash
 p {text-indent: 5em;}
 ```

 - text-indent 属性可以继承

- 水平对齐
 - text-align 是一个基本的属性， 它会影响一个元素中的文本行互相之间的对齐方式。
 -  justify：在两端对齐文本中， 文本行的左右两端都放在父元素的内边界上。 然后， 调整单词和字母间的间隔， 使各行的长度恰好相等。 

- 字间隔
 - word-spacing 属性可以改变字（ 单词） 之间的标准间隔。 其默认值 normal 与设置值为 0 是一样的。
 - word-spacing 属性接受一个正长度值或负长度值。 如果提供一个正长度值， 那么字之间的间隔就会增加。 为 word-spacing 设置一个负值， 会把它拉近：

   ```bash
 p.spread {word-spacing: 30px;}
p.tight {word-spacing: -0.5em;}
<p class="spread">
This is a paragraph. The spaces between words will be increased.
</p>
<p class="tight">
This is a paragraph. The spaces between words will be decreased.
</p>
   ```

- 字母间隔
 - letter-spacing 属性与 word-spacing 的区别在于， 字母间隔修改的是字符或字母之间的间隔。
 
   ```bash
 h1 {letter-spacing: -0.5em}
h4 {letter-spacing: 20px}
<h1>This is header 1</h1>
<h4>This is header 4</h4>
   ```

- 字符转换
 - none
 - uppercase
 - lowercase
 - capitalize：每个单词的首写字母大写

   ```bash
 h1 {text-transform: uppercase}
   ```

- 文本装饰
 - text-decoration 属性
   - none
   - underline
   - overline
   - line-through
   - blink

- 处理空白符
 - white-space 属性会影响到用户代理对源文档中的空格、 换行和 tab 字符的处理。
 - 可以用以下声明显式地设置这种默认行为：

   ```bash
   p {white-space: normal;}
   ```

 - 如果将 white-space 设置为 pre， 受这个属性影响的元素中， 空白符的处理就有所不同， 其行为就像 XHTML 的 pre 元素一样；空白符不会被忽略。

    ```bash
	p {white-space: pre}
	```

 - nowrap：会防止元素中的文本换行
 - pre-wrap：该元素中的文本会保留空白符序列， 但是文本行会正常地换行。如果设置为这个值， 源文本中的行分隔符以及生成的行分隔符也会保留。
 - pre-line：pre-line 与 pre-wrap 相反， 会像正常文本中一样合并空白符序列， 但保留换行符。

- 文本方向
 - direction 属性影响块级元素中文本的书写方向、 表中列布局的方向、 内容水平填充其元素框的方向、 以及两端对齐元素中最后一行的位置。

######css字体
- CSS 字体属性定义文本的字体系列、 大小、 加粗、 风格（ 如斜体） 和变形（ 如小型大写字母） 。
- font-family 属性 定义文本的字体系列。
- 字体风格
 - normal
 - italic：斜体
 - oblique：倾斜

- 字体变形
 - font-variant 属性可以设定小型大写字母。

- 字体加粗
 - font-weight 属性设置文本的粗细。

- 字体大小
 - font-size 属性设置文本的大小。
 - 16px=1em

######CSS链接
- 链接的四种状态：
 - a:link - 普通的、 未被访问的链接
 - a:visited - 用户已访问的链接
 - a:hover - 鼠标指针位于链接的上方
 - a:active - 链接被点击的时刻

- a:hover 必须位于 a:link 和 a:visited 之后

- a:active 必须位于 a:hover 之后

- 文本修饰
 - text-decoration 属性大多用于去掉链接中的下划线：

   ```bash
   a:link {text-decoration:none;}
   a:visited {text-decoration:none;}
   a:hover {text-decoration:underline;}
   a:active {text-decoration:underline;}
   ```

- 背景色
 - background-color 属性规定链接的背景色：

######CSS列表
- 要修改用于列表项的标志类型， 可以使用属性 list-style-type：

 ```bash
 ul {list-style-type : square}
 ```

- 对各标志使用一个图像，这可以利用 list-style-image:

 ```bash
 ul li {list-style-image : url(xxx.gif)}
 ```

######CSS表格
- 表格边框
 -  border 属性

    ```bash
	table, th, td {
	    border: 1px solid blue;
	}
	```

- border-collapse 属性设置是否将表格边框折叠为单一边框：

 ```bash
 table {
     border-collapse:collapse;
 }
 table,th, td {
     border: 1px solid black;
 }
 ```

- 表格宽度和高度
 - 通过 width 和 height 属性定义表格的宽度和高度。

- 表格文本对齐
 - text-align 和 vertical-align 属性设置表格中文本的对齐方式。
 - text-align 属性设置水平对齐方式， 比如左对齐、 右对齐或者居中：

    ```bash
	td {
	    text-align: right;
	}
	```

 - vertical-align 属性设置垂直对齐方式， 比如顶部对齐、 底部对齐或居中对齐：

    ```bash
	td {
	    height: 50%;
		vertical-align:bottom;
	}
	```

- 表格内边距
 - padding

- 表格颜色
 - color、background-color

######CSS轮廓
- 轮廓（ outline） 是绘制于元素周围的一条线， 位于边框边缘的外围， 可起到突出元素的作用。
- CSS outline 属性规定元素轮廓的样式、 颜色和宽度。
- outline：设置所有属性
- outline-color：轮廓颜色
- outline-style：轮廓样式
- outline-width：轮廓宽度

######CSS框模型
- CSS 框模型 (Box Model) 规定了元素框处理元素内容、 内边距、 边框 和 外边距的方式。
- **CSS框模型概述**

 ![CSS框模型概述](./img/1.gif)

- 许多元素将由用户代理样式表设置外边距和内边距。 可以通过将元素的 margin 和 padding 设置为零来覆盖这些浏览器样式。

 ```bash
 * {
     margin: 0;
	 padding: 0;
 }
 ```

- CSS内边距
 - CSS padding属性

 ```bash
 h1 {padding: 10px;}
 ```

 - 按照上、 右、 下、 左的顺序分别设置

 ```bash
 h1 {padding: 1px 1px 1px 1px;}
 ```

 - 单边内边距属性
   - padding-top
   - padding-right
   - padding-bottom
   - padding-left

 - 百分数值是相对于其父元素的width计算的。

######CSS边框
- border，有三方面，宽度，样式，以及颜色
- border-style：

 ```bash
 p.aside {border-style: solid dotted dashed double;}
 ```

- 单边样式
 - border-top-style
 - border-right-style
 - border-bottom-style
 - border-left-style

- border-width 属性为边框指定宽度
 - 同样可以设置单边样式
   - border-top-width





















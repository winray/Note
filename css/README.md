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
 -  border-style 的默认值是 none， 如果没有声明样式， 就相当于 border-style:none。 因此， 如果您希望边框出现， 就必须声明一个边框样式。

- 边框颜色
 - border-color 属性，一次最多可接受4个颜色值

    ```bash
	p {
	    border-color: blue rgb(25%, 35%, 45%) #909090 red;
	}
	```

 - 默认的边框颜色是元素本身的前景色。 如果没有为边框声明颜色， 它将与元素的文本颜色相同。 另一方面， 如果元素没有任何文本， 假设它是一个表格， 其中只包含图像， 那么该表的边框颜色就是其父元素的文本颜色（ 因为 color 可以继承） 。 这个父元素很可能是 body、 div 或另一个 table。

 - 定义单边颜色，如：
   - border-top-color

- 透明边框

 - CSS2 引入了边框颜色值 transparent。 这个值用于创建有宽度的不可见边框。 

######CSS外边距
- 围绕在元素边框的空白区域是外边距。 设置外边距会在元素外创建额外的“空白”。
- 设置外边距的最简单的方法就是使用 margin 属性， 这个属性接受任何长度单位、百分数值甚至负值。

- 与内边距的设置相同， 这些值的顺序是从上外边距 (top) 开始围着元素顺时针旋转的：

 - `margin: top right bottom left`

 - 如果缺少左外边距的值， 则使用右外边距的值。
 - 如果缺少下外边距的值， 则使用上外边距的值。
 - 如果缺少右外边距的值， 则使用上外边距的值。

  ![example](img/2.gif)

 - 单边外边距

   ```bash
   p {margin-left: 20px;}   
   ```

- CSS外边距合并

 - 外边距合并指的是， 当两个垂直外边距相遇时， 它们将形成一个外边距。
 - 只有普通文档流中块框的垂直外边距才会发生外边距合并。 行内框、 浮动框或绝对定位之间的外边距不会合并。

######CSS定位
- 只有普通文档流中块框的垂直外边距才会发生外边距合并。 行内框、 浮动框或绝对定位之间的外边距不会合并。

- CSS 有三种基本的定位机制：
 - 普通流
 - 浮动定位
 - 绝对定位

- 除非专门指定， 否则所有框都在普通流中定位。

- position 属性值的含义：
 - static
 - relative
 - absolute
 - fixed

- 相对定位
 - `position: relative`

 ![example](./img/3.png)

- 绝对定位

 - 绝对定位使元素的位置与文档流无关， 因此不占据空间。 这一点与相对定位不同，相对定位实际上被看作普通流定位模型的一部分， 因为元素的位置相对于它在普通流中的位置。
 - `position: absolute`

 ![example](./img/4.png)

 - 绝对定位的元素的位置相对于最近的已定位祖先元素， 如果元素没有已定位的祖先元素， 那么它的位置相对于最初的包含块。


- CSS浮动

 - 在 CSS 中， 我们通过 float 属性实现元素的浮动。
 - 浮动框旁边的行框被缩短， 从而给浮动框留出空间， 行框围绕浮动框。因此， 创建浮动框可以使文本围绕图像：
 - 要想阻止行框围绕浮动框， 需要对该框应用 clear 属性。 clear 属性的值可以是left、 right、 both 或 none， 它表示框的哪些边不应该挨着浮动框。


######CSS元素选择器
- 最常见的 CSS 选择器是元素选择器。 换句话说， 文档的元素就是最基本的选择器。

- 选择器分组

 - `h2, p {color:gray;}`

- 通配符选择器

 - 引入了一种新的简单选择器 - 通配选择器（ universal selector） ， 显示为一个星号（ *） 。 该选择器可以与任何元素匹配， 就像是一个通配符。

 ` * {color: red;}`

 - **在规则的最后一个声明后也加上分号是一个好习惯。 在向规则增加另一个声明时， 就不必担心忘记再插入一个分号。**

- 类选择器（`class`）
 - 类名前有一个点号`.`
 - 可以统一使用类
 - 也可以结合元素选择器,eg.`p.example{color: red;}`

- 多类选择器
 - 各个词之间用空格分隔。 例如， 如果希望将一个特定的元素同时标记为重要（ important） 和警告（ warning），就可以写作：

 ```bash
 <p class="important warning">
This paragraph is a very important warning.
</p>
 ```
 
 - 这两个词的顺序无关紧要， 写成 warning important 也可以。


######CSS ID选择器
- ID 选择器前面有一个 # 号 - 也称为棋盘号或井号。
- ID 选择器不引用 class 属性的值， 毫无疑问， 它要引用 id 属性中的
值。

######类选择器还是 ID 选择器？
- 与类不同， 在一个 HTML 文档中， ID 选择器会使用一次， 而且仅一次。
- 不同于类选择器， ID 选择器不能结合使用， 因为 ID 属性不允许有以空格分隔的词列表。
- 类选择器和 ID 选择器可能是区分大小写的。 这取决于文档的语言。 HTML和 XHTML 将类和 ID 值定义为区分大小写， 所以类和 ID 值的大小写必须与文档中的相应值匹配。


######CSS 属性选择器
- 属性选择器可以根据元素的属性及属性值来选择元素。
- example
 - 如果您希望把包含标题（ title） 的所有元素变为红色， 可以写作：

    ```bash
	*[title] {color:red;}
	```

 - 与上面类似， 可以只对有 href 属性的锚（ a 元素） 应用样式：

    ```bash
	a[href] {color:red;}
	```

 - 还可以根据多个属性进行选择， 只需将属性选择器链接在一起即可。

    ```bash
	a[href][title] {color:red;}
	```

- 根据具体属性值选择
 - 除了选择拥有某些属性的元素， 还可以进一步缩小选择范围， 只选择有特定属性值的元素。

 ```bash
 a[href="http://www.w3school.com.cn/about_us.asp"] {color: red;}
 ```

 - 与简单属性选择器类似， 可以把多个属性-值选择器链接在一起来选择一个文档。

 ```bash
 a[href="http://www.w3school.com.cn/"][title="W3School"] {color: red;}
 ```

 - **属性与属性值必须完全匹配**
   - 如果属性值包含用空格分隔的值列表， 匹配就可能出问题。

 - **根据部分属性值选择**
   - 如果需要根据属性值中的词列表的某个词进行选择， 则需要使用波浪号（ ~） 。

 ```bash
 p[class~="important"] {color: red;}
 ```

######子串匹配属性选择器
example:

| 类型 | 描述 |
|--------|--------|
| [abc^="def"]|选择 abc 属性值以 "def" 开头的所有元素|
|[abc$="def"]|选择 abc 属性值以 "def" 结尾的所有元素|
|[abc*="def"]|选择 abc 属性值中包含子串 "def" 的所有元素|

######特定属性选择类型
example：
- `*[lang|="en"] {color: red;}`
 - 上面这个规则会选择 lang 属性等于 en 或以 en- 开头的所有元素。

- **一般来说， [att|="val"] 可以用于任何属性及其值。**


######CSS后代选择器
- 后代选择器（descendant selector）又称为包含选择器。后代选择器可以选择作为某元素后代的元素。

- 根据上下文选择元素
 - 举例来说， 如果您希望只对 h1 元素中的 em 元素应用样式， 可以这样写：`h1 em {color:red;}`

######CSS 子元素选择器
- 如果您不希望选择任意的后代元素， 而是希望缩小范围， 只选择某个元素的子元素， 请使用子元素选择器（ Child selector） 。
- example `h1 > strong {color:red;}`
 - 这个规则会把第一个 h1 下面的两个 strong 元素变为红色， 但是之后h1中的strong 不受影响：


######CSS 相邻兄弟选择器
- 相邻兄弟选择器（ Adjacent sibling selector） 可选择紧接在另一元素后的元素，且二者有相同父元素。
- example：如果要增加紧接在 h1 元素后出现的段落的上边距， 可以这样写：

 ```bash
 h1 + p {margin-top:50px;}
 ```

 - 选择紧接在 h1 元素后出现的段落， h1 和 p 元素拥有共同的父元素;


######CSS伪类`Pseudo-classes`
- CSS 伪类用于向某些选择器添加特殊的效果。

- 伪类可以与 CSS 类配合使用：`a.red : visited {color: #FF0000}`

- 伪元素的语法：`selector:pseudo-element {property:value;}`

- 可以结合多个伪元素来使用.


######CSS水平对齐
- 对齐块元素


















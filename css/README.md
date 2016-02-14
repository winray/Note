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


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
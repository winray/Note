##HTML
######概念
超文本标记语言(Hyper Text Markup Language)
######标签
html标记标签通常被称为html标签(html tag),如<html>，通常成对出现(开始标签和结束标签)
######html文档=网页
浏览器不显示html标签，而是使用标签来解释页面的内容
```bash
<html>
<body>
<h1>My First Heading</h1>
<p>My first paragraph.</p>
</body>
</html>
```
######基本元素
html文档是由html元素定义的。
```bash
标题：
<h1>-<h6>
段落：
<p>
链接：
<a href="...">...</a>
图像:
<img src="..." width="..." height="..."/>
```
######元素语法
- 以开始标签起始
- 以结束标签终止
- 内容在开始、结束标签之间
- 某些元素具有空内容,如：`<br\>`
- 空元素在开始标签中进行关闭
- 大多数html元素拥有属性值
- 大多数html元素可嵌套
- 使用小写标签

######html属性
- 总是以***名称/值***对的形式出现
- 总是在html元素的开始标签中规定
- 如:

```bash
align: 对齐
bgcolor：背景颜色
border：边框
```
- 属性值加引号(单引号、双引号都可以)
- 具体属性值可以上网查找，但要知道常用的属性值如何使用

######常用知识点
- ` <hr /> `:可用于分割内容
- 注释`<!-- comment -->`
- 借助浏览器查看源码
- 浏览器会自动在段落前后添加空行
- **不要忘记结束标签**
- 换行使用`<br />`
- 浏览器会自动移除多余的空格和空行而只显示一个空格

- 超链接`<a>`
 - 文字
 - 图像
 - 按钮
 - **target**属性: 定义了打开方式
 - **name**属性: 对读者不可见

- 图像
 - alt属性: 为图像定义一串预备的可替换的文本
 - 加载图片需要时间，慎用图片
 - map定义图像地图
 - area定义图像地图中可点的区域、

- 表格
 - `<table>、<tr>、<td>`
 - 边框属性: `<border>`
 - 表格的表头: `<th>`
   - 大多数浏览器会把表头显示为粗体并居中的文本
 - 如果表格内容为空，浏览器可能无法显示出这个单元格的边框。
   - 为了避免，使用空格占位符
 - `<caption>`: title

- 列表
 - 无序
   - 始于`<ul>`标签
   - 每个列表项始于`<li>`
    
	 ```bash
	<ul>
		<li>Coffee</li>
		<li>Milk</li>
	</ul>
      ```
 - 有序
   - `<ol>`
 - 定义列表
   - 始于`<dl>`标签
   - 每个自定义列表项以`<dt>`开始
   - 每个自定义列表始于`<dd>`
    
	 ```bash
	<dl>
		<dt>Coffee</dt>
			<dd>Black hot drink</dd>
		<dt>Milk</dt>
			<dd>White cold drink</dd>
	</dl>
      ```
- `<div>、<span>`
 - 用于布局，亦可用表格进行布局
 - 可用于对大的内容快进行样式设置
 - `<div>`: 块元素
 - `<span>`: 内联元素
 - 可使用网上免费开源模版来快速布局，根据需求对模版进行优化

- 表单
 - `<form>`
 - 输入：`<input>`
  
   ```bash
  <input type="text" name="input" />
   ```
 - 单选按钮：**radio**
 
   ```bash
   <form>
		<input type="radio" name="sex" value="male" /> Male
		<br />
		<input type="radio" name="sex" value="female" /> Female
	</form>
   ```
 
 - 复选框：**checkbox**
 
   ```bash
   <form>
		<input type="checkbox" name="bike" />
		I have a bike
		<br />
		<input type="checkbox" name="car" />
		I have a car
	</form>
   ```
 
 - 动作属性：**action**和确认按钮
  
   ```bash
   <form name="input" action="html_form_action.asp" method="get">
		Username:
		<input type="text" name="user" />
		<input type="submit" value="Submit" />
	</form>
   ```

######html框架 `<frameset>`
使用框架可以在浏览器中显示不止一个页面
- 垂直框架

 ```bash
<frameset cols="25%,50%,25%">
	<frame src="/example/html/frame_a.html">
	<frame src="/example/html/frame_b.html">
	<frame src="/example/html/frame_c.html">
</frameset>
 ```

- 水平框架

 ```bash
<frameset rows="25%,50%,25%">
	<frame src="/example/html/frame_a.html">
	<frame src="/example/html/frame_b.html">
	<frame src="/example/html/frame_c.html">
</frameset>
 ```

- 混合框架

 ```bash
<frameset rows="25%,50%"> 
	<frame src="/example/html/frame_a.html">
	<frameset rows="25%,50%,25%">
		<frame src="/example/html/frame_b.html">
		<frame src="/example/html/frame_c.html">
		<frame src="/example/html/frame_d.html">
	</frameset>
</frameset>
 ```

- 内联框架 `<iframe>`
 - **height、width**设置高、宽
 - `frameborder="0"`移除边框
 - 可用作链接的目标(**target**)

######html背景
好的背景让站点加分
- 颜色
 - `bgcolor="FFFFFF"`
 - 大多数浏览器支持颜色名集合
- 图像
 - 属性值为图像的url，若图像小于浏览器尺寸，图像将在整个浏览器窗口进行复制
 - `<body background="1.jpg">`

######html4.01快速参考
网页链接：http://www.w3school.com.cn/html/html_quick.asp

######html高级
`<!DOCTYPE html>`声明，表示为最新的html5文档类型。

######head元素
- title: 文档标题
- base：为页面上所有链接规定默认地址或默认目标

 ```bash
 <base href="http://www.w3school.com.cn/images/" />
 <base target="_blank" />
 ```

- link: 定义文档与外部资源之间的关系，最常用于谅解样式表：

 ```bash
 <link rel="stylesheet" type="text/css" href="mystyle.css" />
 ```

- style: 可以在style元素内规定html元素在浏览器中呈现的样式：

 ```bash
 <head>
	<style type="text/css">
	body {background-color:yellow}
	p {color:blue}
	</style>
</head>
 ```

- meta: metadata(元数据)
 - name 和 content 属性的作用是描述页面的内容。针对搜索引擎的关键词。

 ```bash
 <meta name="keywords" content="HTML, CSS, XML" />
 ```

- script：用于定义客户端脚本，比如javascrip。
 - JavaScript 使 HTML 页面具有更强的动态和交互性。

###### 字符实体
&nbsp;&nbsp;&nbsp;&nbsp;HTML 中的预留字符必须被替换为字符实体。如空格：`&nbsp;`

###### HTML统一资源定位器

















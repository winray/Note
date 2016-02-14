##HTML

[TOC]


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
- URL，Uniform Resource Locator，也被称为网址
- `scheme://host.domain:port/path/filename`
 - scheme - 定义因特网服务的类型。 最常见的类型是 http
 - host - 定义域主机（ http 的默认主机是 www）
 - domain - 定义因特网域名， 比如 w3school.com.cn
 - :port - 定义主机上的端口号（ http 的默认端口号是 80）
 - path - 定义服务器上的路径（ 如果省略， 则文档必须位于网站的根目录中）
 - filename - 定义文档/资源的名称

- URL 只能使用 ASCII 字符集来通过因特网进行发送。

######HTML Web Server
向世界发布自己的网站，那么需要将其放到web服务器上。
- 托管自己的网站，不建议
- 使用因特网服务提供商(**ISP**)

######HTML多媒体
- Web 上的多媒体指的是音效、 音乐、 视频和动画。
- 注意事项
 - 多媒体格式
 - 视频格式
 - 声音格式
 - 确定使用何种格式

######HTML Object元素
- `<object>` 的作用是支持 HTML 助手（ 插件） 。
- 辅助程序可用于播放音频和视频(以及其他)。辅助程序是使用 `<object>` 标签来加载的。

 ```bash
 <object width="420" height="360" classid="clsid:02BF25D5-8C17-4B23-BC80-D3488ABDDC6B" codebase="http://www.apple.com/qtactivex/qtplugin.cab">
	<param name="src" value="bird.wav" />
	<param name="controller" value="true" />
</object>
 ```

- 下面的例子使用了两个不同的音频格式。 HTML5 `<audio>` 元素会尝试以 mp3 或ogg 来播放音频。 如果失败， 代码将回退尝试 `<embed> `元素。

 ```bash
 <audio controls="controls" height="100" width="100">
	<source src="song.mp3" type="audio/mp3" />
	<source src="song.ogg" type="audio/ogg" />
	<embed height="100" width="100" src="song.mp3" />
 </audio>
 ```

- 雅虎媒体播放器：只需简单地让雅虎来完成歌曲播放的工作就可以了。

- 视频

 ```bash
 <video width="320" height="240" controls="controls">
	<source src="movie.mp4" type="video/mp4" />
	<source src="movie.ogg" type="video/ogg" />
	<source src="movie.webm" type="video/webm" />
	<object data="movie.mp4" width="320" height="240">
		<embed src="movie.swf" width="320" height="240" />
	</object>
 </video>
 ```

 - **最好的解决方法：**下面使用了 4 中不同的视频格式。 HTML 5 `<video>` 元素会尝试播放以 mp4、ogg 或 webm 格式中的一种来播放视频。 如果均失败， 则回退到 `<embed>` 元素。

 ```bash
 <video width="320" height="240" controls="controls">
	<source src="movie.mp4" type="video/mp4" />
	<source src="movie.ogg" type="video/ogg" />
	<source src="movie.webm" type="video/webm" />
	<object data="movie.mp4" width="320" height="240">
		<embed src="movie.swf" width="320" height="240" />
	</object>
</video>
 ```

 - 优酷解决方案
   - 在 HTML 中显示视频的最简单的方法是使用优酷等视频网站。

######XHTML简介
- XHTML 是以 XML 格式编写的 HTML。
 - XHTML 指的是可扩展超文本标记语言
 - XHTML 与 HTML 4.01 几乎是相同的
 - XHTML 是更严格更纯净的 HTML 版本
 - XHTML 是以 XML 应用的方式定义的 HTML
 - XHTML 是 2001 年 1 月发布的 W3C 推荐标准
 - XHTML 得到所有主流浏览器的支持

- 优点
 - XML 是一种必须正确标记且格式良好的标记语言。
 - XHTML 元素必须正确嵌套
 - XHTML 元素必须始终关闭
 - XHTML 元素必须小写
 - XHTML 文档必须有一个根元素
 - 空元素也必须关闭

- XHTML属性
 - XHTML 属性必须使用小写
 - XHTML 属性值必须用引号包围
 - XHTML 属性最小化也是禁止的

######HTML5简介
- HTML5 为 HTML、 XHTML 以及 HTML DOM 的新标准。
- 为 HTML5 建立的一些规则：
 - 新特性应该基于 HTML、 CSS、 DOM 以及 JavaScript。
 - 减少对外部插件的需求（ 比如 Flash）
 - 更优秀的错误处理
 - 更多取代脚本的标记
 - HTML5 应该独立于设备
 - 开发进程应对公众透明

- 新特性：
 - 用于绘画的 canvas 元素
 - 用于媒介回放的 video 和 audio 元素
 - 对本地离线存储的更好的支持
 - 新的特殊内容元素， 比如 article、 footer、 header、 nav、 section
 - 新的表单控件， 比如 calendar、 date、 time、 email、 url、 search

- html5视频
 - control 属性供添加播放、 暂停和音量控件。包含宽度和高度属性也是不错的主意。

 ```bash
<video src="movie.ogg" controls="controls">
</video>
 ```

 - HTML5 `<video>` - 使用 DOM 进行控制

- html5音频
 - HTML5 规定了一种通过 audio 元素来包含音频的标准方法。
 - control 属性供添加播放、 暂停和音量控件。`<audio>` 与 `</audio>` 之间插入的内容是供不支持 audio 元素的浏览器显示的：

 ```bash
 <audio src="song.ogg" controls="controls">
 </audio>
 ```

- html5拖放
 - 拖放（ Drag 和 drop） 是 HTML5 标准的组成部分。
 - 设置元素可拖放：

   ```bash
   <img draggable="true" />
   ```

- html5 **Canvas**
 - canvas 元素用于在网页上绘制图形。
 
   ```bash
<canvas id="myCanvas" width="200" height="100"></canvas>
   ```

- html5内联SVG
 - SVG 指可伸缩矢量图形 (Scalable Vector Graphics)
 - SVG 用于定义用于网络的基于矢量的图形
 - SVG 使用 XML 格式定义图形
 - SVG 图像在放大或改变尺寸的情况下其图形质量不会有损失
 - SVG 是万维网联盟的标准

- HTML5 地理定位
 - HTML5 Geolocation（ 地理定位） 用于定位用户的位置。
 - 在地图中显示结果，可使用经纬度的地图服务，比如谷歌地图或百度地图

- HTML 5 Web 存储
 - HTML5 提供了两种在客户端存储数据的新方法：
   - localStorage - 没有时间限制的数据存储
   - sessionStorage - 针对一个 session 的数据存储

- HTML 5 应用程序缓存
 - 使用 HTML5， 通过创建 cache manifest 文件， 可以轻松地创建 web 应用的离线版本。
 - HTML5 引入了应用程序缓存， 这意味着 web 应用可进行缓存， 并可在没有因特网连接时进行访问。
 - 离线浏览 - 用户可在应用离线时使用它们
 - 速度 - 已缓存资源加载得更快
 - 减少服务器负载 - 浏览器将只从服务器下载更新过或更改过的资源。

- HTML 5 Web Workers
 - web worker 是运行在后台的 JavaScript，不会影响页面的性能。

- HTML5 Input类型
 - email 类型用于应该包含 e-mail 地址的输入域。
 
 ```bash
 E-mail: <input type="email" name="user_email" />
 ```
 
 - url 类型用于应该包含 URL 地址的输入域。
 
 ```bash
 Homepage: <input type="url" name="user_url" />
 ```

 - 还有number、range、Date Pickers（ 日期选择器）、search等等。

- html5 表单元素
 - datalist 元素规定输入域的选项列表。
 - keygen 元素的作用是提供一种验证用户的可靠方法。
 - output 元素用于不同类型的输出， 比如计算或脚本输出：

- html5表单属性
 - form 属性：
   - autocomplete
   - novalidate
 - input 属性：
   - autocomplete
   - autofocus
   - height 和 width等等

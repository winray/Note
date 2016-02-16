##Bootstrap
######简介
- 什么是bootstrap
 - Bootstrap 是一个用于快速开发 Web 应用程序和网站的前端框架。 Bootstrap 是基于 HTML、 CSS、 JAVASCRIPT 的。

- 历史

 - Bootstrap 是由 Twitter 的 Mark Otto 和 Jacob Thornton 开发的。 Bootstrap 是2011 年八月在 GitHub 上发布的开源产品。

- 为什么使用bootstrap

 - 移动设备优先：自 Bootstrap 3 起， 框架包含了贯穿于整个库的移动设备优先的样式。
 - 浏览器支持：所有的主流浏览器都支持 Bootstrap
 - 容易上手：只要您具备 HTML 和 CSS 的基础知识， 您就可以开始学习Bootstra
 - 响应式设计：Bootstrap 的响应式 CSS 能够自适应于台式机、 平板电脑和手机。
 - 它为开发人员创建接口提供了一个简洁统一的解决方案
 - 它包含了功能强大的内置组件， 易于定制
 - 它还提供了基于 Web 的定制
 - 它是开源的

- bootstrap包的内容

 - 基本结构：Bootstrap 提供了一个带有网格系统、 链接样式、 背景的基本结构。
 - CSS：Bootstrap 自带以下特性：全局的 CSS 设置、 定义基本的 HTML 元素样式、 可扩展的 class， 以及一个先进的网格系统。
 - 组件：Bootstrap 包含了十几个可重用的组件， 用于创建图像、 下拉菜单、 导航、 警告框、 弹出框等等。 
 - JavaScript 插件：Bootstrap 包含了十几个自定义的 jQuery 插件。 您可以直接包含所有的插件， 也可以逐个包含这些插件。 
 - 定制：您可以定制 Bootstrap 的组件、 LESS 变量和 jQuery 插件来得到您自己的版本。

- Bootstrap CDN推荐
 - 百度的静态资源库(`http://cdn.code.baidu.com/`)上的Bootstrap资源。
 - 百度的静态资源库的 CDN 服务， 访问速度更快、 加速效果更明显、 没有速度和带宽限制、 永久免费！


######Bootstrap CSS 概览
- html5文档类型(Doctype)

 - Bootstrap 使用了一些 HTML5 元素和 CSS 属性。 为了让这些正常工作， 您需要使用 HTML5 文档类型（ Doctype） 。 因此， 请在使用 Bootstrap 项目的开头包含下面的代码段。

    ```bash
	<!DOCTYPE html>
	<html>
	....
	</html>
	```

- 为了让 Bootstrap 开发的网站对移动设备友好， 确保适当的绘制和触屏缩放， 需要在网页的 head 之中添加 viewport meta 标签， 如下所示：

  ```bash
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```

 - `initial-scale=1.0`确保网页加载时， 以 1:1 的比例呈现， 不会有任何的缩放。
 - 在移动设备浏览器上， 通过为 viewport meta 标签添加 user-scalable=no 可以禁用其缩放（ zooming） 功能。
 - 通常情况下， maximum-scale=1.0 与 user-scalable=no 一起使用。 这样禁用缩放功能后， 用户只能滚动屏幕， 就能让您的网站看上去更像原生应用的感觉。
 - **注意， 这种方式我们并不推荐所有网站使用， 还是要看您自己的情况而定！**

    ```bash
	<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
	```

######响应式图像
- `<img src="..." class="img-responsive" alt="响应式图像">`
- 通过添加 img-responsive class 可以让 Bootstrap 3 中的图像对响应式布局的支持更友好。

######全局显示、 排版和链接
- Bootstrap 3 使用 body {margin: 0;} 来移除 body 的边距。
- 排版

 - 使用 @font-family-base、 @font-size-base 和 @line-height-base 属性作为排版样式。

- 链接样式

 - 通过属性 @link-color 设置全局链接的颜色


- 避免跨浏览器的不一致

 - Bootstrap 使用 Normalize 来建立跨浏览器的一致性。
 - Normalize.css 是一个很小的 CSS 文件， 在 HTML 元素的默认样式中提供了更好的跨浏览器一致性。

######容器
```bash
<div class="container">
...
</div>
```

- Bootstrap 3 的 container class 用于包裹页面上的内容。

- 请注意， 由于内边距（ padding） 是固定宽度， 默认情况下容器是不可嵌套的。


######Bootstrap 网格系统(Grid System)
- Bootstrap 提供了一套响应式、 移动设备优先的流式网格系统， 随着屏幕或视口（ viewport） 尺寸的增加， 系统会自动分为最多12列。

 ![网格分布](./img/1.png)

- 工作原理：

 - 行必须放置在 .container class 内， 以便获得适当的对齐（ alignment） 和内边距（ padding） 。
 - 使用行来创建列的水平组。
 - 内容应该放置在列内， 且唯有列可以是行的直接子元素。
 - 预定义的网格类， 比如 .row 和 .col-xs-4， 可用于快速创建网格布局。 LESS混合类可用于更多语义布局。
 - 列通过内边距（ padding） 来创建列内容之间的间隙。 该内边距是通过 .rows上的外边距（ margin） 取负， 表示第一列和最后一列的行偏移。
 - 网格系统是通过指定您想要横跨的十二个可用的列来创建的。 例如， 要创建三个相等的列， 则使用三个 .col-xs-4。

- 媒体查询

 ```bash
 /* 超小设备（ 手机， 小于 768px） */
/* Bootstrap 中默认情况下没有媒体查询 */
/* 小型设备（ 平板电脑， 768px 起） */
@media (min-width: @screen-sm-min) { ... }
/* 中型设备（ 台式电脑， 992px 起） */
@media (min-width: @screen-md-min) { ... }
/* 大型设备（ 大台式电脑， 1200px 起） */
@media (min-width: @screen-lg-min) { ... }
 ```

- 有时候也会在媒体查询代码中包含 max-width， 从而将 CSS 的影响限制在更小范围的屏幕大小之内。

 `@media (min-width: @screen-sm-min) and (max-width: @screen-sm-max)`

######Bootstrap 排版
- Bootstrap 使用 Helvetica Neue、 Helvetica、 Arial 和 sans-serif 作为其默认的字体栈。
- 使用 Bootstrap 的排版特性， 您可以创建标题、 段落、 列表及其他内联元素。

- 内联子标题

 - 如果需要向任何标题添加一个内联子标题， 只需要简单地在元素两旁添加`<small>`

- 引导主体副本

 - 为了给段落添加强调文本， 则可以添加 class="lead"， 这将得到更大更粗、 行高更高的文本


- 缩写

 - HTML `<abbr>`元素提供了用于缩写的标记， 比如 WWW 或 HTTP。 Bootstrap 定义`<abbr>` 元素的样式为显示在文本底部的一条虚线边框， 当鼠标悬停在上面时会显示完整的文本（ 只要您为 `<abbr>` title 属性添加了文本） 。 为了得到一个更小字体的文本， 请添加 .initialism 到 `<abbr> </abbr>`

 `<abbr title="Real Simple Syndication" class="initialism">RSS</abbr>`

- 地址（ Address）
- 引用（ Blockquote）
- 列表

 - Bootstrap 支持有序列表、 无序列表和定义列表。


######Bootstrap 代码
- Bootstrap 允许您以两种方式显示代码：

 - 第一种是 `<code>` 标签。 如果您想要内联显示代码， 那么您应该使用 `<code>`标签。
 - 第二种是 `<pre>` 标签。 如果代码需要被显示为一个独立的块元素或者代码有多行， 那么您应该使用 `<pre>` 标签。


######Bootstrap 表格
- 如果您想要一个只带有内边距（ padding） 和水平分割的基本表， 请添加 class.table

- 条纹表格

 - 通过添加 .table-striped class， 您将在 `<tbody>` 内的行上看到条纹

- 边框表格

 - 通过添加 .table-bordered class， 您将看到每个元素周围都有边框， 且占整个表格是圆角的

- 悬停表格

 - 通过添加 .table-hover class， 当指针悬停在行上时会出现浅灰色背景


- 精简表格

 - 通过添加 .table-condensed class， 行内边距（ padding） 被切为两半， 以便让表看起来更紧凑

- 上下文类

 - 下表中所列出的上下文类允许您改变表格行或单个单元格的背景颜色。

    ![表格](./img/2.png)

 - 这些类可被应用到 `<tr>`、 `<td>` 或 `<th>`。

- 响应式表格

 - 通过把任意的 .table 包在 .table-responsive class 内， 您可以让表格水平滚动以适应小型设备（ 小于 768px） 。 当在大于 768px 宽的大型设备上查看时， 您将看不到任何的差别。

######Bootstrap 表单
Bootstrap 通过一些简单的HTML 标记和扩展的类即可创建出不同样式的表单。

- Bootstrap 提供了下列类型的表单布局：

 - 垂直表单（ 默认）
 - 内联表单
 - 水平表单

- 向父`<form>`元素添加 role="form"
- 把标签和控件放在一个带有 class .form-group 的 `<div>` 中。 这是获取最佳间距所必需的。
- 向所有的文本元素 `<input>`、 `<textarea>` 和 `<select>` 添加 class .formcontrol。

- 内联表单

 - 如果需要创建一个表单， 它的所有元素是内联的， 向左对齐的， 标签是并排的， 请向` <form> `标签添加 class .form-inline

- 水平表单

 - 水平表单与其他表单不仅标记的数量上不同， 而且表单的呈现形式也不同。
 - 向父 `<form>` 元素添加 class .form-horizontal
 - 把标签和控件放在一个带有 class .form-group 的` <div> `中
 - 向标签添加 class .control-label

- 支持的表单控件

 - Bootstrap 支持最常见的表单控件， 主要是 input、 textarea、 checkbox、 radio 和select。

- 静态控件

 - 当您需要在一个水平表单内的表单标签后放置纯文本时， 请在 `<p>` 上使用 class.form-control-static。

- 表单控件状态

 - 除了 :focus 状态（ 即， 用户点击 input 或使用 tab 键聚焦到 input 上） ， Bootstrap还为禁用的输入框定义了样式， 并提供了表单验证的 class。

 - 验证状态
   - Bootstrap 包含了错误、 警告和成功消息的验证样式。 只需要对父元素简单地添加适当的 class（ .has-warning、 .has-error 或 .has-success） 即可使用验证状态。

- 表单控件大小
 - 您可以分别使用 class .input-lg 和 .col-lg-* 来设置表单的高度和宽度。 下面的实例演示了这点：

- 表单帮助文本

 - Bootstrap 表单控件可以在输入框 input 上有一个块级帮助文本。 为了添加一个占用整个宽度的内容块， 请在 `<input>` 后使用 .help-block。 下面的实例演示了这点：


######Bootstrap 按钮
- 任何带有 class .btn 的元素都会继承圆角灰色按钮的默认外观。 但是 Bootstrap 提供了一些选项来定义按钮的样式，具体如下表所示：

  ![表格](./img/3.png)

- 还可以设置按钮大小
 ![btn](./img/4.png)

- 按钮状态
 ![btnState](./img/5.png)
 ![btnState](./img/6.png)

- 按钮标签

 - 可以在 `<a>`、 `<button>` 或 `<input>` 元素上使用按钮 class。 但是建议您在`<button>` 元素上使用按钮 class， 避免跨浏览器的不一致性问题。


######Bootstrap 图像
-  Bootstrap 提供了三个可对图像应用简单样式的 class：

 - .img-rounded：添加 border-radius:6px 来获得图像圆角。
 - .img-circle：添加 border-radius:500px 来让整个图像变成圆形。
 - .img-thumbnail：添加一些内边距（ padding） 和一个灰色的边框。


######Bootstrap 响应式实用工具
![btnState](./img/7.png)
![btnState](./img/8.png)

######Bootstrap 字形图标（ Glyphicons）
Bootstrap捆绑了 200 多种字体格式的字形
- 用法

 - 如需使用图标， 只需要简单地使用下面的代码即可。 请在图标和文本之间保留适当的空间。

 `<span class="glyphicon glyphicon-search"></span>`

######Bootstrap 下拉菜单（ Dropdowns）
- 下拉菜单是可切换的， 是以列表格式显示链接的上下文菜单。 这可以通过与 下拉菜单（ Dropdown） JavaScript 插件 的互动来实现。
- 如需使用下列菜单， 只需要在 class .dropdown 内加上下拉菜单即可。
- 对齐

 - 通过向 .dropdown-menu 添加 class .pull-right 来向右对齐下拉菜单

- 标题

 - 可以使用 class dropdown-header 向下拉菜单的标签区域添加标题

######Bootstrap 按钮组
- 按钮组允许多个按钮被堆叠在同一行上。 当你想要把按钮对齐在一起时， 这就显得非常有用。 可以通过 Bootstrap 按钮（ Button） 插件 添加可选的 JavaScript 单选框和复选框样式行为。

- .btn-group

 - 该 class 用于形成基本的按钮组。 在 .btn-group 中放置一系列带有 class .btn 的按钮。

- .btn-toolbar

 - 该 class 有助于把几组` <div class="btn-group">` 结合到一个` <div class="btntoolbar">` 中， 一般获得更复杂的组件。

- .btn-group-lg, .btn-group-sm, .btn-group-xs
 - 这些 class 可应用到整个按钮组的大小调整， 而不需要对每个按钮进行大小调整。

- .btn-group-vertical

 - 该 class 让一组按钮垂直堆叠显示， 而不是水平堆叠显示。

- 嵌套

 - 可以在一个按钮组内嵌套另一个按钮组， 即， 在一个 .btn-group 内嵌套另一个.btn-group 。 当您向让下拉菜单与一系列按钮组合使用时， 就会用到这个。

######按钮
- 如需向按钮添加下拉菜单， 只需要简单地在在一个 .btn-group 中放置按钮和下拉菜单即可。 您也可以使用 `<span class="caret"></span> `来指示按钮作为下拉菜单。

- 分割的按钮下拉菜单

 - 分割的按钮下拉菜单使用与下拉菜单按钮大致相同的样式， 但是对下拉菜单添加了原始的功能。 分割按钮的左边是原始的功能， 右边是显示下拉菜单的切换。

- 按钮下拉菜单的大小

 - 可以使用带有各种大小按钮的下拉菜单：.btn-large、 .btn-sm 或 .btn-xs

- 按钮上拉菜单
 - 菜单也可以往上拉伸的， 只需要简单地向父 .btn-group 容器添加 .dropup 即可。

######Bootstrap 输入框组



































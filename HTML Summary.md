# HTML总结

## 元素
HTML由元素组成，元素可以嵌套，例如：
\<p>hello world \</p>
这就是一个元素，元素有开始标签和结束标签，以上述语句为例也就是\<p>和\</p>，而hello world则是内容，内容和标签结合即是一个完整的元素。

## HTML基本组成
HTML文档必定包含以下内容：
### 1. \<html>\</html>
这个标签内包含了所有其他的标签，其他元素都会被嵌套在其中，而通常开始标签处会这么写\<html lang="en">，代表这是一个英文站点，这么写可以方便搜索引擎对其进行收录，如果要改为中文站点，只需要改为\<html lang="zh">即可，但无论是en还是zh，对里面的内容都没有影响。
### 2. \<head>\</head>
head元素包含了各种标签元素，在head元素中，可以插入脚本（script），样式文件（CSS），以及各种meta信息。在此处可以添加的元素有：\<title>, \<style>, \<meta>, \<link>, \<script>和 \<base>。
<br> \<title>：1. 定义了浏览器工具栏的标题  2. 当网页添加到收藏夹时，显示在收藏夹中的标题  3. 显示在搜索引擎结果页面的标题
<br> \<style>：在此元素中定义了HTML文档的样式文件引用地址，也可以直接添加样式来渲染 HTML 文档。例如：
<style>
    @import url(style.css);
</style>

<style>
      .old-browser-tip .title {
        background: #00a1d6;
        text-align: center;
        padding: 10px 0;
        color: #fff;
      }
</style>

<br> \<meta>：\<meta>描述了一些基本的元数据,元数据不会显示在页面上，但是会被浏览器解析，\<meta>元素通常用于指定网页的描述，关键词，文件的最后修改时间，作者，和其他元数据。搜索引擎可以通过\<meta>来通过关键词搜索相关网页。

<br> \<link>：\<link>标签定义了文档与外部资源之间的关系，例如\<link rel="stylesheet" type="text/css" href="mystyle.css">，这就是调用了外部的CSS文件。其他文件类似。

<br> \<script>：\<script>用于加载脚本文件，例如JavaScript，typescript等。

<br> \<base>：\<base>描述了基本的链接地址/链接目标，该标签作为HTML文档中所有的链接标签的默认链接，例如：
<base href="http://www.runoob.com/images/" target="_blank">

### 3. \<body>\</body> 
这个标签中包含了html页面的绝大部分显示内容
<br> 标题（heading）：搜索引擎用标题来索引页面的内容，用户也习惯以标题进行主要内容浏览，以决定是否查看该页面，HTML有六级标题，从\<h1>\</h1>到\<h6>\</h6>，其中\<h1>最大，通常作为主标题，\<h6>最小。

<br> 文本格式：文本格式标签推荐使用如下几种
\<mark>\</mark>，\<del>\</del>，\<s>\</s>，\<ins>\</ins>，\<small>\</small>，\<strong>\</strong>，\<em>\</em>
<br>文本格式不需要用于对页面进行美化，CSS更适合进行页面美化。

<br>超链接：任何东西均可以使用超链接，通常超链接是图片、网址、文本等。语法如下：
<a href="https://www.baidu.com/" target="_blank">百度一下</a>

<br>锚点：
锚点，也称为书签，用于标记页面的某个元素或位置。通过锚点，我们可以轻易的在长页面内实现跳转。先使用id属性生成某元素的锚点，然后再使用超链接指向该锚点即可。例如：
<!-- 文档其余部分 -->
<h2 id="C4">第四章 论零号病人的重要性</h2>
<!-- 文档其余部分 -->
<a href="#C4">跳到第四章</a>
<!-- 文档其余部分 -->
...

<br>插入图片：
src属性为要图片的URL，即图片文件的路径，alt属性当获取图片出现问题时显示的文字（占位符），可以给图片指定高尺寸，但是可能导致图片变形。文件路径有相对路径和绝对路径两种。
例如：
<img src="https://img1.baidu.com/it/u=1919509102,1927615551&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500" alt="View" width="240" height="135">

<br>表格table：
使用\<table>\</table>，<tr>表示行, <td>表示行中的单元, <th>是表头的单元，例如：
<table>
  <tr>
    <th>这是表头的单元</th>
  </tr>
  <tr>
    <td>这是行中的单元</td>
  </tr>
</table>

<br>列表list：
分为有序列表和无序列表，无序列表使用\<ul>标签，默认使用实心圆点作为每项的标志，其它的标志可以是空心圆circle，实心方块square以及不出现标志，有序列表使用\<ol>标签，默认使用数字作为每项的标志，其它的标志可以是大写字母A，小写字母a，罗马字母i等。例如：
无序列表：
<ul type="square">
  <li>111</li>
  <li>222</li>
  <li>333</li>
</ul>

有序列表：
<ol type="A">
  <li>111</li>
  <li>222</li>
  <li>333</li>
</ol>

<br>表单：
表单用于收集用户的输入信息。
HTML表单表示文档中的一个区域，此区域包含交互控件，将用户收集到的信息发送到 Web 服务器。表单是一个包含表单元素的区域。表单元素是允许用户在表单中输入内容，比如：文本域（textarea）、下拉列表（select）、单选框（radio-buttons）、复选框（checkbox）等等。类型定义有多种，例如文本域text，密码字段password，单选按钮radio，复选框checkbox，提交按钮submit等。例如：
<form action="">
用户名: 
<br><input type="text" name="user"><br>
密码: 
<br><input type="password" name="password">

性别：
<br><input type="radio" name="sex" value="male">男<br>
<br><input type="radio" name="sex" value="female">女

拥有的设备：
<br><input type="checkbox" name="equipment" value="computer">电脑<br>
<br><input type="checkbox" name="equipment" value="phone">手机<br>
<br><input type="checkbox" name="equipment" value="pad">平板电脑

<input type="submit" value="提交">
</form>

<br>区块元素与内联元素：
区块元素在浏览器显示时，通常会以新行来开始和结束。如：\<h1>, \<pre>, \<ul>, \<table>，\<div> 等。
例如：
<h2>区块元素</h2>
<div>Hello</div>
<div>World</div>
<p>!</p>

<br>内联元素相反，他们总是一个接一个进行显示，不会新起一行。如： \<span>, \<input>, \<td>, \<a>, \<img>等。
例如：
<h3>下面的元素将在一行中显示</h3>
<span>姓名：</span>
<input name="username">
<span>风景</span>
<a href="https://baidu.com">百度一下</a>
<img src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.jj20.com%2Fup%2Fallimg%2F4k%2Fs%2F02%2F2109242259192W5-0-lp.jpg&refer=http%3A%2F%2Fimg.jj20.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1658021598&t=7985f6e4e680a1057b67044d4b3be2ca" width="360" height="150">
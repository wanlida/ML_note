http://www.w3chtml.com/css3/properties/background/background.html

css的插入方式

1. 链接外部样式表
 <head>
<link rel=stylesheet type=text/css href=slstyle.css>
</head>

2. 内部样式表
<head>
<style type="text/css">
<!--
body {
margin-left:0px;
margin-top:0px;
margin-top:0px;
margin-bottom:0px;
}
.style1 {
color:#fbe334;
font-size:13px;
}
-->
</style>
</head>

3. 内嵌样式表
<table style=color:red;margin-right:220px;>
这是个表格
</table>


常用a标签的伪类选择器
a:link{ color: #ff0000;text-decoration: none; }
a:visited{color: #00ff00;text-decoration: none;}
a:hover{color: #ff00ff;text-decoration: underline;}
a:active{color: #0000ff;text-decoration: underline;}
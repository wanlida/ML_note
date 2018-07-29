* 课程回顾：
	* HTML语言
		* HTML的简介	超文本标记语言。
		* 是网页最基础的语言。
		* 都是由标签所组成的。
		
		* HTML的基本格式
			<html>
				<head>
					属性信息，辅助性的信息
					引入外部的文件（css、js）
					先加载
				</head>
				<body>
					真正的数据内容（展示用户的数据）
				</body>
			</html>
		
		* HTML的规范
		
		* HTML的标签
			* 排版标签
				* <br />	换行
				* &nbsp;	空格
				* <hr />	水平线
				
				* <p></p>	段落标签
				
				* <div></div>
				* <span></span>
				
			* 字体标签
				* <font></font>
					* color：颜色
					* size：字体的大小
						* 最大值：7	最小值是1
					* face：字体的类型
				
				* 标题的标签
					<h1></h1>
					<h6></h6>
					
				* 粗体标签	斜体标签
				
				* 特殊字符
					<	&lt;
					>	&gt;
					&	&amp;
					
			* 列表标签
				<dl>
					<dt></dt>
					<dd></dd>
				</dl>
				
				有序列表和无序列表
					有序：
						<ol type="a" start="3">
							<li></li>
						</ol>
					无序：
						<ul type="">
							<li></li>
						</ul>
						
			* 图片标签
				<img src="图片的地址" width=""  height="" alt="图片的说明文字">
				
			* 超链接的标签
				<a></a>
				* 链接资源
					通过href=""
						* 访问网络的资源：http://www.baidu.com
						* 默认file文件的协议
						* 支持自定义的协议
						
				* 定位资源
					* 通过name	定义锚点
						* 返回需要使用href="#锚点的名称"
						
			* 表格标签
				<table border="1" width="" height="" >	：声明表格的范围
					<caption></caption> ：表格标题标签
					<tr align="中间显示文字对齐方式"> ：行
						<th></th> ：单元格
							* 默认居中和加粗
					</tr>
					<tr>
						<td></td> ：单元格
							* 行合并：rowspan="2"
							* 列合并：colspan="2"
					</tr>
				</table>
				
			* 表单标签
				<form action="表单提交地址" method="提交方式" >
					* 表单的提交方式？
						* 最常用的两种，get和post
						* 区别：
							* get方式将参数列表显示在地址栏上，post不会，参数封装到请求体中。
							* get方式安全级别较低，post较高。
							* get方式不支持大数据，post支持大数据。
							
						* 输入项
							<input type="text" name="username" >	文本框
							<input type="password" name="password" /> 密码框
							<input	type="radio" name="sex" value="0" checked="checked" />男
							<input type="checkbox" name="love" value="0" />篮球
							
							<input type="file" name="myfile" />	上传文件
							<input type="hidden" name="userId" value="001" />隐藏组件
							<input type="button" value="我是按钮" />
							<input type="image" src="引入一张图片" > 提交
							
							<select name="city">
								<option value="bj">数据</option>
							</select>
							
							<textarea rows="10" cols="10" name="desc"></textarea>
							
							<input type="reset" value="重置" />
							<input type="submit" value="提交" />
				</form>
				
			* 框架标签
				<frameset rows="150,*" >
					<frame src="链接html" name="top">
					<frame src="链接html" name="left">
				</frameset>
				
				
==========================================================================================================

* 今天的课程内容：
	* CSS
		* CSS的简介
			* CSS：cascading style sheet	：层叠样式表。
			* 做什么用：设置网页的显示效果（设置样式）。		
			* CSS将网页显示的效果和内容分离。（耦合性）
				
				超<font>文本</font>标签语言
				
			* HTML只需要把文本内容封装起来，不用属性，用CSS的代码来控制显示效果。
			* 如果开发了多套CSS的代码，都不用修改HTML的代码。
				
		* CSS和HTML的结合（*****）
			* CSS与HTML的结合方式（4种）
			* 在html的标签上，提供了一个(属性)，style="CSS的代码"
			* 在HTML的文件，提供了一个(标签)	<style type="text/css">CSS的代码</style>，这个标签放在<head></head>的中间
			
			* 引入外部的文件的方式（引入CSS的文件，定义一个css文件（后缀名名  demo.css））（经常使用的方式）
				* @import url("CSS文件的地址");	 属性必须要写<style></style>内部。大写和小写都没有问题。（注意：必须有;）
				
			* 引入外部文件的方式，通过一个<link>		写在<head></head>中间， 不要放在<style>中间（经常使用）
				* rel：代表当前和引入文件之间的关系
				* type：
				* href：引入CSS文件的地址
				
				
		* CSS的优先级（*****）和规范
			* 从上到下，由外到内，优先级是从低到高的。（一般情况下）（*****）
			* 标签名选择器 < 类选择器 < ID选择器 < style属性	（特殊情况下）（*****）
			
			* 规范
				* CSS的写法：	div{CSS的属性名:值;CSS的属性名:值;...}
				* 如果一个属性有多个值，值与值之间使用空格隔开
					* 例子 div{ xx:yy zz aa }
							
			
		* CSS的选择器（*****）
			* CSS的选择器
				* 告诉CSS的代码作用在哪个标签上。
					* 基本选择器
						* 标签名选择器		div{}	span{}
						* 类选择器：在HTML的标签上，提供了属性	class，定位到div的标签（美工经常使用的方式）
							* 写法：	.class的名称	(.hehe{CSS的代码})
							* 设置不同的标签，具有相同的样式
							
						* ID选择器
							* 在HTML的标签上，提供的属性 设置样式
								* 写法：	#id的名称	(#haha{CSS的代码})
							* 一般情况下：设置不同的ID
								* 一般情况下给js语言来使用。
								
					* 扩展选择器
						* 关联选择器：标签可以嵌套，标签与标签之间的关系。
							* 写法：	中间用空格隔开	例子（div font{CSS的代码}）
							
						* 组合选择器：对多个不同的选择器进行相同的样式
							* 写法：在多个不同的选择器之间用 ,	隔开
							
						* 伪元素选择器：	定义好的一些选择器，用就ok。
							* 如果使用超链接伪元素选择器：使用顺序：	L V H A
						
						
		* CSS的布局（了解）（CSS+DIV进行布局）
			<div>
				<div>
					<img />
				</div>
				<div>
					<font>领导很忙</font>
				</div>
			</div>
			
			
	* JAVASCRIPT（JavaScript简写js，文件的后缀名也是  demo.js）（*****）
		* javascript的简介
			* js是基于对象和事件驱动的脚本语言，作用在客户端（浏览器）上。
			* js的特点：
				* 交互性
				* 安全性：（不可以访问本地的硬盘）
				* 跨平台性：因为浏览器就可以解析js的文件。
				
				
		* javascript和java不同（一点关系没有）（雷锋和雷峰塔）
			* Netscape（网景），静态的效果。livescript（javascript的前身）
			* java诞生了，升级了，改名（javascript），火了。
			* 巨头：自己开发一套（jscript）
			* 找一些公司推出的标准：	SUN	微软	ECMA（欧洲计算机制造协会），联合推出现在的标准。
			
			* ECMAScript：标准。基础上扩展。
			
			* js的基于对象，java是面向对象。
			* js解析就可以执行，java先编译再执行。
			* js是弱类型的语言，java是强类型语言。
			
		* javascript语言的组成
			* ECMAScript	标准（js的语法，变量，函数）
			* BOM			（Browser Object Model）	浏览器对象模型
			* DOM			（Document Object Model）	文档对象模型			
			
			
		* javascript的语法
			* 把js和HTML的结合一起。（2两种方式）
				* js和HTML的结合
					* HTML的文件提供了一个标签	<script type="text/javascript">js的代码</script>，标签可以放在HTML文件的任意位置上。
					
					* 引入外部的文件，有一个外部的文件。编写js文件。
						* <script src="引入js文件（相对路径）" >
						* 如果script通过src的属性引入了外部的文件，里面的js代码就不会执行了。（*****）
						
					* </script>，标签可以放在HTML文件的任意位置上。
				
				
			* 关键字
				* var	声明变量
				
			* 标示符
				* 和java一样
				
			* 注释
				* 和java一样
				
			* 变量		
				* 声明变量，只使用一个关键字	var num = 12;  var str = "abc"; 
				* 5种基本数据类型
					* Undefined、Null、Boolean、Number 和 String 
					
					* 5种基本数据类型
					* Undefined、Null、Boolean、Number 和 String 
					
					* String		字符串类型
						* js中双引号和单引号都代表的是字符串
					* Number		数字类型
						* 不区分整数和小数
					* Boolean		布尔类型
					* Null			空，给引用赋值的
					* Undefined		未定义（声明变量，没有赋值）
					
					* 声明变量，使用var关键字	
					* typeof() 判断当前变量是什么类型的数据
					
			* 运算符
				* js的运算符
					* 算术运算符
						* 0或者null是false，非0或者非null是true，默认用1表示。
						var num = 3710;
						alert(num/1000*1000);
							* 不区分整数和小数
					* 赋值运算符
						* 和java是一样的
					* 比较运算符
						* ==	比较值是否相同
						* ===	比较值和类型是否相同
					* 逻辑运算符
						* 和java中一样
					
					* 三元运算符
						条件?值1:值2
					
					
			* js的数组
				* js的数组
				* java	String [] str = {};
				* 声明数组
					* var arr = [12,34,55];
					* var arr = new Array(5);		声明数组，长度是5
					* var arr = new Array(2,3,4);	声明数组，元素是2 3 4
					
				* 数组的属性
					* 长度：length
					* 数组的长度是可变的。
					
					
			* js的方法
				* java中	public String 方法名称(参数列表(int num,String str)){
								方法体;
								return null;
							}
							
				* js中，通过关键字function	声明方法。
					
					function 方法名称(参数列表 (num,str)){
						方法体;
						return;
					}
					
					* 参数列表：不能使用var关键字
					* 返回值：可写可不写的，如果有写返回值，如果没有，返回值可以省略不写。
					
				* 调用执行。	
				
				* 在函数的内部，有一个数组，装传过来的参数的
					arguments
				
				
		* javascript的对象和API
		
		* BOM	浏览器对象模型
		
		* DOM	文档对象模型
		
		

































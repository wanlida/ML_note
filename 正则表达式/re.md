## 正则表达式  

直接写
半方大的空白&ensp;或&#8194;
全方大的空白&emsp;或&#8195;
不断行的空白格&nbsp;或&#160;
 匹配任意字符  


---
正则表达式中，特殊字母（或字符集合）用来给出要搜索的东西。  
.字符（英语句号）可以匹配到任何一个单个的字符。
---  

-**文本**   

<code>
	sales1.xls  
	orders3.xls  
	sales2.xls
</code>  

-**正则表达式**  

<code>
	sales.
</code>     

-**结果**    
<code>
	***sales1***.xls  
	orders3.xls  
	<u>***sales2***</u>.xls
</code>     

----------
\\.的用途
---  

-**文本**   

<code>
	sales1.xls  
	orders3.xls  
	sales2.xls  
	na1.xls  
	na2.xls  
	sa1.xls
</code>  

-**正则表达式**  

<code>
	sales\\.xls
</code>     

-**结果**    
<code>
	sales1.xls  
	orders3.xls    
	sales2.xls  
	<u>***na1.xls  
	na2.xls  
	sa1.xls***</u>
</code>     

----------

匹配多个字符中的某一个
---  

-**文本**   

<code>
	The phrase "regular expression" is often abbreviated as RegEx or regex
</code>  

-**正则表达式**  

<code>
	[Rr]eg[Ee]x
</code>     

-**结果**    
<code>
	The phrase "regular expression" is often abbreviated as <u>**RegEx**</u> or <u>**regex**</u>
</code>     


----------
甚至可以匹配范围字符
---
-A-Z, 匹配从A到Z的所有大写字母
-a-Z，从匹配从A到Z所有小写字母
-A-f, 匹配从A到F的所有大写字母
-A-z，匹配从ASCII字符A到ASCII字符z的所有字母

---
##匹配空白字符    

元字符	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  说明  

[\b]	    &#8195;&#8195;&#8195;&#8195;&#8195;  回退（并删除）一个字符（Backspace键）  
\f	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  换页符  
\n	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  换行符  
\r	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  回车符  
\t	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  制表符（Tab键）  
\v	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  垂直制表符  
 ---
##匹配数字（与非数字）   

元字符	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  说明  

[\b]	    &#8195;&#8195;&#8195;&#8195;&#8195;  回退（并删除）一个字符（Backspace键）  
\d	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  任何一个数字字符（等价于[0-9]）  
\D	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  任何一个非数字字符（等价于[^0-9]）  

  ---
##匹配字母与数字（与非字母和数字）
元字符	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  说明  

\w	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个字母数字字符（大小写均可）或下划线字符（等价于[a-zA-Z-9_]）  
\W	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  任何一个非字母数字或非下划线字符（等价于[^a-zA-Z0-9]）  

----------
##匹配空白字符（与非空白字符）
元字符	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  说明  

\w	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个字母数字字符（大小写均可）或下划线字符（等价于[a-zA-Z-9_]）  
\W	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  任何一个非字母数字或非下划线字符（等价于[^a-zA-Z0-9]）  

-----------

##十六进制或者八进制

&#8195;&#8195;在正则表达式中，十六进制（逢16进1）数值要用前缀\x来给出。  
比如说，\x0A对应于ASCII字符10（换行符），其效果等价于 \n

&#8195;&#8195;在正则表达式中，八进制（逢8进1）数值要用前缀\0来给出，数值本身可以是两位或者  
三位数字。比如说，\011对应于ASCII字符9（制表符），其效果等价于\t  

 --------------   
使用POSIX字符集  

字符类	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  说明  

[:alnum:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个字母或数字（等价于[a-zA-A0-9]）  
[:alpha:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个字母（等价于[a-zA-Z]）  
[:blank:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  空格或制表符（等价于[\t]）  
[:cntrl:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  ASCII控制字符（ASCII 0到31，再加上ASCII 127）  
[:digit:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个数字（等价于[0-9]）  
[:graph:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  和[:print:]一样，但不包括空格   
[:lower:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个小写字母（等价于[a-z]）  
[:print:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个可打印字符  
[:punct:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  既不属于[:alnum:]也不属于[:contrl:]的任何一个字符  
[:space:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个空白字符，包括（等价于[^\f\n\r\t\v]）  
[:upper:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个大写字母（等价于[A-Z]）  
[:xdigit:]	    &#8195;&#8195;&#8195;&#8195;&#8195;  任何一个十六进制数字（等价于[a-fA-F0-9]）    



-**文本**   

<code>
	<BODY BGCOLOR="#336633" TEXT="#FFFFFF"  
			MARGINWIDTH="0" MARGINHEIGHT="0"
			TOPMARGIN="0"	LEFTMARGIN="0"\>
</code>  

-**正则表达式**  

<code>
	#[[:xdigit:]][[:xdigit:]][[:xdigit:]][[:xdigit:]][[:xdigit:]][[:xdigit:]]
</code>     

-**结果**    
<code>
	<BODY BGCOLOR="<u>#336633</u>" TEXT="<u>#FFFFFF</u>"  
			MARGINWIDTH="0" MARGINHEIGHT="0"
			TOPMARGIN="0"	LEFTMARGIN="0"\>
</code>   

---------  

\w可以匹配所有的字母和数字字符（以及下划线）
想要匹配同一个字符（或字符集合）的多次重复，只要简单地给这个字符（或字符集合）加上一个+字符作为后缀就行了。+匹配一个或更多字符（至少一个；不匹配零个字符的情况）。  

-**文本**   

<code>
	Send personal email to ben@forta.com or ben.forta@forta.com. For question   
	about a book use support@forta.com. If your message is urgent try  
	 ben@urgent.forta.com. Feel free to send unsolicited email to spam@forta.com  
 		(wouldn't it be nice if it were that simple, huh?).  

</code>  

-**正则表达式**  

<code>
	[\w.]+@[\w.]+\.\w+
</code>     

-**结果**    
<code>
	Send personal email to <u>ben@forta.com</u> or <u>ben.forta@forta.com</u>. For question   
	about a book use <u>support@forta.com</u>. If your message is urgent try  
	 <u>ben@urgent.forta.com</u>. Feel free to send unsolicited email to <u>spam@forta.com</u>  
 		(wouldn't it be nice if it were that simple, huh?).  
</code>   
-------------------  
##匹配零个或多个字符
+匹配一个字符或多个字符，但不匹配零个字符，+最少也要匹配一个字符。
\*的用法与+完全一样，只要把它放在一个字符（或一个字符集合）的后面，就可以匹配该字符（或字符集合）连续出现零次货多次的情况。比如，模式和B.\*Forta将匹配B Forta 、 B. Forta 、 Ben Forta和其他有类似规律的组合。   

-**文本**     

<code>
Hello .ben@forta.com is my email address

</code>  

-**正则表达式**  

<code>
	[\w.]+@[\w.]+\.\w+
</code>     

-**结果**      

<code>
Hello <u>.ben@forta.com</u> is my email address
</code>   
---
-**文本**     

<code>
Hello .ben@forta.com is my email address

</code>  

-**正则表达式**  

<code>
	\w+[\w.]*@[\w.]+\.\w+
</code>     

-**结果**      

<code>
Hello .<u>ben@forta.com</u> is my email address
</code>    

---------    

##匹配一个或零个字符  

-**文本**     

<code>
The URL is http://www.forta.com/, to connect
securely use https://www.forta.com/ instead.
</code>  

-**正则表达式**  

<code>
	http?://[\w./]+
</code>     

-**结果**      

<code>
The URL is <u>http://www.forta.com/</u>, to connect
securely use <u>https://www.forta.com/</u> instead.
</code>    

-**分析**  
？在这的含义是：我掐面的字符（s）要么不出现，要么最多出现一次。  
即，https?://既可以匹配到  http://  也可以匹配到 https://

------
##匹配的重复次数  

{3}意味着重复了三次  
{1，3}意味着重复1~3次  
{1，}意味着重复至少1次  

---------------  

##防止过度匹配  


贪婪型元字符	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  懒惰型元字符   

\*	  &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;     \*?   
\+	    &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;   \+?  
{n,}  	  &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;       {n,}?  

---  

-**文本**     

<code>
	This offer is not available to customers  
	living in <B\>AK</B\> and <B\>HI</B\>
</code>  

-**正则表达式**  

<code>
	<[Bb]>.*</[Bb]>
</code>     

-**结果**      

<code>
	This offer is not available to customers  
	living in <u><B\>AK</B\> and <B\>HI</B\></u>
</code>    
---

-**文本**     

<code>
	This offer is not available to customers  
	living in <B\>AK</B\> and <B\>HI</B\>
</code>  

-**正则表达式**  

<code>
	<[Bb]>.*?</[Bb]>
</code>     

-**结果**      

<code>
	This offer is not available to customers  
	living in <u><B\>AK</B\></u> and <u><B\>HI</B\></u>
</code>    
 -------

##单词边界   

b-boundary(边界)

-**文本**     

<code>
	The cat scattered his food all over the room
</code>  

-**正则表达式**  

<code>
	\bcat\b
</code>     

-**结果**      

<code>
	The <u>cat</u> scattered his food all over the room
</code>  

---

-**文本**     

<code>
	The captain wore his cap and cape proudly as he sat listening to the recap of  
	 how  his crew save the men from a capsized vessel.
</code>  

-**正则表达式**  

<code>
	\bcap
</code>     

-**结果**      

<code>
	The <u>cap</u>tain wore his <u>cap</u> and <u>cap</u>e proudly as he sat listening to the recap of  
	 how  his crew save the men from a <u>cap</u>sized vessel.
</code>
---
-**文本**     

<code>
	The captain wore his cap and cape proudly as he sat listening to the recap of  
	 how  his crew save the men from a capsized vessel.
</code>  

-**正则表达式**  

<code>
	cap\b
</code>     

-**结果**      

<code>
	The captain wore his <u>cap</u> and cape proudly as he sat listening to the recap of  
	 how  his crew save the men from a capsized vessel.
</code>

------
##字符串边界

&#8195;&#8195;用来定义字符串边界的元字符有两个：一个是用来定义字符串开头的 ^ ，另一个是用来定义字符串结尾的$。  

-**正则表达式**  

<code>
	</[Hh][Tt][Mm][Ll]>\s*$
</code>     

-**分析**      

<code>
	我们用了4个字符集合来分别匹配H、T、M、L等4个字符（这样就可以对着几个字符的各种大小写组合形  
	式进行处理了），\s*$匹配一个字符串结尾处的零个字符或多个空白字符
</code>

-------
##分行匹配模式
&#8195;&#8195;有许多正则表达式都支持使用一些特殊的元字符去改变另一些元字符行为的做法，用来启用  
分行匹配模式（multiline mode）的（？m）几号就是一个能够改变其他元字符行为的元字符序列。  
分行匹配模式将使得正则表达式引擎把分隔符当作一个字符串分隔符来对待。在分行匹配模式下，  
^不仅匹配正常的字符串开头，还将匹配行分隔符（换行符）后面的开始位置（这个位置是不可见  
的）；类似的，$不仅匹配正常的字符串结尾，还将匹配行分隔符（换行符）后面的结束位置。  
&#8195;&#8195; 在使用时，（？m）必须出现在整个模式的最前面。

-------

##回溯引用：前后一致匹配
-**文本**     

<code>
	<BODY\>
	<H1\>Welcometo my Homepage</H1\>  
Content is divided into two sections:<BR>
<H2\>ColdFusion</H2\>  
Information about Macromedia ColdFusion.  
<H2\>Wireless</H2\>  
Information about Bluetooth,802.11,and more.  
<H2\>This is not valid HTML</H2\>
	</BODY\>
</code>  

-**正则表达式**  

<code>
	<[Hh]([1-6])>.*?</[Hh]\1>
</code>     

-**结果**      

<code>
<BODY\>  
	<u><H1\>Welcometo my Homepage</H1\></u>  
	Content is divided into two sections:<BR>
	<u><H2\>ColdFusion</H2\></u>  
	Information about Macromedia ColdFusion.  
	<u><H2\>Wireless</H2\></u>  
	Information about Bluetooth,802.11,and more.  
	<H2\>This is not valid HTML</H2\>  
</BODY\>
</code>

------
用来大小写转换的元字符

元字符	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;  说明  

\E	  &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;    结束\L或\U转换   
\l	    &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;   把下一个字符转换为小写  
\L  	  &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;
把\L到\E之间的字符全部转换为小写  
\u	    &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;   把下一个字符转换为大写  
\U  	  &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;
把\U到\E之间的字符全部转换为大写
 ---
 -**文本**     

<code>
	<BODY\>
	<H1\>Welcometo my Homepage</H1\>  
Content is divided into two sections:<BR>
<H2\>ColdFusion</H2\>  
Information about Macromedia ColdFusion.  
<H2\>Wireless</H2\>  
Information about Bluetooth,802.11,and more.  
<H2\>This is not valid HTML</H3\>
	</BODY\>
</code>  

-**正则表达式**  

<code>
	(<[Hh]1>)(.*?)(</[Hh]1>)
</code>     
-**替换**  

<code>
	$1\U$2\E$3
</code>     

-**结果**      

<code>
	<BODY\>
	<H1\>WELCOME TO MY HOMEPAGE</H1\>  
Content is divided into two sections:<BR>
<H2\>ColdFusion</H2\>  
Information about Macromedia ColdFusion.  
<H2\>Wireless</H2\>  
Information about Bluetooth,802.11,and more.  
<H2\>This is not valid HTML</H3\>
	</BODY\>
</code>  

--------
##各种前后查找操作符
操作符	&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;   说明  

（？=）	  &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;    正向前查找   
（？！）    &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;   负向前查找   
（？<=）	  &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;    正向后查找   
（？<！）    &#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;   负向后查找   

---  

##嵌入条件  

用来定义这种条件的语法是（？（backreference）true——regex），其中？表明这是一个条  
件，括号里的backreference是一个回溯引用，true——regex是一个只在backreference存在  
时才会被执行的子表达式。
  -**文本**     

<code>
<!-- Nav bar --\>  
<TD\>  
<A HREF="/home"\><IMG SRC="/images/home.gif"\></A\>  
<IMG SRC="/images/spacer.gif"\>  
<A HREF="/search"\><IMG SRC="/images/search.gif"\></A\>  
<IMG SRC="/images/spacer.gif"\>  
<A HREF="/help"\><IMG SRC="/images/help.gif"\></A\>  
</TD\>  

-**正则表达式**  

<code>
(<[Aa]\s+[^>]+>\s\*)?<[Ii][Mm][Gg]\s+[^>]+>(?(1)\s*</[Aa]>)
</code>  

-**替换**  

<code>
	$1\U$2\E$3
</code>     

-**结果**      

<code>
<!-- Nav bar --\>  
<TD\>  
<u><A HREF="/home"\><IMG SRC="/images/home.gif"\></A\></u>  
<u><IMG SRC="/images/spacer.gif"\></u>  
<u><A HREF="/search"\><IMG SRC="/images/search.gif"\></A\></u>  
<u><IMG SRC="/images/spacer.gif"\></u>  
<u><A HREF="/help"\><IMG SRC="/images/help.gif"\></A\></u>  
</TD\>    

-------
##常见应用软件和编程语言中的正则表达式

JavaScript

JavaScript 1.x版本在String和RegEx对象的以下集合方法里实现了正则表达式处理  
exec： 一个用来搜索一个匹配的RegEx方法  
match：一个用来匹配一个字符串的String方法  
replace： 一个用力啊完成替换操作的String方法  
search：一个用来测试在某给定字符串里是否存在着一个匹配的String方法  
split：一个用来把一个字符串拆分为多个子串的String方法  
test：一个用来测试在某给定字符串里是否岑仔着一个匹配的RegEx方法  

JavaScript对正则表达式的支持源自Perl语言，但需要注意以下几个问题：
JavaScript使用命令行选项来管理全局的区分大小写搜索：g选项激活全局搜索功能，i选项让匹配操作不区分字母大小写，这两个选项可以组合为gi。  
其他命令行选项（版本4及以后的浏览器支持）包括：m，支持多行字符串；s，支持单行字符串；x，忽略正则表达式模式里的空白字符。  
在使用回溯引用的时候，$'将返回被匹配字符串前面的所有东西，$`将返回被匹配字符串后面的所有东西，$+将返回最后一个被匹配的子表达式，$&将返回被匹配到的所有东西。  
JavaScript提供了一个名为RegExp的全局对象，在执行完一个正则表达式之后，你们可以通过对这个对象获得与这次执行有关的信息。
JavaScript不支持POSIX字符类   
JavaScript不支持\A\和Z。  

MySQL  
MySQL是一个流行的开源代码数据库软件。MySQL率先提供了正则表达式支持作为一种数据库搜索手段，这一点我们在其他数据库系统里面还没有见过。  
MySQL对正则表达式的支持体现允许在WHERE字句中使用如下格式的表达式：  
REGEXP "expression"  
下面是一条使用了正则表达式的MySQL语句的完整语法：  
SELECT *FROM table WHERE REGEXP "pattern"  
MySQL正则表达式支持很有用，功能也很强大，但它还算不上是一个完备的正则表达式实现。  
只提供了搜索支持，不支持使用正则表达式进行替换操作。  
在默认的情况下，正则表达式搜索不区分字母的大小写，如果要区分字母的大小写，必须增加一个BINARY关键字（放在REGEXP和模式之间）  
用[[:<:]]来匹配一个单词，用[[:<:]]来匹配一个单词的结束  
不支持向前于预测。   
不支持嵌入条件。  
不支持八进制字符搜索。  
不支持\a \b \e \f和\v。  
不支持回溯引用。  

sun java  
java对正则表达式的支持是从1.4版本开始的，此前的JRE（java runtime environment,java运行环境）版本不支持正则表达式。  
java语言中的正则表达式匹配功能主要是通过java.util.regex.matcher类和以下这些方法实现的。  
find():在一个字符串里寻找一个被顶模式的匹配。  
lookingAt():用一个给定的模式去尝试匹配一个完整的字符串。  
replaceAll（）：进行替换操作，对所有的匹配都进行替换。  
replaceFirst（）：进行替换操作，只对第一个匹配都进行替换。  
matcher类还提供了几个能让程序员对特定操作做出更加细致调控的方法。此外，java.util.regex.pattern类也提供了几个简单易用的包装器方法。   
compile():把一个正则表达式编译成一个模式。  
flags():返回某个定模式的匹配标志。  
matches():在功能上等价于刚才介绍的matchers（）方法。  
pattern（）：把一个模式还原为一个正则表达式。  
split（）：把一个字符串拆分为子字符串。  
sun公司发布的java正则表达式支持与perl语言基本兼容，但要哦注意以下几点：  
想要使用正则表达式，必须先用import java.util.regex.*语句导入正则表达式组件  
不支持嵌入条件  
不支持使用 \E \I \L \u 和 \U进行字母大小写转换。
不支持使用\b匹配退格符。  
不支持\z.

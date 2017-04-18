#JS阶段
	
##第一天JavaScript基础
	
	1,JavaScript历史(有过三足)
	
	2,JavaScript特点
		①浏览器的脚本语言,可以跟html代码混排
		②跨平台
		③安全性好
		④兼容性(谷歌火狐还好,IE不行)

	3,JavaScript目标
		到学习结束,有以下三个大目标:
		一:特效; 二表单验证 ;三Ajax;

	4,JavaScript语法
		 document.write();//向文档中输出文档流,使用要谨慎
		 console.log();//控制台输出日志 控制台进行打印
		
		/*
		js中语句以分号作为结束,如果省略分号,
		则由解析器来确定语句的结尾,一般情况下,换行会当成语句的结尾
		*/
					
		

		①使用场景
			js的代码错误需要调试工具查看
			
			①script标签
			(一般写在head下方 或者在body结束标签之前)
			
			②外部引入  
			(在有src属性的script标签中不能写js代码)
			
			③元素的事件属性
				可在元素的事件中书写script如在onclick中

			④a标签的href属性
			<a href="javascript:alert('a')">baidu</a>
			<a href="javascript:void(0)" onclick="alert('b')">taobao</a> 

		
		②变量声明
			使用var 定义变量
			虽然不使用var也可以定义变量,但是不推荐

			命名规则:
			字母数字下划线($),
			首字母不能为数字,
			严格区分大小写,
			且不能使用关键字 if else elseif this....
			(变量声明命名几乎适用于所有的语言)
			

		③注释和分隔符
			// /**/

		④数据类型
			(typeof() 获取数据类型)
			
			boolean布尔值
			string字符串
			number数字
				包括	:整型,浮点,NaN,科学技术法.
					(科学技术法
					var a = 5E2;//10的2次方*5
					var a = 5.21E9999;// Infinity 正无穷)
				
				NaN是一个特殊的数字类型 not a number
				NaN,要求要返回一个number类型值,但是返回不了,防止报错,返回NaN,类型是Number
				1,任何一个数值跟NaN进行运算得到的值 都是NaN
				2,任何数值跟NaN进行比较的时候 返回的结果都是false
				3,检测一个值是否为NaN的时候只能使用isNaN函数		


			object对象
				包括:
				new Object()对象
				new Array()数组
				null 空
		
			function函数
			undefined未定义

		⑤数据类型转换
			强制类型转化
				1,转化成数字
					parseInt
					如果是纯数字的话 则直接返回数字类型的值
					如果首字母是数字,则截取到第一个不是数字之前的数字返回
					如果首字母不是数字,返回NaN

					parseFloat
					规律同上;
					
					Number
					纯数字转化成数字 如果中间有非数字 则直接返回NaN
					true=>1   false => 0

				2,转化成字符串
					 String()  是一个函数 用来将其它类型的值转为字符串

					单双引号都不解析变量
					可以互相嵌套
					转义字符 单双引号都能解析转义字符
					在js中定义字符串不能随意换行

				3,转化成布尔类型 
					转化为假的七种情况
					false 0 0.0 '' NaN null undefined

			自动类型转化
				计算
					加号 一个特殊的运算符
					当一个字符串加上数字那么就是连接符,结果也是字符串
					当两个数字时则是加法运算
				if
	
		⑥运算符	
			算子赋比逻位他
		
	    7流程控制
			与php相同 但else  if中间一定要有空格
			if else,switch(case的值必须要全等于才可以匹配上)	
		⑧循环控制
			同php一样 
			for
			while(循环体中的代码一定要向着脱离条件的方法发展)
			continue
			break		
##第二天JavaScript函数和对象
	1,对象
		①声明方式
			new  Object()
			  例:var mm=new Object();
			
			{}  json格式  快速声明对象
			  注意:属性与值用:分割 多个成员之间用,分隔
			  例:var long={};
				推荐使用json方法!!!
			
			构造函数形式 创建对象
				例:function MeiNv(参数){}
				var a=new MeiNv(值);
			
			
		②元素(对象属性和方法)的操作方式
			 .  成员访问符
			[]当属性名存在与 一个变量中时,使用[]
			this 代表当前这个对象

		③对象的遍历
			for in
			例: for(var i in nana) //i 代表 属性名 方法名
			 {
	 			console.log(nana[i]);
			 }

		④with简便操作
			格式:
				with(对象)
				{
					console.log(成员);
				}


	2,函数
		
		①函数的声明方式
			1,function  (推荐)
				例:
				function 方法名(){}
				可在声明前后调用
			2,匿名函数    (推荐)
			    例:
				var love=function(){}
				不能在声明之前调用
			3,Function构造函数方式
				例:
				var a=new Function();
			   不能在声明之前调用
				
	
		②函数的调用
			1,代码中直接调用
			2,事件触发
			3,赋值给一个变量
			4,a链接
		
		③注意事项
			1,优先级
				定义变量时,不能函数名冲突 否则会覆盖函数			
			2,参数
				如果有形参,但是没有传递,可以执行,但是参数值为undefined
				如果少传参数,没有传递的参数值为undefined
				如果多传参数,那么多余的参数会被"忽略","抛弃"

				不要给形参设置默认值,ie不兼容
				获取函数的参数	arguments
			
			3,返回值
				如果不使用return返回一个值的话 那么函数的默认返回值是undefined
				可以返回一个函数

		④作用域	
			变量作用域以及函数作用域
				川哥总结:
				在脚本中使用var定义的变量叫做 全局变量,在函数内及子函数中都可以使用
				在函数中使用var定义的变量叫做 局部变量,只能在当前函数及子函数中使用
				
				!!!如果在函数中不使用var定义变量默认作为全局变量

				自己总结: 除了在函数内部用 var 定义的变量时局部变量  其余,全部都是全局变量
					
				函数作用域,
				在脚本中直接定义的函数,称为 全局函数,都可以使用
				在函数内部定义的子函数,称为 局部函数,只能在当前函数中(当前代码块)使用
##第三天JavaScript内置对象
	1,String
		①创建字符串对象
		 var str = new String('iloveyoutosimida');
		(数据类型是对象,而表示的内容是字符串)
		
		②属性常用 :length
		属性 length 长度 获取字符串长度
			例: var r = str.length;

		③常用方法
			trim() 清空两侧的空白
			charAt()  获取指定位置上的字符
			indexOf 获取指定字符或者字符串首次出现的位置
			lastIndexOf 获取指定字符或者字符串最后一次出现的位置
			(indexOf 和 lastIndexOf这两种方法,在查找不到字符串或字符时 返回 -1)
			concat()  连接两个或者多个字符串
			slice()和substring() 截取字符串 从start到end 要前不要后
			split()  按照指定字符或者字符串来拆分字符串
			str.substr() 截取字符串
			toLowerCase() 将字符串变成小写
			toUpperCase() 将字符串变成大写
			replace()替换(注意str_replace第一个参数不能为正则表达式)
					
	2,Array
		①声明方式
			1,new Array()
			  例:
			   var arr = new Array();//空数组
		       var arr = new Array(1,2,3,4,5);
		       var arr = new Array(5);//定义数组的元素个数,元素的值为undefined
			2,[]
			  例:
				var arr = [5];//定义第一个数组元素 5
				数组中的值可以是任意类型
				 var arr = [1,'abc',true,function(){},undefined,null,new Object(),NaN];

		②常用属性length
			常用属性 获取数组元素个数
			例:var len = arr.length;

		③注意点
			1,不支持[]的形式添加成员,(除非指定下标)
				例:  arr[] = 'miss';
			2,不支持关联数组,只支持索引数组; 
				例: arr['abc'] = 'abcdef';//给对象添加属性
				    alert(arr['abc']);//获取对象的属性
			3,二维数组
				例:
				var arr = [];
				arr[2] = [];//如果向直接使用多维数组,先把前面的元素定义为数组
				arr[2][3] = 300;//不能直接定义多维数组
			4,索引连续
				例: var arr = [];
					arr[100] = 'abc';
				(就算是定义第一百个下标的值是abc那么前面的索引依旧是0-99只是值是undefined)
		④元素的增删改 访问
			 1,splice  删除,替换,添加(常用推荐)
			 例:
			var res = arr.splice(2,3);//从哪个下标开始,删除几个
		 	var res = arr.splice(2,3,'a','b');//从哪个下标开始,删除几个,替换的值
			var res = arr.splice(2,3,'a','b','c','d','e');//从哪个下标开始,删除几个,替换的值
			
			2,添加操作
			
			例:
			arr[10] = 44;//必须要有下标, 没有下标,会报错
				
			用常用方法进行添加:
			例:
			//从数组尾部压入元素
			var res = arr.push(55);//返回数组元素个数
			arr[arr.length] = 66;
			//从数组头部压入元素
			var res = arr.unshift(0);//返回数组元素个数
			
			3,删除操作
			
			//删除的时元素的值,值变成undefined
			delete arr[2];

			用常用方法进行删除:
			例:
			//删除并返回数组中最后一个元素
			var res = arr.pop();
			//删除并返回数组中第一个元素
			var res = arr.shift();
		⑤数组的遍历(根据情况需求使用两种方法)
			1,for (推荐)
			例:
			for (var i = 0; i < arr.length; i++) {
				console.log(arr[i]);
			}

			2,for in(不推荐)
			如果元素的值为undefined,遍历时会'过滤' 跳过
			例:
			
			for(var i in arr)
			{
				console.log(arr[i]);
			}
		⑥常用方法
			concat()连接两个或者多个数组,返回一个新数组
			join()使用特定字符串连接数组
			reverse()反转 颠倒数组中的元素
			slice() 返回数组中的一部分
			sort() 将数组元素排序
			splice() 删除、替换或插入数组元素
			push 在数组尾部添加元素
			unshift在数组头部添加元素
			pop    删除并返回数组的最后一个元素
			shift 删除并返回数组的第一个元素
	
			
	3,RegExp(正则表达式)
	正则表达式使用单个字符串来描述、匹配一系列符合某个句法规则的字符串,正则表达式通常被用来检索、替换那些符合某个模式的文本

		①声明方式
			new RegExp();
			//
	
		②分隔符
			//

		③普通字符
		
		④转义字符
			\w  \W  \d  \D  \s  \S  \t
			例:
			var reg = /\w/;//单个字母数字下划线
			var reg = /\W/;//单个非字母数字下划线
			var reg = /\d/;//单个数字
			var reg = /\D/;//单个非数字
			var reg = /\s/;//单个空白字符
			var reg = /\S/;//单个非空白字符
			var reg = /\t/;//单个制表符 tab键

		⑤元字符
			.  *  +  ?  {}  []  ()  |  ^  $
			例:
			var reg = /./;//除了换行符之外的任何单个字符
			var reg = /z*/;//匹配0次或多次
			var reg = /z+/;//匹配至少1次或多次
			var reg = /z+?/;//禁止贪婪
			var reg = /\w{5}/;//限制匹配次数
			var reg = /\w{5,10}/;//限制匹配次数 5到10次
			var reg = /[a-zA-Z0-9_]/;//限制范围
			var reg = /z(love)z/;//子组
			var reg = /abc|def|123/;//或
		
			//限制用户名
			var str = 'asdsadUser1ayyhhduUser2saadhd';
			// var reg = /^\w{8,18}$/;

		⑥模式修饰符
			i  g
			例:
			//修饰符 i 不区分大小写  g
			// var reg = /user\d/i;
			var reg = /user\d/ig;//g 全局匹配 一般配合字符串的match来使用
			//match  字符串的方法
			var res2 = str.match(reg);

		两种方法test exec
			例:
			// var res = reg.test(str);//返回布尔类型的值
			var res1 = reg.exec(str);//匹配.如果匹配到,返回匹配到的数组
			(多个的话只返回回最后匹配到的,想要都返回str.match(reg);),如果不存在返回 null
			

	4,Math(数学对象)
		方法:
			round  四舍五入
			max  获取最大值
			min  获取最小值
			abs  获取绝对值
			floor  退一取整
			ceil  进一取整
			pow  幂运算
			sqrt  开方运算
			random  获取一个随机数(0-1之间的随机小数有可能是0,决不可能是1)
		扩展:
			获取一个从m到n的随机整数 (n-m+1)+m
			function rand(m,n)
			{
				return Math.floor(Math.random()*(n-m+1))+m;
			}
	5,Date(时间)
		初始化:
			当前时间:date();			
			特定时间:
		常用方法:
			getFullYear()获取4位数的年
			getMonth() 获取月份(0-11),月份的索引是从0开始,所以要获取当前月份得+1
			getDate()获取天数
			getHours()获取小时
			getMinutes()获取分钟
			getSeconds()获取秒数
			getDay()获取星期

##第四天第五天JS事件
	1,事件的定义
		当对文档中的元素进行操作的时候或者文档的状态发生改变的时候会产生一个事件

	2,事件的三要素
		①事件源
		②事件类型
		③事件的处理程序

	3,准备知识
		①document.getElementById
		②document.getElementsByTagName
		③innerHTML(获取双标签中的值)
		style(修改样式,只能对行内样式进行操作;若有双拼词,把横杠去掉,后面单词首字母大写)	
		例	:time.style.textAlign = 'center';

	4,绑定事件
		①html元素事件属性 	例:onclick="func()"
		②元素对象的事件属性
			例:var one = document.getElementById('one');
			one.onclick = function(){}
		③addEventListener(添加事件监听 低版本ie不兼容) 
		attachEvent(针对低版本ie浏览器)

	5,事件的分类
		①文档事件 
			onload文档加载完毕事件
			onunload当文档在关闭时触发的事件 针对低版本ie浏览器
			onbeforeunload当前页面在关闭时触发的事件
			//不能alert 只能return  火狐中 此页面要求您确认想要离开 - 您输入的数据可能不会被保存
		②鼠标事件
			onclick单击事件
				(//阻止默认行为
				return false)
				批量绑定:
				先遍历,再循环绑定事件
			ondblclick双击事件
			oncontextmenu右键事件(当需要获取鼠标位置时,传递事件对象 e
			var x = e.clientX;
			var y = e.clientY;)
			onmouseover鼠标放上去的事件
			onmouseout鼠标离开的事件
			onmousemove鼠标移动事件
			onmousedown鼠标按下事件
			onmouseup鼠标弹起(松开)事件
			offsetTop获取当前元素相对于父级元素的y轴的偏移量  offsetLeft获取当前元素相对于父级元素X轴的偏移量, offsetWidth  offsetHeight
			获取当前元素的宽高
		③键盘事件
			onkeydown
			e.keyCode 获取的是大写键盘字符 Ascii
			onkeypress
			press按下 e.charCode 获取的是小写键盘字符 Ascii
			onkeyup
			
		④表单事件
			onfocus获取焦点
			onblur丧失焦点
			onchange当状态|值发生改变时触发的事件
			onselect
			onsubmit表单提交事件
			onreset重置
	6,事件的冒泡
		当触发一个元素的事件时,会自动触发该元素的父级和先辈级的同类型事件
		造成了事件的多层并发,导致页面混乱,就是事件冒泡
		//阻止事件冒泡	
		stopPropagation
		例:var ds = document.getElementsByTagName('div');

		//遍历
		for (var i = 0; i < ds.length; i++) {
		//绑定事件
		ds[i].onclick = function(e)
		{
			//解决ie和火狐对事件对象e的兼容性问题
			var e = (e)?e:window.event;

			//修改样式
			this.style.background = 'black';
			//阻止事件冒泡
			// e.stopPropagation();// 低版本ie浏览器不支持
			e.cancelBubble = true;
		}
	};

	7,扩展了解
			window.getComputedStyle
			例:
			var d = document.getElementById('d');
			var dd = getComputedStyle(d);
			var h = dd.height;
			console.log(h);
##第六天BOM
	浏览器对象模型(BOM) 可以使js 有能力与浏览器进行'对话'

	window 对象 代表当前浏览器打开的窗口  是js中最大的 最顶级的对象
	
	全局变量是  window 对象的 属性

	全局函数是  window 对象的 方法

	1,定义
		browser object model window对象
	2,子对象
		①document文档对象
		 dom
		页面文档中的html 都属于window的子对象(DOM) document

		②location对象
		用于获取当前页面中的地址(URL)信息 能使页面重定向
		属性:

		了解:		
		hash	设置或返回从井号 (#) 开始的 URL（锚）。
		host	设置或返回主机名和当前 URL 的端口号。
		search	设置或返回从问号 (?) 开始的 URL（查询部分）。

		常用:
		hostname	设置或返回当前 URL 的主机名。
		pathname	设置或返回当前 URL 的路径部分。
		href	设置或返回完整的 URL。
		port	设置或返回当前 URL 的端口号。 默认(80或443)不显示
		protocol	设置或返回当前 URL 的协议。

		方法:
			页面跳转  例:
			location.href='http://www.baidu.com'//
			location.replace('http://www.baidu.com')
			页面刷新
			location.href = location.href;// ctrl + f5
			reload
			例: location.reload()//相当于ctrl+r  F5
			reload(true)
			例: location.reload(true);//相当于ctrl+F5

		③navigator对象
		包含了有关访问者浏览器的相关信息
		了解部分:
		appCodeName	返回浏览器的代码名。
		Ie/Firefox/Chrome 返回值都是 'Mozilla'

		appMinorVersion	返回浏览器的次级版本。 IE8 
		appName	返回浏览器的名称。//IE Microsoft Internet Explorer  ///Firefox/Chrome Netscape
		appVersion	返回浏览器的平台和版本信息。 IE8
		browserLanguage	返回当前浏览器的语言。IE8
		cpuClass	返回浏览器系统的 CPU 等级。  ie8
		onLine	返回指明系统是否处于脱机模式的布尔值。
		platform	返回运行浏览器的操作系统平台。
		systemLanguage	返回 OS 使用的默认语言。
		userLanguage	返回 OS 的自然语言设置。
		常用必记:
		userAgent	返回由客户机发送服务器的 user-agent 头部的值。
		cookieEnabled	返回指明浏览器中是否启用 cookie 的布尔值。

		④screen对象
			属性
			availWidth  返回屏幕的宽度(不包括任务栏)
			availHeight 返回屏幕的高度(不包括任务栏)
			width 屏幕总宽度
			height 屏幕总高度

			页面的相关尺寸
			
			浏览器可视区域的宽高
			window.document.documentElement.clientWidth
			document.documentElement.clientHeight
			当前整个文档的宽高
			document.documentElement.scrollWidth
			document.documentElement.scrollHeight
			当前文档(页面) 滚动的距离 top left
			document.documentElement.scrollTop
			document.documentElement.scrollLeft
			
			兼容性
			//兼容问题 chrome
			// var t = document.body.scrollTop;
			// var l = document.body.scrollLeft;
		
			//解决兼容问题
			var t = document.documentElement.scrollTop || document.body.scrollTop;

		⑤history对象
		包含用户 (在浏览器窗口中) 访问过的所有url 历史信息
		
		属性: length 历史记录中url的数量
	
		方法:
			back()  加载历史列表中的前一个url
			forward() 加载历史列表中的下一个url
			go() //go(1)前进;-1后退


		⑥frames对象
		 包含了当前窗口(页面)中所有 子窗口中的window对象

		 //在子窗口中操作父级窗口的 window对象 要用parent
		 当前页面中的parent代表的是父级窗口中的window对象  在谷歌中必须要使用http协议才能使用parent

	3,基本方法

		alert提示框
		confirm确认框

		prompt获取用户输入 弹出带提示的 输入框,返回用户输入的信息

		open打开新窗口
		如果给打开的窗口起了名字,再开打时不是新建窗口,而是刷新已存在的;第三个参数,可以控制新打开窗口的位置,大小

		close关闭窗口
		setTimeout单次计时
			clearTimeout()关闭
		setInterval多次计时
			clearInterval()清空计时
	
		moveTo 定义浏览器位置
		moveBy 按照步进来移动浏览器
		resizeTo缩放浏览器
		resizeBy按照步进缩放浏览器
		scrollTo移动文档,(滚动条)
		scrollBy按照指定步进进行移动文档(滚动条)

	4,事件
		onresize当浏览器可视区域尺寸发生改变时触发的事件

		onscroll当文档滚动时触发的事件
##第七八天DOM
	1,简介
		HTML文档中的每个元素都是一个节点	无论是标签  标签属性  文本  注释甚至空白都算是一个节点

	2,查找元素
		①通用方法
			document.getElementById 通过id属性来查找元素
			document.getElementsByTagName 通过标签名来查找元素
			document.getElementsByClassName  通过类名来查找元素    ie有兼容问题
			document.getElementsByName 通过name属性查找元素


		②父子关系节点(重点记带*号的)
			childNodes  获取所有的子节点(包括文本节点和注释节点)
			*children  获取所有的子元素节点标签节点
			firstChild  第一个节点
			*firstElementChild  获取第一个元素节点
			lastChild  最后一个节点
			*lastElementChild 最后一个元素节点
			previousSibling  上一个节点
			*previousElementSibling  上一个元素节点
			nextSibling 下一个节点
			*nextElementSibling 下一个元素节点
			parentNode 父级节点
			*parentElement 父级元素节点

		③特殊节点
			document.doctype  获取文档头
			document.documentElement 获取html标签
			document.head  获取head标签元素
			document.body  获取body元素
			document.title 获取页面的标题 获取的不是title标签而是title标签中的文本
				(设置标题的时候  只能document.title = 'i love you')
			

		④节点集合
			document.forms  获取所有的表单元素
				(elements获取元素
				name获取元素)
			
			document.links  获取所有的a标签
			document.images  获取所有的img标签元素


	3,操作元素
		①修改元素
			1修改节点属性
				setAttribute
				getAttribute获取
				removeAttribute移出
			2修改元素的样式
				style
				setAttribute 或者 className
			3修改元素的文本
				innerHTML
				textContent

				区别:
				innerHTML获取时获取当前对象内的所有字符内容包括标签;能够解析标签
				textContent获取时只获取当前对象内的文本内容,忽略标签;不解析标签,不管给什么,都当成文本处理

			4设置form控件的值
				输入框值的获取和设置
					例:
					var form = document.forms[0];
					form.username.value = 'iloveyou';//赋值
					console.log(form.username.value);//获取

				单选框值的获取和设置
					例:
					var s = form.sex;
					s[0].checked = true;//设置选中
					for (var i = 0; i < s.length; i++) {
						if(s[i].checked){
						 console.log(s[i].value);//获取
						}
					};

				复选框值的获取和设置
					例:
					var hs = form['hobby[]'];
					//设置选中
					for (var i = 0; i < hs.length; i++) {
						if(hs[i].value == 2){
							hs[i].checked = true;
						}
					};
					//获取选中的值
					var arr = [];
					for (var i = 0; i < hs.length; i++) {
						if(hs[i].checked){
							// arr.push(hs[i].value);
							arr[arr.length] = hs[i].value;
						}
					};
					console.log(arr);

				文本域值的获取和设置
					例:
					 console.log(form.textarea.value);//获取
				   	 form.textarea.value = '就是帅';//设置
		
				下拉框值的获取和设置
					例:	 
						var lol = form.select;
					 	//获取当前选中的值(option选项中的value就是select的value)
						console.log(lol.value);//获取
						lol.value = 4;//设置

		②节点操作
		
		创建节点
			document.createElement创建标签
		插入节点
			appendChild从尾部插入
			insertBefore 从前面插入 (参数1要插入谁,参数2在谁的前面)
		删除节点
			removeChild  删除节点
		替换节点
			replaceChild  节点替换(参数1新的元素,参数2替换的模板)
		克隆节点
			cloneNode(true)  克隆复制节点
			克隆不会克隆事件,需自己再绑定
			参数true 如果不传递true 克隆时只克隆当前元素,不会克隆它的子标签和文本
			

	4,扩展了解
		XML
		Extensible Markup Language 可扩展的文本标记语言

		整个文档是一个文档节点 
		每个 XML 标签是一个元素节点 
		包含在 XML 元素中的文本是文本节点 
		每一个 XML 属性是一个属性节点 
		注释属于注释节点

		例:

		<?xml version='1.0' encoding='utf-8'?>
		<movies>
			<movie>
				<name>辩护人</name>
				<country>韩国</country>
			</movie>
			<movie>
				<name>V字仇杀队</name>
				<country>美国</country>
			</movie>
			<movie>
				<name>盗梦空间</name>
				<country>美国</country>
			</movie>
		</movies>
	
		XML的主要作用是为了信息传递
		XML 文档必须有根元素
		所有 XML 元素都须有关闭标签
		XML 标签对大小写敏感
		XML 必须正确地嵌套
		XML 的属性值须加引号

	js解析xml
		文件
			IE:
			var xmlDoc=new ActiveXObject("Microsoft.XMLDOM");
			xmlDoc.async=false;
			xmlDoc.load("note.xml");
			非IE:
			var xmlDoc=document.implementation.createDocument("","",null);
			xmlDoc.async=false;
			xmlDoc.load("note.xml");
	
		字符串
			if (window.DOMParser)//非IE
			  {
			  parser=new DOMParser();
			  xmlDoc=parser.parseFromString(txt,"text/xml");
			  }
			else // IE
			  {
			  xmlDoc=new ActiveXObject("Microsoft.XMLDOM");
			  xmlDoc.async=false;
			  xmlDoc.loadXML(txt);
			  }


	5,特效
		网站的标题闪烁,飞机大战,放大镜,二级菜单,表单验证,跟随广告,延时按钮,滚动广告,动态添加表单元素
##第九天Ajax
	1,定义
		asychronous  javascript   and   xml 异步的javascript和xml技术	 偷偷的请求服务器

	2,作用
		实现页面的无刷新请求服务器,提高用户体验

	3,基本使用
		①创建ajax对象
			new XMLHttpRequest()
			new ActiveXObject('Microsoft.XMLHTTP')
		②创建(绑定)事件函数(处理服务器返回的结果)
			onreadystatechange
				readyState ajax对象的状态
					0:请求未初始化
					1:服务器连接已建立
					2:请求已接受
					3:请求处理中
					4:请求已完成,且相应已就绪
				status响应码
					200:'OK'
					404:未找到页面
					403:权限不足
					
			  	responseText接收服务器返回的数据

		③初始化ajax请求
			 参数1,请求方式 参数2 url  参数3 是否异步 true异步 false同步
			get方式
				xmlhttp.open('get','1.php?a=1&b=2&c=3',true);
			post方式
				需要设置头信息,携带的参数要在send中写;
				xmlhttp.setRequestHeader('content-type','application/x-www-form-urlencoded');
				xmlhttp.open('post','1.php',true);

		④发送Ajax请求
			 send

	4,服务器返回
		echo普通的字符串
		普通html文件
		索引数组
		关联数组
		返回数组类型的数据使用json_encode() 将数据转成json格式字符串
		在ajax式用eval() 将字符串进行js语法解析

	5,注意事项
		同源策略:
			当前页面要和服务器的协议地址和端口 域(域名或ip地址)都要相同
		notice waring错误一定要留意
		post发送的ajax请求
			setRequestHeader('content-type','application/x-www-form-urlencoded');
		在使用ajax时一定要打开F12调试工具

	6,Ajax简单的封装
		(详见第九天js文件中的ajax.js文件)

	7,主要应用
		表单验证
		瀑布流
		无刷新登录网站
	
	8,重点
		基本操作4步骤
			
		服务器返回
			echo  '0';
			echo  json_encode($arr)

		同步异步 必须要理解
			同步:false,有特别要求用,同步就是等在原地等待数据的回来;

			异步:true,一般用异步,异步就是不等数据回来先往下面执行数据最后还是会回来;

		firebug(调试工具F12)要练熟

		进行ajax操作的时候 一定要将firebug打开网络tab项 对当前ajax请求的连接进行查看

		ajax也可以当作是一个微型的客户端
		(客户端并不只是指浏览器)

	9,补充:(以下响应码了解)
		http响应码			
				http状态返回代码 1xx（临时响应）
				表示临时响应并需要请求者继续执行操作的状态代码。
				http状态返回代码 代码   说明
				100   （继续） 请求者应当继续提出请求。 服务器返回此代码表示已收到请求的第一部分，正在等待其余部分。 
				101   （切换协议） 请求者已要求服务器切换协议，服务器已确认并准备切换。
				http状态返回代码 2xx （成功）
				表示成功处理了请求的状态代码。
				http状态返回代码 代码   说明
				200   （成功）  服务器已成功处理了请求。 通常，这表示服务器提供了请求的网页。
				201   （已创建）  请求成功并且服务器创建了新的资源。
				202   （已接受）  服务器已接受请求，但尚未处理。
				203   （非授权信息）  服务器已成功处理了请求，但返回的信息可能来自另一来源。
				204   （无内容）  服务器成功处理了请求，但没有返回任何内容。
				205   （重置内容） 服务器成功处理了请求，但没有返回任何内容。
				206   （部分内容）  服务器成功处理了部分 GET 请求。
				http状态返回代码 3xx （重定向）
				表示要完成请求，需要进一步操作。 通常，这些状态代码用来重定向。
				http状态返回代码 代码   说明
				300   （多种选择）  针对请求，服务器可执行多种操作。 服务器可根据请求者 (user agent) 选择一项操作，或提供操作列表供请求者选择。
				301   （永久移动）  请求的网页已永久移动到新位置。 服务器返回此响应（对 GET 或 HEAD 请求的响应）时，会自动将请求者转到新位置。
				302   （临时移动）  服务器目前从不同位置的网页响应请求，但请求者应继续使用原有位置来进行以后的请求。
				303   （查看其他位置） 请求者应当对不同的位置使用单独的 GET 请求来检索响应时，服务器返回此代码。
				304   （未修改） 自从上次请求后，请求的网页未修改过。 服务器返回此响应时，不会返回网页内容。
				305   （使用代理） 请求者只能使用代理访问请求的网页。 如果服务器返回此响应，还表示请求者应使用代理。
				307   （临时重定向）  服务器目前从不同位置的网页响应请求，但请求者应继续使用原有位置来进行以后的请求。 
				http状态返回代码 4xx（请求错误）
				这些状态代码表示请求可能出错，妨碍了服务器的处理。
				http状态返回代码 代码   说明
				400   （错误请求） 服务器不理解请求的语法。
				401   （未授权） 请求要求身份验证。 对于需要登录的网页，服务器可能返回此响应。
				403   （禁止） 服务器拒绝请求。
				404   （未找到） 服务器找不到请求的网页。
				405   （方法禁用） 禁用请求中指定的方法。
				406   （不接受） 无法使用请求的内容特性响应请求的网页。
				407   （需要代理授权） 此状态代码与 401（未授权）类似，但指定请求者应当授权使用代理。
				408   （请求超时）  服务器等候请求时发生超时。
				409   （冲突）  服务器在完成请求时发生冲突。 服务器必须在响应中包含有关冲突的信息。
				410   （已删除）  如果请求的资源已永久删除，服务器就会返回此响应。
				411   （需要有效长度） 服务器不接受不含有效内容长度标头字段的请求。
				412   （未满足前提条件） 服务器未满足请求者在请求中设置的其中一个前提条件。
				413   （请求实体过大） 服务器无法处理请求，因为请求实体过大，超出服务器的处理能力。
				414   （请求的 URI 过长） 请求的 URI（通常为网址）过长，服务器无法处理。
				415   （不支持的媒体类型） 请求的格式不受请求页面的支持。
				416   （请求范围不符合要求） 如果页面无法提供请求的范围，则服务器会返回此状态代码。
				417   （未满足期望值） 服务器未满足"期望"请求标头字段的要求。
				http状态返回代码 5xx（服务器错误）
				这些状态代码表示服务器在尝试处理请求时发生内部错误。 这些错误可能是服务器本身的错误，而不是请求出错。
				http状态返回代码 代码   说明
				500   （服务器内部错误）  服务器遇到错误，无法完成请求。
				501   （尚未实施） 服务器不具备完成请求的功能。 例如，服务器无法识别请求方法时可能会返回此代码。
				502   （错误网关） 服务器作为网关或代理，从上游服务器收到无效响应。
				503   （服务不可用） 服务器目前无法使用（由于超载或停机维护）。 通常，这只是暂时状态。
				504   （网关超时）  服务器作为网关或代理，但是没有及时从上游服务器收到请求。
				505   （HTTP 版本不受支持） 服务器不支持请求中所用的 HTTP 协议版本。

##三天jQuery
	1,简介
		是一个免费的,开源的javascript库

	2,作用
		方便的完成web前端的相关操作,例如节点操作,元素操作,事件绑定,ajax操作,且解决了大多数的兼容性问题

	3,使用
		①配置
			本地配置:
				1,下载jquery文件 官网(www.jquery.com)
				2,移入jquery文件
			访问远程文件
				<script src="http://www.xxoo.com/jquery.js"></script>
			检测配置
				引入后再script中使用alert($) 或者 
				alert(jQuery)来检测是否引入成功
			

		②应用
			1,查找元素
				①基本获取
					通过id查找元素
					$('#id');
					通过标签名或者元素
					$('div');
					通过class属性获取
					$('.class')
					逗号并列获取
					$('#id,.class');
					空格层级获取
					$('#id .class')
				②过滤获取
					获取第一个元素
					$('li:first')
					获取最后一个元素
					$('li:last')
					获取指定索引的元素
					$('li:eq(5)')
					获取包含指定文本的元素
					$('li:contains("love")')
					通过属性查找元素
					$('input[name=username]')
					$('input[type=text][name=email]')
				③父子获取
					获得所有的子元素
					$('ul').children()
					获取第一个子元素
					$('ul li:first-child')
					获取最后一个子元素
					$('ul li:last-child')
					获取指定索引的元素
					$('ul li:nth-child(1)')  //这里的索引是从1 开始的
					获取下一个元素
					$('#id').next()
					获取上一个元素
					$('#id').prev()
					获取父级元素
					$('#id').parent()
					获得先辈元素
					$('#id').parents('.class')
					获得同辈元素
					$('#id').siblings()
					在父级元素中查找元素
					$('ul').find('.class')

			2,元素操作
				①属性操作
					attr()//添加/获取属性
					removeAttr()//移除属性
				②样式操作
					css()
					addClass
					removeClass

				③文本操作
					text()
					html()
					相当于innerHTML和contentText
				④form元素值的操作
					参考课件中4.html中或者jquery版本的全选反选

				⑤其他
					获取元素相对于文档的偏移offset()//可以直接.left/.top获取来运算
					获取元素相对于父级元素的偏移position()//可以直接.left/.top获取来运算
					元素的滚动距离(两者既可以获取也可以设置)
					scrollLeft() , scrollTop()
					
					宽度高度 
						width
						获取可视区域的宽度
						$(window).width()
						获取整个文档的宽度
						$(document).width()
		
					height
						获取可视区域的高度
						$(window).height()
						获取整个文档的高度
						$(document).height()
	
			3,节点操作
				①创建元素
					$('<div></div>')
					$('<div class="cls"><span>iloveyou</span></div>')
				②插入元素
					内部尾部添加
					$(parent).append(newNode)
					newNode.appendTo(parent)
					内部头部添加
					$(parent).prepend(newNode)
					newNode.prependTo(parent)
					元素外部之后添加
					$(element).after(newNode);
					newNode.insertAfter(element)
					元素外部之前添加
					$(element).before(newNode)
					newNode.insertBefore(element)
				③删除元素
					$(element).remove() 删除当前元素
					$(element).empty()清空
				④替换节点
					$(element).replaceWith(newNode);
				⑤克隆节点
					$(element).clone(true)
				⑥包裹元素
					$(element).wrap('<div></div>')
					$(element).unwrap()

			4,事件
				①事件绑定
					基本绑定(更多见手册)
						$(element).click(function(){})
						$(element).dblclick(function(){})
						..........
						加载完毕事件
						$(document).ready(function(){})
						$(function(){})

					方法绑定
						$(element).bind('click', function(){})
						$(element).unbind();//括号内指定要解绑的事件,不指定则解除当前元素所有事件

					动态绑定
						$(element).live('click', function(){})

				②事件触发
					$(element).trigger('click')

				③阻止事件冒泡和默认行为
					return false;

				⑤获得当前鼠标的位置和按键
					$(element).click(function(e){})
					var x = e.clientX;//client相对于窗口的00点
					var y = e.clientY;
					var _x = e.pageX;//相对于文档
					var _y = e.pageY
					e.keyCode
					例:
						$(window).mousemove(function(e){
							//获取鼠标位置
							console.log(e.clientX,e.clientY);
						    console.log(e.pageX,e.pageY);
						})

						//键盘事件 
						$(window).keydown(function(e){
							console.log(e.keyCode);
						})


			5,ajax请求
				$(this)在ajax请求中代表的是当前的ajax对象 所以要注意$(this)的使用!!
				
				全局配置  扩展
				$.ajaxSetup({
				 	//是否异步 true 异步   false  同步
				 	async:false
				)

					
				①$.get()
				②$.post()
				参数  (url,data,func,type) type 返回内容格式，xml, html, script, json, text, _default。

				③$.ajax()
					url请求的脚本
					data发送的数据
					dataType数据的类型
					type请求的类型
					success成功的执行代码
					error失败的执行代码
					timeout 超时时间  设置请求时间 ,必须是异步请求时才能生效
					async 是否异步
				例:
					$.ajax({
						url:'5.php',//请求的url
						type:'post',//请求的方式
						data:{id:10,name:'lisi'},//请求携带的参数
						// dataType:'json',//返回的数据类型
						success:function(data){
							//请求成功后执行的代码
							console.log(data);
						},
						error:function()
						{
							//请求出错时执行的代码
							alert('出错啦  思密达');
						},
						timeout:2000,//设置请求时间 ,必须是异步请求时才能生效
						async:false//true  异步 false 同步
					})9

			6,(库中自带)特效(括号里可加入时间)
				快速显示和隐藏
					$(element).hide()
					$(element).show()
				滚动显示和隐藏
					$(element).slideDown()
					$(element).slideUp()
				渐隐渐显
					$(element).fadeIn()
					$(element).fadeOut()
				自定义动画
					$(element).animate({},2000)
				停止
					$(element).stop()
				延时
					$(element).delay(2000)



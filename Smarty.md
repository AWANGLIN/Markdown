#Smarty
	
	1,定义:
		一个开源的模板引擎
		模板引擎是为了使用户界面与业务数据分离而产生的,它可以生成特定格式的文档,用于网站的模板引擎就会生成一个标准的HTML文档

	2,功能

		将网站的数据和网站的界面实现分离(php和HTML代码)

		缓存
		
	
	3,下载
		(www.smarty.net)

	4,使用
		①引入smarty类库
		②实例化smarty对象

		③初始化参数
			template_dir  模板存放目录
			compile_dir  编译目录
			config_dir  配置文件目录
			left_delimiter  左边界
			right_delimiter 右边界
			caching  是否开启缓存
			cache_dir 缓存文件目录
			cache_lifetime 缓存文件有效时间(单位是秒)

		④分配变量
			普通变量

				例:$s->assign('abc',$title);

			超全局变量
				{$smarty.get}
				{$smarty.post}
				{$smarty.cookies}
				{$smarty.session}
				{$smarty.server}
				
				例:
					{$smarty.get['id']}
					{$smarty.get.age}
					{$smarty.post['name']}
					{$smarty.post.name}
					{$smarty.cookies.like}
					{$smarty.session.love}
					{$smarty.server.HTTP_USER_AGENT}

			保留变量
				$smarty.now	时间戳
				$smarty.const 获取常量
				$smarty.template返回正在处理的当前模板名
				$smarty.current_dir 获取当前模板文件的目录
				$smarty.version 获取smarty的版本信息
				$smarty.ldelim 左定界符
				$smarty.rdelim 右定界符

				$smarty.config获取配置文件中的信息
					实现多语言功能
					configs目录下的配置文件的文件名可以随意起

				例:	
					{$smarty.now}
					{$smarty.const.LOVE}
					{$smarty.const.LIKE}
					{$smarty.template}
					{$smarty.version}
					{$smarty.config.USER}

		⑤解析模板
			1,{*注释*}

			2,忽略smarty解析  {literal}{/literal}
			
			3,直接使用函数和变量调节器
				cat 连接字符串
				date_format 格式化日期
				default
				truncate 截取
				replace 替换
				upper 大写
				lower 小写
				(也可以使用我们php中的函数用法不变,只要在外面加上{})
				例:
					{$love|cat:'verymuch'}
					{$smarty.now|date_format:'Ymd'}
					{$usernames|default:'<a href="">请登录</a>'}
					{$str|truncate:13}
					{$love|replace:'love':'like'}

			4,内置函数
				 {assign}  在模板中定义变量
				 {append}  向数组中压入元素
				 {capture} 捕获
				 {debug}   debug调试模式
				 {include} 引入文件

				 {extends}模板继承
						append
						prepend	

				(注意以下都是有结束标签的)
				for循环
				foreach循环
				if elseif else
				{nocache}不缓存标签中的数据
				{strip}排版成一行
				{literal} 不使用smarty解析
				
				例:
					{for $i=0 to 10 step=2}
						{$i}
						<br>
					{/for}

					{foreach $users as $k=>$v}
						{$v['id']}
						{$v['username']}
					{/foreach}

					{if $total >90}
						给你买个锤子
					{else if $total >=80 && $total <=90}
						给你买个煎饼果子
					{else}
						给你买个毛线
					{/if}

					{nocache}
					<p>不缓存{$smarty.now}</p>
					{/nocache}



			

		
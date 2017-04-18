##MVC
	1,简介
		MVC是一种设计模式
		MVC全名是Model View Controller
		是模型(model)－视图(view)－控制器(controller)的缩写

	2,特点
		单入口
		结构清晰
		扩展性强

	3,搭建

		单入口文件index.php

		MVC目录
			模型Model=>Model.class.php
			视图View=>smarty
			控制器Controller=>Controller
			配置文件config
			公共目录Public

##命名空间
	1,介绍
		命名空间是一种封装事物的方法.就是将代码放到一个'文件夹'中

	2,作用
		①为了防止命名重复
			CertificateNotYetValidException
			CertificateNotYetValidException
			CertificateParsingException
			CertificateParsingException
			CertificateRevokedException
		
			ertificate
				NotYetValidException
				NotYetValidException
				ParsingException
				ParsingException
				RevokedException

	    ②方便类的引入

	3,使用
		①创建命名空间
			namespace space
			namespace  a\b\c

			注意事项:
				命名空间语句必须要放到第一行
				命名空间只对函数,类和常量(const)有效  变量是全局有效的
				大多数情况下 都是一个文件一个命名空间

		②命名空间的使用
			常量操作

			函数操作
				系统同名函数
				变量函数

			类的操作
				系统类
				变量类
				导入



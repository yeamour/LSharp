﻿A Pure C# IL Runner,Run DLL as a Script.直接解析执行IL的脚本引擎
	L#是FB引擎系列的一部分
	欢迎访问FB引擎主站http://www.FBact.com
	欢迎加入讨论QQ群：223823428
	用途，Unity3D热更（包括IOS平台）等
	Beta阶段，有一定动手能力的小伙伴，已经可以将它用于实战
	更新日志：
2015-02-02 V0.39.7Beta
	修正了调用函数使用ｅｎｕｍ参数的问题
2015-01-30 V0.39.6Beta
	修正了数值数组初始化的问题
2015-01-30 V0.39.5Beta
	修正了脚本定义struct
	修正了使用 Type作为参数的函数调用问题
2015-01-28 V0.39.4.1Beta
2015-01-28 V0.39.4Beta
	修改了一小批bug
2015-01-28 V0.39.3Beta
	修改一处参数bug
2015-01-28 V0.39.2Beta
	修改了一些继承检查，有充分的警告
2015-01-27 V0.39.1Beta
	修改了数组取值的一点问题
	时隔5天才发现新的Bug，
	正式作为Beta版。
2015-01-22 V0.39PreBeta
	这几天帮助一个朋友进行了C#Light项目迁移L#的VIP服务（玩笑，只是他集中的发现了不少bug）
	L#的稳定性也得到了极大的增强
	将版本提升到PreBeta.
2015-01-21 V0.38.3Alpha
	修正一处参数传数值问题
2015-01-21 V0.38.2Alpha
	修正一处模板类型查找的问题
2015-01-21 V0.38.1Alpha
	修正一处参数的bug
2015-01-21 V0.38Alpha
	进行了一轮优化
2015-01-21 V0.37Alpha
	构造函数数值类型转换修复
2015-01-21 V0.36.9Alpha
	脚本内置类型数组修复
2015-01-21 V0.36.8Alpha
	参数检查顺序反了，严重bug，两个参数以上的call，不会检查类型了。
	已修复
2015-01-21 V0.36.7Alpha
	修复brfalse语句，if不命中时偶有问题
2015-01-19 V0.36.6Alpha
	修改了脚本对脚本调用传参的一处bug
2015-01-18 V0.36.5Alpha
	修改了一些委托相关的bug
2015-01-18 V0.36.4Alpha
	修改了一些在u3d环境的问题
2015-01-17 V0.36.3Alpha
	修改了一下MethodParamList的接口，防止滥用
	不允许再修改MethodParamList的内容
2015-01-17 V0.36.2Alpha
	Test01增加一个CrossBind的使用例子
2015-01-17 V0.36.1Alpha
    数组长度没实现，补上
2015-01-16 V0.36Alpha
    修复了一处直接调用函数bool传参的问题
	增加了用反射加载执行和用L#CLR加载执行的快速切换方式，见例子Test01
	增加了一个autoLogDump的参数
	 object IMethod::Invoke(ThreadContext context, object _this, object[] _params, bool bVisual,bool autoLogDump);
	脚本委托默认打开此参数
	打开此参数时，脚本内异常堆栈自动通过ILogger.LogError 输出
2015-01-16 V0.35.2Alpha
	脚本继承脚本时，没有区分虚实调用，导致脚本的base.XX()实际上调用的是this.XX()，已修复。
2015-01-15 V0.35.1Alpha
	给成员变量赋内部值类型时可能发生转换，已修复。
2015-01-14 V0.35Alpha
	Unity_HelloWorld 在WP运行成功
	调整了一个ForUnity目录，里面放基本的支持库
2015-01-14 V0.34Alpha
	Unity_HelloWorld 在IOS运行成功
2015-01-13 V0.33Alpha
	增加Dump机制
	Try catch 脚本执行入口，catch以后，调用
	string CLRSharp.ThreadContext.activeContext.Dump()
	可以Dump出脚本错误堆栈，这个函数完全可以外部实现
	可参考此函数自行Dump
2015-01-13 V0.32Alpha
	支持了CrossBind，让脚本可以通过绑定继承程序类型
	目前实现了yield，就是通过这种方式实现的
	env构造时就执行了这样两句
		RegCrossBind(new CrossBind_IEnumerable());
		RegCrossBind(new CrossBind_IEnumerator());
	这样就可以让脚本继承IEnumerable 和 IEnumerator
	也就是迭代器的基础

2015-01-13 V0.31.5Alpha
	处理了脚本继承脚本的虚函数问题
2015-01-13 V0.31.3Alpha
	处理了枚举值得box转换
2015-01-13 V0.31.2Alpha
	//值管理有泄露。。修复
2015-01-13 V0.31.1Alpha
	从loc来的变量没有Clone，导致计算错误
	//还有其他可能的各种bug
	//需要查一遍
2015-01-13 V0.31Alpha
	继续重构了堆栈数值类型部分，之前的虚调用太多，性能很差，改写
2015-01-13 V0.3Alpha
	重构了堆栈数值类型部分,解决一些数值类型执行上的bug
2015-01-12 V0.23Alpha
	加入一个MethodCache 和FieldCache，期待提升性能
2015-01-12 V0.22.2Alpha
	修复脚本中类中类的查找
2015-01-12 V0.22.1Alpha
	实现了switch指令
2015-01-12 V0.22Alpha
	规范修改了数值计算
2015-01-12 V0.21.1Alpha
	修复bug:if xxx==null问题
2015-01-12 V0.21Alpha
	修复bug:结构体的构造
2015-01-11 V0.20Alpha
	所有用例全部通过
2015-01-11 V0.17Alpha
	线程局部存储Context，委托调用安全
2015-01-11 V0.16Alpha
	try catch用例通过
	用例通过情况(38/39)
2015-01-11 V0.15Alpha
	增加EvilTesto用例九个
	用例通过情况(37/39)
	除try catch以外，基本语法都通了
2015-01-10 V0.10Alpha
	匿名函数实现
	用例通过情况(30/30)
	C#LightTestor所有用例移植完毕
2015-01-10 V0.07Alpha
	调整了代码结构，更顺畅，也为实现匿名函数打下了基础
	用例通过情况(29/30)
2015-01-09 V0.06Alpha
	修改了很多，基本测试基本通过
	用例通过情况(29/30)
2015-01-09 V0.05Alpha
	改进了类型匹配方法，对模板类型可以根据名称任意深度匹配
	用例通过情况(26/30)
2015-01-09 V0.04Alpha
	继续实现,推进了很多CLR的实现
	用例通过情况(24/30)
2015-01-08 V0.03Alpha
	增加了PDB的加载
	改变了界面显示，更容易对照源码和汇编
	增加了DebugLevel
2015-01-08 V0.02Alpha
	开始跑表达式用例
	用例通过情况(14/30)
2015-01-07 V0.01Alpha
	暂定名 L# 
	新坑报道，直接解析执行IL，相当于CLR的工作
	可用于Unity在IOS等奇葩平台解析执行，将所有dotnet语言作为脚本
	可用于Xamarin，silverlight ，wp winstore开发，只要有dotnet 2.0的环境即可。
	语法完美支持c# vb.net F#等任何语言，只要能编译为dll即可。
	目前实现程度还刚开始。
	可以跑个循环，调用静态函数。用例3个
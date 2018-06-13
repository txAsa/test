#ReactJs
起源于facebook的内部项目  
	- react不是一个完整的MVC模型，最多可认为是View，甚至react并不是非常认可MVC开发模式。
	- React是一个纯V层，不擅长与动态数据打交道，也替代不了常规MVC框架
	- React擅长处理组件化界面
###组件化
	即封装起来的具有独立的功能的UI部件
	虚拟dom不仅带来了简单的ui开发逻辑，同时也带来了组件化开发思想。react推荐以组件的方式去重新思考ui构成，将ui上每一个功能相对独立的模块定义成组件，然后将小的组件通过组合或者嵌套的方式构成大的组件，最终完成整个ui构建
#####react认为一个组件有以下特征
1. 可组合：一个组件易于和其他组件一起使用
2. 可重用
3. 可维护
#####webpack
1. 模块化，把复杂的程序细化为小文件
2. 类似于typeScript这种在JS基础上拓展的开发语言，使我们能够实现目前版本的JS不能直接使用的特性，并且之后还能转为JS文件，使浏览器能识别  
作用：可找到js模块或你的项目中浏览器不能识别的文件及语言打包成浏览器可识别的格式  
工作方式：把你的项目当做整体，通过一个给定的主文件，webpack将从这个文件开始找到你的项目的所有依赖文件，使用loader处理它们，最后打包为一个或多个浏览器可识别的js文件
####JSX
HTML语言直接写在JS语言中，不加任何引号，这就是JSX的语法，它允许html与js混写  
缺点： 
	- JSX只支持一个根节点  
另注：JSX的优点就是html与js混写，但也是它的缺点    
改变this的指向（3个）
	- apply（）参数数组
	- call（）参数是以‘x，x..’分隔
	- bind（）不会立即执行当前的指向
####state和props的区别
1. state：一般用于组件内部的状态维护，更新组件内部数据，状态，更新子组件的props等。
2. props：一般用于父组件与子组件通信，在组件之间通信使用
3. state可变，props不可变（只不修改数据源）
####单项数据流
	在react中，数据的流向是单向的，从父节点传到子节点
###react组件生命周期
1. 挂载阶段，组件第一次绘制阶段（虚拟节点变成真实节点）
2. 运行阶段，组件运行个交互阶段，处理用户交互，或者接受事件更新界面
3. 卸载阶段，组件卸载消亡的阶段

		实例化
		首次实例化
		
		getDefaultProps
		getInitialState
		componentWillMount
		render
		componentDidMount
		实例化完成后的更新
		
		getInitialState
		componentWillMount
		render
		componentDidMount
		存在期
		组件已存在时的状态改变
		
		componentWillReceiveProps
		shouldComponentUpdate
		componentWillUpdate
		render
		componentDidUpdate
		销毁&清理期
		componentWillUnmount
###Redux(状态机)
对于大型的复杂应用，代码结构，组件之间的通信，恰恰是关键，因此只用React没法写大型应用。  
Redux是一个独立的框架，他可以独立运行
####概念及API
	store保存数据的地方
	action，就是view发出的通知，表示state应该要发生变化了。state的变化，会导致view的变化
	
	state：每次调用计算函数时，会把当前store的所有状态传递过来。
	action：每次发送action促发计算函数时，会把本次action传递过来

扩展：  
	匿名函数：当前函数所属对象，当前函数属于谁，this就指向谁
	箭头函数：当它所处环境在是哪个对象，它的this就指向哪里
####router
	监听url的变化，然后进行相应的跳转
	react-router通过监听url，实现组件的切换和状态的变化，开发复杂的应用几乎都会用到
####跨域
浏览器不能直接执行其他网站的脚本（不同域名之间相互访问），它是由浏览器的同源策略造成的，是浏览器对javascript施加的安全限制（所谓同源就是指，域名，协议，端口相同）
location和127.0.0.1虽然都是指向本机，但属于跨域，跨域只存在于js代码中，图片音频不会被限制。  
####react的ajax
npm i axios --s 安装  
引入import axios from 'axios'  
用法：axios.get('.....',{}).then(function(data){})  
get方式传递参数需要在{}中家伙是哪个params  ，例：{params:{name：‘ss’..}}  
#Vue框架
####vue和react
1. react和vue都是用虚拟dom，Virtud DOM
2. react和vue都是提供了响应式和组件化的视图组件
3. react和vue都将注意力集中保持在核心库，伴随于此，有配套的路由和负责处理全局的状态的库
4. react使用jsx渲染页面，vue使用简单的模块
5. vue比react运行更快
####Vue的优势
1. 模板和渲染函数的弹性选择
2. 简单语法和项目配置
3. 更快的渲染速度和更小的体积
####React的优势
1. 更适合大型应用和更好的可测试性
2. Web端和移动端原生App通吃
3. 更大的生态系统，更多的支持和好用的工具
####模板语法
{{}}  
1. v-html将数据（标签）渲染成html  
2. v-bind绑定自定义 		缩写‘：’
3. v-on点击，简写@，不需要加上on，它的点击促发函数写在methods:{funName(){}}
4. <p v-if=''></p>引号中给的值为布尔，才能正常识别，当然也有<p v-else=''></p>
5. v-for=''循环数组
6. v-for=''循环对象
7. v-model=''双向绑定，用于采集value值

####.vue结构
	<template></template>模板  
	<script>
	export deafult{
		name:'zhangsan',
		data(){
				return {
					.....
				}		
			}	
		}
	</script>
####vue路由
vue.use(Router),可直接把{}内的组件，注册成全局，其他地方，则不需要import引入
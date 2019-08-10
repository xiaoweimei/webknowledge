1. SCSS是什么
- 加强版的CSS
2. SaSS的历史
- Awesome非常厉害的类CSS语言2007年第一版2016年完全成熟
- 把所有括号分号冒号都去掉的CSS
- SCSS在Sass基础上把括号冒号分号都又重新加了回来Ruby语言写的 Rails
3. rail是ruby社区的全栈框架
4. 安装与运行
- 零配置学习-使用parcel parcel代替webpack的
- npx parcel index.html把你的html跑起来
5. 最简单的几个语法
- 嵌套选择器 变量 mixin placeholder
6. 可以使用变量
- 如`$r:red; h1{color:$r}`
- 可以使用嵌套
7. mixin与placeholder
- 可以把一堆代码写在一起，起一个名字，在不同地方使用，这种方法叫mixin，
- mixin还可以接受变量，并且设置默认值但这种方法并没有节省代码量，因为是选择器不放在一起，样式每次都要复制一次
- mixin只是把代码机械的复制了，并没有节省代码量，为了解决这个问题，发明了placeholder，样式写一次，选择器放一起
8. 在线编码网站jsbin codepen codesandbox
```
//div>ul>li
//变量 嵌套选择器
$grey:#666; //变量
$gray:$grey;
$boder-width:2px;
@mixin debug{ //minin不接受参数
	border:$boder-width solid red;
}
@mixin decolor($border-color:red){ //minin接受默认参数
	border:3px solid $border-color;
}
.nav{
	@include decolor(blue); //嵌套及mixin
	>ul{
		@include debug; 
		>li{
			@include decolor;
		}
	}
}
```
```
//div>ul>li
//变量 嵌套选择器
$grey:#666;
$gray:$grey;
$boder-width:2px;
%debug{  //placeholder写法
	border:$boder-width solid red;
}
.nav{
	@extend %debug; //placeholder调用
	>ul{
		@extend %debug;
		>li{
			@extend %debug;
		}
	}
}
```

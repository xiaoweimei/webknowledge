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
- BEM（block element modifier） CSS命名法
1. 主要名字.user-card
2. 细节部分 .user-card__picture .user-card__name
3. 状态部分 .user-card--active
- 直接加&符号可以省略前置部分代码
- 嵌套属性，属性也是可以嵌套的，比如font-size,font-family可以嵌套
- 注释，
1. css注释/*这是CSS注释*/
2. sass注释//这是sass注释
3. 变量也是可以有作用域的CSS变量的作用域覆盖
4. 支持加减乘除取余
5. 颜色相关运算，提供了一套操控颜色的函数，30多种关于颜色的函数
6. 关于字符串插值
```
---------------------------------
html
---------------------------------
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>SCSS 2</title>
  <link rel="stylesheet" href="./2.scss">
</head>
<body>
<div class="userCard">
  <div>
    <div class="userCard-name">scss语法</div>
    <div class="userCard-oneSentence">前端社区</div>
  </div>
  <div class="userCard-description">前端社区</div>
</div>
</body>
</html>
---------------------------------
2.scss
---------------------------------
$red:#f60;
.userCard{
	width:100px;
	&.active{
		width:100px;
	}
	&-name{ //直接加&符号可以省略前置部分代码
		font:{
			size:18px;
			weight:bold;
			family:"楷体";
		}
		&:hover{
			color:$red;
		}
	}
	&-description{
		$width:100px; //变量作用域
		width:$width;
		height:$width;
		border-radius:$width/4; //使用除法
		border:1px solid green;
	}
	&-oneSentence{
		&::before{
			content:'oop#{$red}' //字符串中插入变量
		}
		&::after{
			content:'ppo'
		}
	}
}
```

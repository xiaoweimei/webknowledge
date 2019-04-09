### 事件队列、事件循环、执行栈
- js是单线程语言，同步代码依次执行，异步代码放入循环队列
### js基本物料
- 基础类型、表达式、语句、流程控制、函数、数组、引用类型、正则等等
### 控制页面
- DOM操作
- 常见事件 鼠标点击、鼠标放上去
- 先选取用querySelector，querySelectorAll，再绑定
### 养成编程思路，分析问题处理问题
### 运用自如、优化、复用、组件、模块
### 数组常用方法 forEach方法，sort方法 还有各种方法
- 懒加载、轮播、数据流
### window对象的一些知识
1. `window.outerHeight` 返回浏览器窗口的外部高度 `window.outerWidth`返回浏览器窗口的外部宽度
2. `window.innerHeight` 返回浏览器窗口的内容区域的高度包含垂直滚动条(如果有的话) `window.innerWidth`返回浏览器窗口的内容区域宽度，包含水平滚动条(如果有的话)
- 举个例子：打开控制台后，向上拖动控制台上面边线，使右侧垂直方向出现滚动条，这个时候，innerHeight的值就会随着你的拖动变得越来越小，而不拖动浏览器外部放大缩小窗口的话，outerHeight是不会改变的。
3. `window.screenX`和`window.screenY`属性，返回浏览器窗口左上角相对于当前屏幕左上角的水平距离和垂直距离（单位像素）。这两个属性只读。
4. `window.scrollX`属性返回页面的水平滚动距离，`window.scrollY`属性返回页面的垂直滚动距离，单位都为像素。这两个属性只读。
5. `window.pageXOffset`属性和`window.pageYOffset`属性，是`window.scrollX`和`window.scrollY`别名。
6. `window.screen`Screen 对象表示当前窗口所在的屏幕，提供显示设备的信息。`window.screen`属性指向这个对象。包括屏幕高度、宽度、可用高度、可用宽度、色彩位深等
7. `window.navigator`属性指向一个包含浏览器信息的 Navigator 对象。脚本通过这个属性了解用户使用的是哪一种浏览器。
8. `window.alert()`、`window.prompt()`、`window.confirm()`都是浏览器与用户互动的全局方法。
### JavaScript其中数据类型
- Number\String\Undifined\Null\Bool\Symbol\Object
### 手写一个AJAX
```
 let xhr = new XMLHttpRequest()
 xhr.open('POST', '/xxxx')
 xhr.onreadystatechange = function(){
     if(xhr.readyState === 4 && xhr.status === 200){
         console.log(xhr.responseText)
     }
 }
 xhr.send('a=1&b=2')
```
### 函数节流: 指定时间间隔内只会执行一次任务；
- 任务触发之后，先对指定值进行判断，为真则什么也不做；为假则执行代码，并把指定值设为真，同时三秒钟后把指定值设为假
### 函数防抖: 任务频繁触发的情况下，只有任务触发的间隔超过指定间隔的时候，任务才会执行。
- 初始将timeid设为null，遇到事件触发时，先进行判断，timeid存在则将其消除，不存在则将其设为5秒钟后执行的函数名，同时在执行完函数之后就将其设为null
### 函数节流
```
function fn(){}
var cd=false
button.onclick=function(){
  if(cd){
  //
  }else{
    fn();
    cd=true;
    var timeId=setTimeout(()=>{
      cd=false
      },3000)
  }
}
//主要思路，事件触发后立即执行，无视三秒钟内的操作
```
### 函数防抖
```
var timeId=null
button.onclick=function(){
  if(timeId){
    window.clearTimeout(timeId)
  }
  timeId=setTimeout(()=>{
    fn()
    timeId=null
  },5000)
}  
//主要思路，事件触发后开始计时，如果5秒钟内无后续操作再执行
```
### 同源策略与跨域
- 浏览器出于安全方面的考虑，只允许与本域下的接口交互。不同源的客户端脚本在没有明确授权的情况下，不能读写对方的资源。
- 本域指的是：同协议、同域名、同端口
- 跨域的几种方式：JSONP、CORS、降域跨域、postMessage
### 作用域与作用域链
- 函数在执行的过程中，先从自己内部找变量
- 如果找不到，再从创建当前函数所在的作用域去找, 以此往上
- 注意找的是变量的当前的状态
### 字符串操作
- length返回长度，charAt返回指定位置的字符,charCodeAt返回指定位置的unicode码点，concat方法用于连接两个字符串。
- slice方法用于从原字符串取出子字符串并返回，
- indexOf方法用于确定一个字符串在另一个字符串中第一次出现的位置，返回结果是匹配开始的位置。如果返回-1，就表示不匹配。
- trim方法用于去除字符串两端的空格，返回一个新字符串，不改变原字符串。toLowerCase方法用于将一个字符串全部转为小写，toUpperCase则是全部转为大写。
- match方法用于确定原字符串是否匹配某个子字符串，返回一个数组，成员为匹配的第一个字符串。
- search方法的用法基本等同于match，但是返回值为匹配的第一个位置。replace方法用于替换匹配的子字符串。
- split方法按照给定规则分割字符串，返回一个由分割出来的子字符串组成的数组。
- localeCompare方法用于比较两个字符串。它返回一个整数，如果小于0，表示第一个字符串小于第二个字符串；如果等于0，表示两者相等；如果大于0，表示第一个字符串大于第二个字符串。
### 数组操作
- length返回数组长度,属性可写，清空数组可数值length为0
- 检查某个键名是否存在的运算符in，适用于对象，也适用于数组。
- for...in循环不仅可以遍历对象，也可以遍历数组，毕竟数组只是一种特殊对象。但不推荐使用for...in遍历数组。
- 数组的遍历可以考虑使用for循环或while循环。
- 数组的forEach方法，也可以用来遍历数组
- 如果一个对象的所有键名都是正整数或零，并且有length属性，那么这个对象就很像数组，语法上称为“类似数组的对象”（array-like object）。
### javascript函数
- 三种声明函数的方法（1、function命令：function后面接函数名；2、函数表达式，采用变量赋值的方法；3、Function 构造函数）
- JavaScript 语言将函数看作一种值，与其它值（数值、字符串、布尔值等等）地位相同。凡是可以使用值的地方，就能使用函数。比如，可以把函数赋值给变量和对象的属性，也可以当作参数传入其他函数，或者作为函数的结果返回。函数只是一个可以执行的值，此外并无特殊之处。由于函数与其他数据类型地位平等，所以在 JavaScript 语言中又称函数为第一等公民。
- 函数的属性和方法（name属性、length属性、toString方法：返回函数的源码字符串）
- 如遇同名参数，则取最后出现的那个值
- arguments对象特别有用（由于 JavaScript 允许函数有不定数目的参数，所以需要一种机制，可以在函数体内部读取所有参数。这就是arguments对象的由来。）
- eval命令的作用是，将字符串当作语句执行。
### 基本类型和引用类型
1. 基本类型(数值、布尔值、字符串、null和undefined)
- 指的是保存在栈内存中的简单数据段
2. 引用类型(对象、数组、函数、正则)
- 指的是那些保存在堆内存中的对象，变量中保存的实际上只是一个指针，这个指针执行内存中的另一个位置，由该位置保存对象
### Math对象常用方法
```
Math.E // 2.718281828459045
Math.LN2 // 0.6931471805599453
Math.LN10 // 2.302585092994046
Math.LOG2E // 1.4426950408889634
Math.LOG10E // 0.4342944819032518
Math.PI // 3.141592653589793
Math.SQRT1_2 // 0.7071067811865476
Math.SQRT2 // 1.4142135623730951
```
```
Math.round(0.1) // 0
Math.round(0.5) // 1
Math.round(-1.1) // -1
Math.round(-1.5) // -1

Math.abs(1) // 1
Math.abs(-1) // 1

Math.max(2, -1, 5) // 5
Math.min(2, -1, 5) // -1

Math.floor(3.2) // 3
Math.floor(-3.2) // -4

Math.ceil(3.2) // 4
Math.ceil(-3.2) // -3

Math.pow(2, 2) // 4
Math.pow(2, 3) // 8

Math.sqrt(4) // 2
Math.sqrt(-4) // NaN

Math.log(Math.E) // 1
Math.log(10) // 2.302585092994046

Math.log(100)/Math.LN10 // 2
Math.log(8)/Math.LN2 // 3

Math.exp(1) // 2.718281828459045
Math.exp(3) // 20.085536923187668

Math.random()生成0到1之间一个随机数，可能等于0，但一定小于1
Math.random() // 0.7151307314634323
// 返回给定范围内的随机数
function getRandomArbitrary(min, max) {
  return Math.random() * (max - min) + min;
}
function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

Math.sin(0) // 0
Math.cos(0) // 1
Math.tan(0) // 0

Math.asin(1) // 1.5707963267948966
Math.acos(1) // 0
Math.atan(1) // 0.7853981633974483

```

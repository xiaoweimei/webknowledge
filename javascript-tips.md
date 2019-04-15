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
### JSON对象
1. 合法的JSON格式
- 复合类型的值只能是数组或对象，不能是函数、正则表达式对象、日期对象。
- 原始类型的值只有四种：字符串、数值（必须以十进制表示）、布尔值和null（不能使用NaN, Infinity, -Infinity和undefined）。
- 字符串必须使用双引号表示，不能使用单引号。
- 对象的键名必须放在双引号里面。
- 数组或对象最后一个成员的后面，不能加逗号。
2. JSON字符串与正常字符串直接的转换
- JSON.stringify方法用于将一个值转为 JSON 字符串
- JSON.parse方法用于将一个值转为JSON字符串还原。
### Number对象
- `(10).toString() // "10"`用于进行数字与字符串的转换，括号内的参数代表进制
- toString方法只能将十进制的数，转为其他进制的字符串。如果要将其他进制的数，转回十进制，需要使用parseInt方法。
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
### 数组操作(标准库)
- Array.isArray(arr),返回一个布尔值，表示arr是否为数组
- arr.valueOf()，表示对该独享求值，不同对象的valueOf方法不尽一致，数组的valueOf方法返回数组本身
- toString方法也是对象的通用方法，数组的toString方法返回数组的字符串形式
- arr.push(1),用于在数组末端添加一个或多个元素，返回添加新元素后的数组长度，pop方法用于删除数组的最后一个元素，返回该元素，两种方法都会改变原数组
- a.shift()方法用于删除数组的第一个元素，并返回该元素；unshift方法用于在数组的第一个位置添加一个或多个元素，并返回添加新元素后的数组长度。和pop、push方法一样，这两种方法同样会改变原数组
- arr.join(' '),join方法以指定参数作为分隔符，将所有数组成员连接为一个字符串返回。如果不提供参数，默认用逗号分隔,数组成员是undefined或null或空位，会被转成空字符串，join方法不改变原数组
- concat方法用于多个数组的合并，将新数组成员，添加到原数组成员的后面，返回一个新数组，原数组不变，如`['hello'].concat(['world'],['!'])`\`[1,2,3].concat(4,5,6)`
- 如果数组成员包括对象，concat方法返回当前数组的一个浅拷贝。所谓“浅拷贝”，指的是新数组拷贝的是对象的引用。
- reverse方法用于颠倒排列数组元素，返回改变后的数组。注意，该方法将改变原数组。如`['a','b','c'].reverse()`
- slice方法用于提取目标数组的一部分，返回一个新数组，原数组不变。如`arr.slice(start,end)`
- splice方法用于删除原数组的一部分成员，并可以在删除的位置添加新的数组成员，返回值是被删除的元素。注意，该方法会改变原数组。`arr.splice(start, count, addElement1, addElement2, ...);`splice的第一个参数是删除的起始位置（从0开始），第二个参数是被删除的元素个数。如果后面还有更多的参数，则表示这些就是要被插入数组的新元素。下面给出两个离子
```
var a = ['a', 'b', 'c', 'd', 'e', 'f'];
a.splice(4, 2) // ["e", "f"]
a // ["a", "b", "c", "d"]
var a = ['a', 'b', 'c', 'd', 'e', 'f'];
a.splice(4, 2, 1, 2) // ["e", "f"]
a // ["a", "b", "c", "d", 1, 2]
```
- 如果只是单纯地插入元素，splice方法的第二个参数可以设为0。
```
var a = [1, 1, 1];
a.splice(1, 0, 2) // []
a // [1, 2, 1, 1]
```
- 如果只提供第一个参数，等同于将原数组在指定位置拆分成两个数组。
```
var a = [1, 2, 3, 4];
a.splice(2) // [3, 4]
a // [1, 2]
```
- sort方法对数组成员进行排序，默认是按照字典顺序排序。排序后，原数组将被改变。`['d', 'c', 'b', 'a'].sort()`\`[4, 3, 2, 1].sort()`
- map方法将数组的所有成员依次传入参数函数，然后把每一次的执行结果组成一个新数组返回，原数组不变
- map方法接受一个函数作为参数。该函数调用时，map方法向它传入三个参数：当前成员、当前位置和数组本身。
```
[1, 2, 3].map(function(elem, index, arr) {
  return elem * index;
});
// [0, 2, 6]
```
```
var numbers = [1, 2, 3];
numbers.map(function (n) {
  return n + 1;
});
// [2, 3, 4]
numbers
// [1, 2, 3]
////上面代码中，map方法的回调函数有三个参数，elem为当前成员的值，index为当前成员的位置，arr为原数组（[1, 2, 3]）。
```
- forEach方法与map方法很相似，也是对数组的所有成员依次执行参数函数。但是，forEach方法不返回值，只用来操作数据。这就是说，如果数组遍历的目的是为了得到返回值，那么使用map方法，否则使用forEach方法。forEach的用法与map方法一致，参数是一个函数，该函数同样接受三个参数：当前值、当前位置、整个数组。
```
function log(element, index, array) {
  console.log('[' + index + '] = ' + element);
}

[2, 5, 9].forEach(log);
// [0] = 2
// [1] = 5
// [2] = 9
```
- some方法是只要一个成员的返回值是true，则整个some方法的返回值就是true，否则返回false。
```
var arr = [1, 2, 3, 4, 5];
arr.some(function (elem, index, arr) {
  return elem >= 3;
});
// true
//--------------------------分割线---------------//
var arr = [1, 2, 3, 4, 5];
arr.every(function (elem, index, arr) {
  return elem >= 3;
});
// false
```
- reduce方法和reduceRight方法依次处理数组的每个成员，最终累计为一个值。它们的差别是，reduce是从左到右处理（从第一个成员到最后一个成员），reduceRight则是从右到左（从最后一个成员到第一个成员），其他完全一样。
```
[1, 2, 3, 4, 5].reduce(function (a, b) {
  console.log(a, b);
  return a + b;
})
// 1 2
// 3 3
// 6 4
// 10 5
//最后结果：15

function substract(prev, cur) {
  return prev - cur;
}
[3, 2, 1].reduce(substract) // 0
[3, 2, 1].reduceRight(substract) // -4
```
- indexOf方法返回给定元素在数组中第一次出现的位置，如果没有出现则返回-1。
- indexOf方法还可以接受第二个参数，表示搜索的开始位置。
- lastIndexOf方法返回给定元素在数组中最后一次出现的位置，如果没有出现则返回-1。
- 链式使用
```
var users = [
  {name: 'tom', email: 'tom@example.com'},
  {name: 'peter', email: 'peter@example.com'}
];

users
.map(function (user) {
  return user.email;
})
.filter(function (email) {
  return /^t/.test(email);
})
.forEach(console.log);
// "tom@example.com"
```
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
### Date对象常用方法
- 一种是将日期转化为字符串方便换算，另一种是将字符串转成日期便于只管查看
**Date对象是 JavaScript 原生的时间库。它以1970年1月1日00:00:00作为时间的零点，可以表示的时间范围是前后各1亿天（单位为毫秒）。**
```
Date()
// "Tue Dec 01 2015 09:34:43 GMT+0800 (CST)"
var today = new Date();
today
// "Tue Dec 01 2015 09:34:43 GMT+0800 (CST)"
// 等同于
today.toString()
// "Tue Dec 01 2015 09:34:43 GMT+0800 (CST)"
```
- Date.now方法返回当前时间距离时间零点（1970年1月1日 00:00:00 UTC）的毫秒数，相当于 Unix 时间戳乘以1000。
```
Date.now() // 1364026285194
```
- 日期转各种数字，牢记Date对象的一系列get*方法就可以了
```
getTime()：返回实例距离1970年1月1日00:00:00的毫秒数，等同于valueOf方法。
getDate()：返回实例对象对应每个月的几号（从1开始）。
getDay()：返回星期几，星期日为0，星期一为1，以此类推。
getYear()：返回距离1900的年数。
getFullYear()：返回四位的年份。
getMonth()：返回月份（0表示1月，11表示12月）。
getHours()：返回小时（0-23）。
getMilliseconds()：返回毫秒（0-999）。
getMinutes()：返回分钟（0-59）。
getSeconds()：返回秒（0-59）。
getTimezoneOffset()：返回当前时间与 UTC 的时区差异，以分钟表示，返回结果考虑到了夏令时因素。
```
- 数字转日期,直接使用new Date(number)就可获得距离1970年1月1日number毫秒的时间

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
### 取消默认与阻止冒泡
```
e.preventDefault() //取消默认行为
e.stopPropagation() //阻止事件冒泡
```
### apply、call、bind有什么作用，什么区别？
1. 三者的相似之处
- 都是用来改变函数的this对象的指向的。
- 第一个参数都是this要指向的对象。
- 都可以利用后续参数传参。
- 不同的是，bind返回的是一个函数，而apply和call相当于对函数的直接调用
-  Function.prototype.bind:
- 作用：bind，返回一个新函数，并且使函数内部的this为传入的第一个参数
```
var fn3 = obj1.fn.bind(obj1);
fn3();
```
- 使用call和apply设置this
- call apply，调用一个函数，传入函数执行上下文及参数
```
fn.call(context, param1, param2...)
fn.apply(context, paramArray)
// 语法很简单，第一个参数都是希望设置的this对象，不同之处在于call方法接收参数列表，而apply接收参数数组
fn2.call(obj1);
fn2.apply(obj1);
```
如：
```
var xj={
  name: "小姬",
  gender: "男",
  age: 24,
  say: function(){
      alert(this.name+" , "+this.gender+" ,今年"+this.age);
  }
}
var xg={
  name: "小古",
  gender: "女",
  age: 18
}
xj.say();
```
- 显示的肯定是小姬 ， 男 ， 今年24。如何用xj的say方法来显示xg的数据呢。对于call可以这样：
- xj.say.call(xg),对于apply可以这样xj.say.apply(xg),对于bind可以这样xj.say.bind(xg)()
- 即call和apply都是对函数的直接调用，而bind方法返回的仍然是一个函数，因此后面还需要()来进行调用才可以。
- 那么对于apply和call的区别呢
- 改写上述例子
```
var xj={
  name: "小姬·",
  gender: "男",
  age: 24,
  say: function(school,grade){
      alert(this.name+" , "+this.gender+" ,今年"+this.age+',在'+school+"上"+grade);
  }
}
var xg={
  name: "小古",
  gender: "女",
  age: 18
}
xj.say('德育中学','三年级');
```
- 显示的是"小姬 , 男 ,今年24,在育才中学上三年级",对于call可以这样:xj.say.call(xg,'德育中学','四年级'),对于apply可以这样xj.say.apply(xg,['德育中学','四年级']),对于bind可以这样xj.say.bind(xg,'德育中学','四年级')()，也可以在调用过程中将参数传递过去，即xj.say.bind(xg)('德育中学','四年级')
### 关于原型、原型链
1. 如下代码中， new 一个函数本质上做了什么？
```
function Modal(msg){
    this.msg = msg
}
var modal = new Modal()
```
- 创建一个新的对象，这个对象的类型是object；
- 查找Modal的prototype上的所有方法、属性，复制一份给创建的Object
- 将构造函数Modal内部的this指向创建的Object
- 创建的Object的proto指向Modal的prototype
- 执行构造函数Modal
- 返回新创建的对象给变量modal


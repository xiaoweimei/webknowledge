### window对象的一些知识
1. window.outerHeight 返回浏览器窗口的外部高度 window.outerWidth返回浏览器窗口的外部宽度
2. window.innerHeight 返回浏览器窗口的内容区域的高度包含垂直滚动条(如果有的话) window.innerWidth返回浏览器窗口的内容区域宽度，包含水平滚动条(如果有的话)
- 举个例子：打开控制台后，向上拖动控制台上面边线，使右侧垂直方向出现滚动条，这个时候，innerHeight的值就会随着你的拖动变得越来越小，而不拖动浏览器外部放大缩小窗口的话，outerHeight是不会改变的。
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
### 数组操作
### 基本类型和引用类型
1. 基本类型(数值、布尔值、字符串、null和undefined)
- 指的是保存在栈内存中的简单数据段
2. 引用类型(对象、数组、函数、正则)
- 指的是那些保存在堆内存中的对象，变量中保存的实际上只是一个指针，这个指针执行内存中的另一个位置，由该位置保存对象

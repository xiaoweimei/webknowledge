### let与var与const
- let声明的变量只在它所在的代码块有效。
- let不存在变量提升
- let不允许重复声明
- const声明一个只读的常量。一旦声明，常量的值就不能改变。
- const声明的变量不得改变值，这意味着，const一旦声明变量，就必须立即初始化，不能留到以后赋值。
- const的不变性指的是变量保存的值不变，对于简单数据来说就是数值不变，对于复合数据来说，则是保存其地址不变，地址里面的数据是可以改变的
- ES5 只有两种声明变量的方法：var命令和function命令。ES6 除了添加let和const命令，后面章节还会提到，另外两种声明变量的方法：import命令和class命令。
```
for (let i = 0; i < 10; i++) {
  // ...
}
console.log(i);
// ReferenceError: i is not defined
如果用var声明的话，输出10
```
```
var tmp = 123;
if (true) {
  tmp = 'abc'; // ReferenceError
  let tmp;
}
上面代码中，存在全局变量tmp，但是块级作用域内let又声明了一个局部变量tmp，导致后者绑定这个块级作用域，所以在let声明变量前，对tmp赋值会报错。
ES6 明确规定，如果区块中存在let和const命令，这个区块对这些命令声明的变量，从一开始就形成了封闭作用域。凡是在声明之前就使用这些变量，就会报错。
```
### 模板字符串
模板字符串使用反引号 (` `) 来代替普通字符串中的用双引号和单引号。模板字符串可以包含特定语法（${expression}）的占位符。
占位符中的表达式和周围的文本会一起传递给一个默认函数，该函数负责将所有的部分连接起来，如果一个模板字符串由表达式开头，则
该字符串被称为带标签的模板字符串，该表达式通常是一个函数，它会在模板字符串处理后被调用，在输出最终结果前，你都可以通过该函数
来对模板字符串进行操作处理。在模版字符串内使用反引号（`）时，需要在它前面加转义符（\）。
### Promise
- 所以我们用Promise的时候一般是包在一个函数中，在需要的时候去运行这个函数
```
function runAsync(){
    var p = new Promise(function(resolve, reject){
        //做一些异步操作
        setTimeout(function(){
            console.log('执行完成');
            resolve('随便什么数据');
        }, 2000);
    });
    return p;            
}
runAsync()
```
- 这时候你应该有两个疑问：1.包装这么一个函数有毛线用？2.resolve('随便什么数据');这是干毛的？
- 在我们包装好的函数最后，会return出Promise对象，也就是说，执行这个函数我们得到了一个Promise对象。还记得Promise对象上有then、catch方法吧？这就是强大之处了，看下面的代码：
```
runAsync().then(function(data){
    console.log(data);
    //后面可以用传过来的数据做些其他操作
    //......
});
```
- 在runAsync()的返回上直接调用then方法，then接收一个参数，是函数，并且会拿到我们在runAsync中调用resolve时传的的参数。运行这段代码，会在2秒后输出“执行完成”，紧接着输出“随便什么数据”。
```
Promise
.all([runAsync1(), runAsync2(), runAsync3()])
.then(function(results){
    console.log(results);
});
```
- 用Promise.all来执行，all接收一个数组参数，里面的值最终都算返回Promise对象。这样，三个异步操作的并行执行的，等到它们都执行完后才会进到then里面。那么，三个异步操作返回的数据哪里去了呢？都在then里面呢，all会把所有异步操作的结果放进一个数组中传给then，就是上面的results。所以上面代码的输出结果就是：
```
Promise
.race([runAsync1(), runAsync2(), runAsync3()])
.then(function(results){
    console.log(results);
});
```
- all方法的效果实际上是「谁跑的慢，以谁为准执行回调」，那么相对的就有另一个方法「谁跑的快，以谁为准执行回调」，这就是race方法，这个词本来就是赛跑的意思。race的用法与all一样，我们把上面runAsync1的延时改为1秒来看一下：
### 声明方式
```
a=1 //声明全局变量
var a=1 //变量提升，建议所有的var写在最前方
//上面两种ES3的，下面两种ES6的
let a=1 //let只能声明一次，重复声明会报错，let作用域在最近的{}之间，如果在let a之前使用a，则报错
const a=1 //const只有一次赋值机会，重复赋值会报错
```
### 一个小函数
`function sum(a){return function pp(b){return a+b}}  //sum(2)(3)返回5`
### async和await
- async function 用于和Promise联用处理异步情况，使语法和结构会更像是标准的同步函数。
- await 操作符用于等待一个Promise 对象。它只能在异步函数 async function 中使用，后面加上return promise对象的函数。
- 一个简单的小例子
```
function yaoshaizi(){
    return new Promise((resolve,reject)=>{
        setTimeout(()=>{
            let n=parseInt(Math.random()*6+1,10)
            resolve(n)
            },3000)    
    })
}
async function test(){
    let n=await yaoshaizi();
    console.log(n)
}
test()//3秒钟后输出1-6的随机数
```

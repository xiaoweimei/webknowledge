- LESS简要介绍
1. 是一种 动态 样式 语言.
2. LESS 将 CSS 赋予了动态语言的特性，如变量,继承,运算,函数.LESS既可以在客户端上运行(支持IE 6+, Webkit, Firefox)，也可以借助Node.js或者Rhino在服务端运行。
- LESS变量
1. 变量允许我们单独定义一系列通用的样式，然后在需要的时候去调用。所以在做全局样式调整的时候我们可能只需要修改几行代码就可以了。
```
// LESS
@color: #4D926F;
#header {
  color: @color;
}
h2 {
  color: @color;
}
/* 生成的 CSS */
#header {
  color: #4D926F;
}
h2 {
  color: #4D926F;
}
```

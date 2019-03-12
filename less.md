- LESS简要介绍
1. 是一种 动态 样式 语言.
2. LESS 将 CSS 赋予了动态语言的特性，如变量,继承,运算,函数.LESS既可以在客户端上运行(支持IE 6+, Webkit, Firefox)，也可以借助Node.js或者Rhino在服务端运行。
- LESS用法的基本规则
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
2. 混合可以将一个定义好的class A轻松的引入到另一个class B中，从而简单实现class B继承class A中的所有属性。我们还可以带参数地调用，就像使用函数一样。
```
// LESS
.rounded-corners (@radius: 5px) {
  border-radius: @radius;
  -webkit-border-radius: @radius;
  -moz-border-radius: @radius;
}

#header {
  .rounded-corners;
}
#footer {
  .rounded-corners(10px);
}
/* 生成的 CSS */

#header {
  border-radius: 5px;
  -webkit-border-radius: 5px;
  -moz-border-radius: 5px;
}
#footer {
  border-radius: 10px;
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
}
```
3. 通过嵌套规则我们可以在一个选择器中嵌套另一个选择器来实现继承，这样很大程度减少了代码量，并且代码看起来更加的清晰。
```

// LESS

#header {
  h1 {
    font-size: 26px;
    font-weight: bold;
  }
  p { font-size: 12px;
    a { text-decoration: none;
      &:hover { border-width: 1px }
    }
  }
}
/* 生成的 CSS */

#header h1 {
  font-size: 26px;
  font-weight: bold;
}
#header p {
  font-size: 12px;
}
#header p a {
  text-decoration: none;
}
#header p a:hover {
  border-width: 1px;
}
```
4. 函数 & 运算 运算提供了加，减，乘，除操作；我们可以做属性值和颜色的运算，这样就可以实现属性值之间的复杂关系。LESS中的函数一一映射了JavaScript代码，如果你愿意的话可以操作属性值。
```

// LESS

@the-border: 1px;
@base-color: #111;
@red:        #842210;

#header {
  color: @base-color * 3;
  border-left: @the-border;
  border-right: @the-border * 2;
}
#footer { 
  color: @base-color + #003300;
  border-color: desaturate(@red, 10%);
}
/* 生成的 CSS */

#header {
  color: #333;
  border-left: 1px;
  border-right: 2px;
}
#footer { 
  color: #114411;
  border-color: #7d2717;
}

```

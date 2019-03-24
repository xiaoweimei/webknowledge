### cursor鼠标手势
1. `cursor : move` 出来十字指示符
2. `cursor: pointer` 出来一个手
3. `cursor: none` 啥也没有
4. `cursor: text` 出来选择文字的符号
5. `cursor: zoom-in` 放大符号
6. `cursor: zoom-out` 缩小符号
7. `cursor : auto` 浏览器根据内容决定指针样式，如文字用text样式
8. `cursor : default` 默认指针，通常是箭头
### 媒体查询代码示例
```
@media (min-width:1000px){
  .box{width:600px}
}
```
### 清除浮动
```
overflow: hidden;//BFC形式清除浮动

.clearfix{
  content:'';
  display:block;
  clear:both;
}
```
### 说说盒模型
```
box-sizing:content-box;// width == 内容区宽度
box-sizing:border-box; width == border 宽度 + 内容区宽度 + padding 宽度
```
### css reset 和 normalize.css 有什么区别？
- reset 重置，之前的样式我不要，a{color: red;}，抛弃默认样式
- normalize 让所有浏览器的标签都跟标准规定的默认样式一致，各浏览器上的标签默认样式基本统一。
### 选择器优先级如何确定？
1. 选择器越具体，优先级越高。 #xxx 大于 .yyy
2. 同样优先级，写在后面的覆盖前面的。
3. color: red !important; 优先级最高。

### BFC是什么?
```
overflow:hidden 清除浮动。（可以用.clearfix 清除浮动，坚决不用 overflow:hidden 清除浮动）
overflow:hidden 取消父子 margin 合并
```
### 水平居中
- 内联：爸爸身上写 `text-align:center;`
- 块级：`margin-left: auto; margin-right: auto;`
### 垂直居中
方法比较多,flex最方便，具体参见之前写的代码
### css加在元素上的超链接
- css中关于超链接的五个属性一般正常顺序为：link，visited，focus，hover，active
### css hack
- 由于不同厂商的浏览器，比如Internet Explorer, Safari, Mozilla Firefox,Chrome等，或者是同一厂商的浏览器的不同版本，如IE6和IE7，对CSS的解析认识不完全一样，因此会导致生成的页面效果不一样，得不到我们所需要的页面效果。这个时候我们就需要针对不同的浏览器写不同的CSS，让它能在不同的浏览中也能得到我们想要的页面效果。
### css hack常用方式
- 条件注释法、IE hack法、选择器前缀法
### 大型项目命名法
- BEM命名法
### position用法
### transition用法
- 基本用法：Transitions可以为一个元素在不同状态之间切换的时候定义不同的过渡效果。比如在不同的伪元素之间切换，像是 :hover，:active 或者通过JavaScript实现的状态变化。
```
//简写语法，属性、时间、速度、延迟
//兼容性：IE11，CSS3
div {
    transition: <property> <duration> <timing-function> <delay>;
}
```
### animation用法
### transform用法

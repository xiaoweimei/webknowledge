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
- 父元素高度不固定，由内部子元素撑开，设置上下padding相等，使子元素在父元素内垂直居中，具体实现比较简单，不多说了
- 绝对定位实现居中，子元素宽高确定情况下设置绝对定位，使用负margin实现垂直居中，
- 绝对定位配合`transform:translate(-50%,-50%)`实现垂直居中，子元素的宽高不确定也可以实现
- `vertical-align:middle`实现垂直居中，关键点，伪元素基线对齐，具体实现，在父元素下创建一个伪元素，设置`content:'';display:inline-block;height:100%;vertical-align:middle`,居中的子元素上设置`vertical-align:middle;display:inline-block`即可
- `vertical-align:middle`配合table-cell实现垂直居中,具体实现父元素上设置`display:table-cell;vertical-align:middle`,子元素上不用考虑
- `display:flex`实现水平居中，具体实现父元素上可以设置`justify-content: center;align-items: center;display:flex`
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
```
position: static | relative | absolute | sticky | fixed //基础语法
```
- absolute定位 不设置top、right、bottom、left有什么效果？
- 元素脱离文档流，但因为没有设置属性导致无法具体定位，紧跟在上个元素之后，但下个元素排列时会忽略此元素
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
- CSS animation属性是如下属性的一个简写属性形式: animation-name, animation-duration, animation-timing-function, animation-delay, animation-iteration-count, animation-direction 和 animation-fill-mode.
- 设置过程中，名称和时间必须设置，要不然看不到效果
```
//举个小例子
//属性初始值as each of the properties of the shorthand:
//animation-name: none
//animation-duration: 0s
//animation-timing-function: ease
//animation-delay: 0s
//animation-iteration-count: 1
//animation-direction: normal
//animation-fill-mode: none
//animation-play-state: running
.name{
  text-align: center;
  margin: 0 auto; 
  display: inline-block;
  animation: .5s zhuandong infinite linear;
}
//animation顺序按照名字、持续时间、速度类型、延迟、运行次数、运行方向、目标样式、是否暂停动画
@keyframes zhuandong {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg);}
}

//再来一个小例子
p {
  animation-duration: 3s;
  animation-name: slidein;
}

@keyframes slidein {
  from {
    margin-left: 100%;
    width: 300%; 
  }

  to {
    margin-left: 0%;
    width: 100%;
  }
}
```
### transform用法
- CSS transforms 通过一系列 CSS 属性实现，通过使用这些属性，可以对 HTML 元素进行线性仿射变形（affine linear transformations）。可以进行的变形包括旋转，倾斜，缩放以及位移，这些变形同时适用于平面与三维空间。
> 只有使用盒模型（Box Model）来定位的元素可以被变换（transformed）。根据一般经验（原文：As a rule of thumb），拥有 display: block 的元素是由盒模型定位的。
### SASS
1. 嵌套选择器
2. 变量
3. mixin
4. placeholder
### CSS的filter属性
- filter CSS属性将模糊或颜色偏移等图形效果应用于元素。滤镜通常用于调整图像，背景和边框的渲染。
- 包括以下一些属性值。blur()设置高斯模糊、brightness()设置亮度、contrast()设置对比度、drop-shadow()设置阴影、grayscale()设置灰度、hue-rotate()设置色相旋转、invert()设置图像翻转、opacity()设置透明度、saturate()设置饱和度、sepia()将图像转化为深褐色
- 可以设置符合属性值
- 兼容性：只能兼容到Edge

### Vue的钩子函数
- created 钩子可以用来在一个实例被创建之后执行代码：
- v-once指令，可以执行一次性地插值，当数据改变时，插值处的内容不会更新，如：
`<span v-once>这个将不会改变: {{ msg }}</span>`
### 使用JavaScript表达式
- 对于所有的数据绑定，Vue.js 都提供了完全的 JavaScript 表达式支持。例如
```
{{ number + 1 }}
{{ ok ? 'YES' : 'NO' }}
{{ message.split('').reverse().join('') }}
<div v-bind:id="'list-' + id"></div>
```
### 指令 (Directives) 是带有 v- 前缀的特殊特性。指令特性的值预期是单个 JavaScript 
表达式 (v-for 是例外情况，稍后我们再讨论)。指令的职责是，当表达式的值改变时，将其产生的连带影响，响应式地作用于 DOM。
- 一些指令能够接收一个“参数”，在指令名称之后以冒号表示。例如，v-bind 指令可以用于响应式地更新 HTML 特性：
`<a v-bind:href="url">...</a>`,一个例子是 v-on 指令，它用于监听 DOM 事件：`<a v-on:click="doSomething">...</a>`
### 指令缩写
```
<!-- 完整语法 -->
<a v-bind:href="url">...</a>
<!-- 缩写 -->
<a :href="url">...</a>
----------------------------
<!-- 完整语法 -->
<a v-on:click="doSomething">...</a>
<!-- 缩写 -->
<a @click="doSomething">...</a>
```
### 计算属性computed和侦听属性watch
### v-if
- v-if、v-else、v-else-if
- v-show 不支持 <template> 元素，也不支持 v-else。
- 因此，如果需要非常频繁地切换，则使用 v-show 较好；如果在运行时条件很少改变，则使用 v-if 较好。
- v-if和v-for最好不要同时使用，如果使用的话，优先级是v-for要比v-if优先级高
- Vue 包含一组观察数组的变异方法，所以它们也将会触发视图更新。这些方法如下：
`push()`
`pop()`
`shift()`
`unshift()`
`splice()`
`sort()`
`reverse()`
- 你可以用 v-model 指令在表单 <input>、<textarea> 及 <select> 元素上创建双向数据绑定。它会根据控件类型自动选取正确的方法来更新元素。尽管有些神奇，但 v-model 本质上不过是语法糖。它负责监听用户的输入事件以更新数据，并对一些极端场景进行一些特殊处理。

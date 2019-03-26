### Object.defineProperty()
- Object.defineProperty() 方法会直接在一个对象上定义一个新属性，或者修改一个对象的现有属性。这个方法执行完成后会返回修改后的这个对象。
- 属性描述对象中 configurable 的值设置为 false 后(如果没设置，默认就是 false)，以后就不能再次通过 Object.defineProperty修改属性，也无法删除该属性。
- delete 操作符用于删除对象的某个属性；如果没有指向这个属性的引用，那它最终会被释放。
- 设置 enumerable 属性为 false 后，遍历对象的时候会忽略当前属性(如果未设置，默认就是 false不可遍历)。
- value 和 writable 叫数据描述符，具有以下可选键值：
1. value：该属性对应的值。可以是任何有效的 JavaScript 值（数值，对象，函数等）。默认为 undefined。
2. writable：当且仅当该属性的writable为true时，该属性才能被赋值运算符改变。默认为 false。
- configurable: true 和 wriable: true 的区别是，前者是设置属性能删除，后者是设置属性能修改
- get 和 set 叫存取描述符，有以下可选键值：
1. get：一个给属性提供 getter 的方法，如果没有 getter 则为 undefined。该方法返回值被用作属性值。默认为 undefined。
2. set：一个给属性提供 setter 的方法，如果没有 setter 则为 undefined。该方法将接受唯一参数，并将该参数的新值分配给该属性。默认为 undefined。
- 数据描述符和存取描述符是不能同时存在的

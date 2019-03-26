### Object.defineProperty()
- Object.defineProperty() 方法会直接在一个对象上定义一个新属性，或者修改一个对象的现有属性。这个方法执行完成后会返回修改后的这个对象。
- 属性描述对象中 configurable 的值设置为 false 后(如果没设置，默认就是 false)，以后就不能再次通过 Object.defineProperty修改属性，也无法删除该属性。
-  delete 操作符用于删除对象的某个属性；如果没有指向这个属性的引用，那它最终会被释放。

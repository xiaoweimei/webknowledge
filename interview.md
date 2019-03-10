### 如何理解前端语义化
### Localstorage,cookie,sessionStorage有什么区别
- 从数据生命周期来看
Cookie一般由服务器生成，可设置失效时间，如果在浏览器中生成，默认是关闭浏览器后失效；localStorage除非主动清空，否则永久保存；sessionStorage进房钱回话下有小，关闭页面或浏览器就会删除
- 从存放数据大小来看
Cookie一般在4K左右；而localStorage和sessionStorage在5M左右
- 从与服务器端的通信来看
Cookie每次都会携带在http头中，所以Cookie过多，会带来性能问题；localStorage与sessionStorage都仅在客户端(浏览器)中保存，不参与服务器的通信
- 从应用方面来看
Cookie一般用来用户记住密码，localStorage一般用于管理购物车，sessionStorage一般用来保存表单信息

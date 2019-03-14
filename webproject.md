### webpack打包工具
- 值得注意的是，webpack 4.0版本出来之后，与之前版本改变有些大，主要在配置文件方面。
1. webpack默认不需要配置文件
2. webpack除了需要安装webpack，还需要安装webpack-cli
3. 从 webpack 4 开始，不再必须定义 entry point(入口点) ：它将默认为`./src/index.js`
4. 它会在`./dist/main.js`中输出模块包，没有的话会自行创建
- 第二个需要注意的是：webpack 4：production(生产) 和 development(开发) 模式
1. 首先需要在package.json中加入下面代码
```
"scripts": {
  "dev": "webpack --mode development",
  "build": "webpack --mode production"
}
```
2. 运行`npm run dev`,输出未压缩的文件
3. 运行`npm run build`,输出压缩文件
4. 可以在package.json中设置输入位置和输出位置，覆盖默认位置
```
"scripts": {
  "dev": "webpack --mode development ./foo/src/js/index.js --output ./foo/main.js",
  "build": "webpack --mode production ./foo/src/js/index.js --output ./foo/main.js"
}
```

### npm安装的一些技巧
```
npm install -g nrm //全局安装
npm install --save nrm //本地安装是你发布之后还依赖的东西，安装完成后版本号和包名称会出现在package.json的dependencies下
npm install --save-dev nrm //本地安装是你开发时候依赖的东西，安装完成后版本号和包名称会出现在package.json的dependencies下
nrm ls //查看源
nrm use taobao //切换源
```
### CommonJs和AMD
- common.js同步规范
- AMD异步的require

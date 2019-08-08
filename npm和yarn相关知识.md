### 配置npm
- `npm config set loglevel http` 让你知道npm发的每一个请求
- `npm config set progress false` 关闭那个进度条
- 为了安装速度更快，运行`npm config set register XXX代表淘宝原地址` 想要恢复原样只需要`npm config delete register`就可以了
### 全局安装yarn
- `npm install -g yarn`
### yarn全局安装和卸载
- `yarn global add parcel-bundler`,``
- `yarn / yarn install` 等同于`npm install` 批量安装依赖
- `yarn add xxx` 等同于 `npm install xxx —save` 安装指定包到指定位置
- `yarn remove xxx` 等同于 `npm uninstall xxx —save` 卸载指定包
- `yarn add xxx —dev` 等同于 `npm install xxx —save-dev`
- `yarn upgrade` 等同于 `npm update` 升级全部包
- `yarn global add xxx` 等同于 `npm install xxx -g` 全局安装指定包
- `yarn global remove xxx` 等同于 `npm uninstall xxx -g` 全局安装指定包
### 生产环境和开发环境
- `npm install -d` 就是`npm install --save-dev` 安装到开发环境 例如 gulp，babel，webpack 一般都是辅助工具
- `npm insatll -s` 就是`npm install --save`  安装到生产环境 如 vue ,react等

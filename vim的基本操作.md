### 常见单词及其意思
yank复制 paste粘贴 quit退出 write写 read读 undo撤销 redo再次做（按键ctrl+r）、replace替换 change修改 delete删除 insert插入 append添加 line一行 find查找 word单词 forward前进 backward后瑞 up向上 down向下
### 四种模式 编辑模式和普通模式、冒号模式（命令模式）、V模式（编辑选区模式）
### vim编辑器之神其特点是
1. Linux自带(nano也是Linux自带的)
2. 不需要鼠标，不用来回切换，速度快
3. 快捷键非常方便
4. 支持宏，支持插件，可以将vim配成集成开发环境
### 在gitbash中输入vimtutor弹出vim的官方教程
- h左，l右，j下k上 hjkl方向键
1. 第一个点：退出
- 先按Esc，再输入:q!强制退出不保存 q退出quit的缩写，!强制
2. 删除
- 按x删除
3. i插入、u撤销、ctrl+r撤销的再做一遍
- 小写i在光标前插入，大写的i在行首插入，小写a在光标后面插入，大写的a在行末插入
### 普通模式下输入冒号后面就可以输入命令了
- ctrl+d向下移动半页、ctrl+u向上翻半页
- dd删除一行、dw删除一个单词、db删除前面的单词、di(删除括号里面的东西不包括括号、da(删除括号里面的东西包括括号、dit删除标签里面的东西比如<div>要删除的内容</div>
- cit删除tag里面内容并同时开启编辑
- cw更改文字
- dd删除一行，3dd删除3行，j往下走一行，8j往下走8行，dw删除一个单词，2dw把dw重复两次，d2w删除两个单词
- v模式下，选择一定东西，按y复制按p粘贴，按大P粘到光标之前

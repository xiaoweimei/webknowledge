### git相关命令
1. `git clone`从远程主机克隆一个版本库
2. `git init`初始化仓库
3. `git add .`将目录文件夹下的文件提交至暂存区，管辖单位为行
4. `git commit -v`提交并且加注释 
5. `git push`用于将本地分支的更新，推送到远程主机。
6. `git pull`取回远程主机某个分支的更新，再与本地的指定分支合并。
7. `git status`查看你的文件在工作目录与缓存的状态
8. `git open`在浏览器打开目标仓库
9. `exit`退出gitbash
10. `git log`展示提交历史
11. `git show 提交历史编号`展示该次提交过程中具体做了什么
### git配置
```
git config --global user.name XXX 全局设置用户名字
git config --global user.email YYY 全局设置用户邮箱
git config --global push.default simple 
git config --global core.quotepath false 防止文件名变成数字
git config --global core.editor "vim" #使用vim编辑提交信息
这些配置都是在~/.gitconfig文件中
```
### gitbash终端下面输入`start 文件名`可以打开改文件，输入软件名可以打开软件
### git、git bash及github的一些知识
1. git bash里面选中即为复制，使用中键进行粘贴
### 跳转目录用z工具，bashrc文件的配置情况
1. alias调整快捷键`alias ga='git add'`修改完成使用`. ~/.bashrc`使之生效
### 常见命令
- Ctrl + R 搜索历史，再次 Ctrl + R 切换
- Ctrl + A 行首
- Ctrl + E 行尾
- Ctrl + B 退后
- Ctrl + F 前进
- Ctrl + W 删一个单词
- Ctrl + Kill 干掉这一行
- Ctrl + Cancel 中断
- Ctrl + Go 退出搜索
- Alt + .复制粘贴上一行最后一个词
### GitBash
- shift+insert粘贴
- 选中复制
- 中键粘贴
### CMD
- 选中再回车复制
- 右键粘贴
### snipaste软件，截图神器
### ClipboardFusion软件，剪切板快捷工具
### ConEmu替代git bash的软件
### nodejs是一个相当于浏览器的平台，向下调用文件API向上为js提供接口

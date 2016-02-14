##Node For Git
右键选择： `git bash here`
参考：http://www.ruanyifeng.com/blog/2014/06/git_remote.html
![theory](./img/theory.jpg)
###心得
有改动别忘了 `commit`
######首先，初始化
```bash
git init
```
######加载文件/文件夹
```bash
git add .
git add file/.
```
######提交文件
```bash
git commit -m "init commit"
"-m为注释"
```
######查看状态
```bash
git status
```
######推送代码
第一次推送时要添加远程的代码库到配置：
```bash
比如：其中origin可变
git remote add origin master https://github.com/winray/Python.git
```
推送代码：
```bash
git push origin master
```
######查看分支
```bash
git branch
git branch -a
```
######创建分支
```bash
git branch fz
```
######切换分支
```bash
git checkout fz
```
######切换分支
```bash
git push origin --delete <branchName>
```
######删除
```bash
删除文件夹：git rm -rf dir
删除文件：git rm file
```
######修改项目名
```bash
在Github页面中，进入要修改的仓库，在页面上方选择“Settings”，即可重命名远程仓库。
本地仓库删除远程仓库："git remote rm origin"
然后按照之前的方法添加新的远程仓库
```

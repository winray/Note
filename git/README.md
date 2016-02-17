##Note For Git
右键选择： `git bash here`
参考：http://www.ruanyifeng.com/blog/2014/06/git_remote.html
![theory](./img/theory.jpg)
###心得
有改动别忘了 `commit`
######首先，克隆
从远程主机克隆一个版本库到自己的主机上
```bash
git clone <网址URL>
```
######管理远程主机
- 克隆版本库的时候，所使用的远程主机自动被Git命名为origin。如果想用其他的主机名，需要用git clone命令的-o选项指定。
  ```bash
  git clone -o name <网址URL>
  ```

- 列出远程主机：`git remote`

- 查看远程主机网址：`git remote -v`

- 查看该主机的详细信息：`git remote show <主机名>`

- 用于添加远程主机：`git remote add <主机名> <网址>`

- 命令用于删除远程主机：`git remote rm <主机名>`

- 命令用于远程主机的改名：`git remote rename <原主机名> <新主机名>`

######git fetch
- 当远程主机有改动，需将改动取回到本地，此时执行：`git fetch <远程主机名>`

- git fetch取回所有分支（branch）的更新。如果只想取回特定分支的更新，可以指定分支名：`git fetch <远程主机名> <分支名>`

- 查看远程分:`git branch -r`

- 查看所有分支：`git branch -a`

- 取回远程主机的更新以后，可以在它的基础上，使用git checkout命令创建一个新的分支：`git checkout -b newBrach origin/master`

- 创建分支
 ```bash
 git branch fz
 ```

- 切换分支
 ```bash
 git checkout fz
 ```

######git pull
- `git pull`命令的作用是，取回远程主机某个分支的更新，再与本地的指定分支合并。它的完整格式稍稍有点复杂。
```bash
git pull <远程主机名> <远程分支名>:<本地分支名>
```
- 比如，取回origin主机的next分支，与本地的master分支合并，需要写成下面这样:
 ```bash
 git pull origin next:master
 ```

- 如果远程分支是与当前分支合并，则冒号后面的部分可以省略。

 ```bash
 git pull origin next
 ```

######推送代码`git push`
- 它的格式与git pull命令相仿
 ```bash
 git push <远程主机名> <本地分支名>:<远程分支名>
 ```

- 如果省略远程分支名，则表示将本地分支推送与之存在"追踪关系"的远程分支（通常两者同名），如果该远程分支不存在，则会被新建。
 ```bash
 git push origin master
 ```

   - 上面命令表示，将本地的master分支推送到origin主机的master分支。如果后者不存在，则会被新建。

- 如果省略本地分支名，则表示删除指定的远程分支，因为这等同于推送一个空的本地分支到远程分支。

 ```bash
 git push origin :master
 等同于
 git push origin --delete master
 ```

    - 上面命令表示删除origin主机的master分支

- 如果当前分支与远程分支之间存在追踪关系，则本地分支和远程分支都可以省略。

 ```bash
 git push origin
 ```

- 如果当前分支只有一个追踪分支，那么主机名都可以省略。

 ```bash
 git push
 ```

- 将本地的所有分支都推送到远程主机，这时需要使用--all选项。

 ```bash
 git push --all origin
 ```

- 如果远程主机的版本比本地版本更新，推送时Git会报错，要求先在本地做git pull合并差异，然后再推送到远程主机。这时，如果你一定要推送，可以使用--force选项

 ```bash
 git push --force origin
 ```

- git push不会推送标签（tag），除非使用--tags选项

 ```bash
 git push origin --tags
 ```

######删除
```bash
删除文件夹：rm -rf dir
删除文件：rm file
```

######修改项目名
```bash
在Github页面中，进入要修改的仓库，在页面上方选择“Settings”，即可重命名远程仓库。
本地仓库删除远程仓库："git remote rm origin"
然后按照之前的方法添加新的远程仓库
```


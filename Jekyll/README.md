##使用 Jekyll 搭建自己的博客
######序言
大二就知道可以使用github搭建自己的博客，what's more，我还学了web2.0的课程，但是（罪恶的词语呀！！！），用博客园的模版还是挺方便的，最重要的还是我懒....囧，所以上到大三才想着自己去弄自己的博客，github上建议我们用Jekyll，那么我就来学学吧

######安装
- 官网windows安装教程：http://jekyll-windows.juthilo.com/

- 步骤如下：

 - 安装ruby：http://rubyinstaller.org/downloads/
 ![](./img/1.png)
 - 然后安装DevKit-mingw64：http://rubyinstaller.org/downloads/
   - 解压到一个目录
   - 进入到这个解压目录
   - `ruby dk.rb init`
   - `ruby dk.rb install`

 - 在命令行下安装Jekyll：`gem install jekyll`
    ![](./img/2.png)

 - windows下还需安装wdm，命令行安装：`gem install wdm`

- 语法高亮：
 - `gem install rouge`
   - 在_config.yml文件中加入：`highlighter: rouge`

 - 使用python的pip安装Pygments
   - 在_config.yml文件中加入：`highlighter: pygments`


######效果
- 命令行输入以下命令：
 - `jekyll new myblog`
 - `cd myblog`
 - `jekyll serve`

![](./img/3.png)


######遇到的错误
-  Error:  Permission denied - bind(2) for 127.0.0.1:4000
 - 端口号被占用，命令行输入：`netstat -an`可以查看端口号被占用情况，只需改变端口号就行，只需打开_config.yml 在最后加上一行 ，比如，`port: 8888`










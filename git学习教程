### 准备工作：
1.要在Arch Linux上下载Git，请打开终端并输入以下命令：
sudo pacman -S git //这将使用Pacman包管理器安装Git。
安装好git后，再配置
git config --global user.name  'archlinux6'  //github上的用户名
git config --global user.email '1239269497@qq.com' //github上的邮箱地址

git config --global user.name 用于设置全局 Git 仓库中的用户名。这意味着在你机器上所有的 Git 仓库都会使用这个用户名。
注意git config命令的–global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

### 基本知识：
1.使用 git init 命令来初始化一个 Git 仓库
git init 该命令执行完后会在当前目录生成一个 .git 目录。(pwd查看当前目录)
git init newrepo 初始化后，会在 newrepo 目录下会出现一个名为 .git 的目录，所有 Git 需要的数据和资源都存放在这个目录中。
$ git add *.c
$ git add README
$ git commit -m '初始化项目版本'
以上命令将目录下以 .c 结尾及 README 文件提交到仓库中。（在 Linux 系统中，commit 信息使用单引号 '，Windows 系统，commit 信息使用双引号 "。）

2.我们使用 git clone 从现有 Git 仓库中拷贝项目（类似 svn checkout）。
克隆仓库的命令格式为：git clone <repo>
如果我们需要克隆到指定的目录，可以使用以下命令格式：git clone <repo> <directory>
比如，要克隆 Ruby 语言的 Git 代码仓库 Grit，可以用下面的命令：
$ git clone git://github.com/schacon/grit.git
执行该命令后，会在当前目录下创建一个名为grit的目录，其中包含一个 .git 的目录，用于保存下载下来的所有版本记录。
如果要自己定义要新建的项目目录名称，可以在上面的命令末尾指定新的名字：
$ git clone git://github.com/schacon/grit.git mygrit

### 常用命令：
git init   - 初始化仓库。
git add    - 添加文件到暂存区。
git commit - 将暂存区内容添加到仓库中。
git clone  - 拷贝一份远程仓库，也就是下载一个项目。
git remote - 查看当前配置的远程仓库。
git remote rm 名字 -删除远程仓库。



### Git 远程仓库(Github)教程：
https://www.runoob.com/git/git-remote-repo.html

注意：我们向GitHub添加公匙出现Key is invalid. You must supply a key in OpenSSH public key format.怎么解决
直接打开文件复制可能会格式不对
解决方法是用cat命令查看文件，或者其他方式查看，总之公钥不能有换行。

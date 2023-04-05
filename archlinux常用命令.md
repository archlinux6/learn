1.pacman介绍:  

    pacman 包管理器是 Arch Linux 和其他主要发行版如 Red Hat 和 Ubuntu/Debian 之间的主要区别之一。 
     
    pacman 可以将包列表与软件库同步，它能够自动解决所有所需的依赖项，以使得用户可以通过一个简单的命令下载和安装软件。

2.可以用以下形式的代码来安装一个或者多个软件包：  

`pacman -S` 软件包名1 软件包名2 ...  

-S 选项的意思是同步synchronization，它的意思是 pacman 在安装之前先与软件库进行同步

3.卸载一个包，并且删除它的所有依赖。  

`pacman -R` 软件包名

4.安装git  

`sudo pacman -S git`

5.下载QQ  

`yay -S linuxqq ` // 百度搜索AUR 进入之后找到 Package Search:QQ 找包名

6.`tab` 命令补齐  >键 也可以

注意:  

`cd ~`  或 `cd ~/`  

是在主文件夹下，里面有  

    cslg     Documents  learn  Music     Public           Templates  单词本.xlsx  yes.pub
    Desktop  Downloads  miku   Pictures  runoob-git-test  Videos     yes

`cd / `  

是在根文件夹下，里面有  

    bin  boot  dev  etc  home  lib  lib64  lost+found  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

快捷键：  

`shift + alt + t` 运行终端

其他命令：  

`pacman -Syu `      同步源，并更新系统

### 1.安装Git
`sudo pacman -S git`    

`git -v`   
验证是否安装好    
出现版本号安装成功

Git 是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。
### 2.安装Node.js
`sudo pacman -S nodejs npm`  
安装 nodejs npm
  

Node.js 是一个 javascript 运行环境  

`node -v`  

`npm -v`  
验证是否安装好  
出现版本号安装成功   

一些npm命令 ： 

`npm init`  
这个会生成一个package.json文件  
这个文件主要是用来记录这个项目的详细信息  

文件内容为：
```
package name:                     项目名
version:                          版本号
description:                       对项目的描述
entry point:                      项目的入口文件（一般你要用那个js文件作为node服务，就填写那个文件）
test command:                     项目启动的时候要用什么命令来执行脚本文件（默认为node app.js）
git repository:                    
keywirds：                       
author:                       
license:                        
```

### 3.安装Hexo
`sudo npm install hexo-cli -g`  

使用 npm 安装 Hexo


Hexo 是一个快速、简洁且高效的博客框架。

### 4.注册github配置git

注册完github,   
新建一个仓库 名字是 `用户名/用户名.github.io `   

配置git
```
git config --global user.name  'archlinux6'  //github上的用户名  
git config --global user.email '1239269497@qq.com' //github上的邮箱地址  
```
`git config --global user.name`用于设置全局 Git 仓库中的用户名。这意味着在你机器上所有的 Git 仓库都会使用这个用户名。
注意git config命令的–global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

生成 SSH Key：
```
$ ssh-keygen -t rsa -C "1239269497@qq.com"
```
邮箱为你在 Github 上注册的邮箱，之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。

成功的话会在 ~/ 下生成 .ssh 文件夹，进去，打开 id_rsa.pub，复制里面的 


回到 github 上，进入 Account => Settings（账户配置）。   
左边选择 SSH and GPG keys，然后点击 New SSH key 按钮,title 设置标题，可以随便填，粘贴在你计算机上生成的 key。

` ssh -T git@github.com`
连接到github

### 5.开始
```
mkdir blog //创建文件夹 blog
cd blog    //进入blog文件夹里
hexo init  //初始化hexo 文件夹
//……初始化后
> ls       //查看文件夹里文件
node_modules  source  _config.landscape.yml  package.json
scaffolds     themes  _config.yml            package-lock.json
> code .   //用vscode打开当前目录下的所有文件
```
_config.yml
网站的 配置 信息，您可以在此配置大部分的参数。  

修改 _config.yml 文件 将 deploy 修改为以下 repository 为自己的博客地址，如：
```
deploy:
  type: git
  repository: https://github.com/archlinux6/archlinux6.github.io
  branch: master
```
接着
```
> hexo s  //在本地运行
> hexo d  //部署到网站
```  
在Hexo项目根目录下  
 选择github 安装
```
git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly
```
在themes文件夹下出现butterfly文件夹

修改Hexo配置  
```
// 在Hexo的 _config.yml  文件里修改主题
theme: butterfly
```
安装依赖   

 ```
//butterfly使用需要安装 pug 以及 stylus 的渲染器
npm install hexo-renderer-pug hexo-renderer-stylus --save
```

### 参考：https://hexo.io/zh-cn/
hexo的一些命令：
```
hexo init # 初始化项目
hexo g # 生成静态文件
hexo clean # 清楚静态文件
hexo d # 推送静态文件至 git远程仓库
hexo s # 本地预览项目
```

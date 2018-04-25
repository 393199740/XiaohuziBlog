title: 基于hexo与github搭建个人博客
author: xiaohuzi
tags:
  - Hexo
categories:
  - 博客
date: 2018-04-24 10:00:00
---
#### 基于hexo与github搭建个人博客 ####

----------

- ##### 为什么用Hexo搭建独立博客？ #####
 
 Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

- ##### 为什么使用github #####
 
 gitHub是一个面向开源及私有软件项目的托管平台，因为只支持git 作为唯一的版本库格式进行托管，故名gitHub。

----------

- ##### 安装 nodejs #####

 既然是基于 nodejs 的，那第一步毫无疑问就是先安装 nodejs 了。来到 nodejs 的官网 https://nodejs.org/ 下载安装，搞定。

- ##### 安装 git ##### 

 git官网地址:https://git-scm.com/
 git是什么？ 
 git是目前世界上最先进的分布式版本控制系统（没有之一）。 
了解更多，[参考git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
 
- ##### 安装 hexo #####
  ```
npm install -g hexo-cli
npm install hexo --save
hexo -v #查看是否安装成功
  ```
  等待中...直到全部安装成功...
  
- ##### 注册 github账号 #####
 
 新建一个repository仓库地址.用来管理你自己的博客...
 
 ![upload successful](\images\pasted-6.png)
 
  ```
  注意:username必须和你的用户名相同...
  ```
- ##### 开启gh-pages功能 #####

 点击界面右侧的Settings，你将会打开这个库的setting页面，向下拖动，直到看见GitHub Pages，如图：
 
 ![upload successful](\images\pasted-7.png)
 
 点击Automatic page generator，Github将会自动替你创建出一个gh-pages的页面。 如果你的配置没有问题，那么大约15分钟之后，yourname.github.io这个网址就可以正常访问了~ 如果yourname.github.io已经可以正常访问了，那么Github一侧的配置已经全部结束了。
 
- ##### 利用hexo建立博客网站.#####
  
  1. ###### 初始化hexo ######
    执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件
  ```
	 hexo init <folder>   #建立博客文件夹目录
	 cd <folder>        #进入目录
	 npm install        #安装组件
  ```
    ![upload successful](\images\pasted-9.png)
    
    ![upload successful](\images\pasted-10.png)
    
    初始化完成...
    
    官方文档(https://hexo.io/zh-cn/docs/setup.html)
    
   2. ###### 首次体验hexo ######
     
     Hexo 3.0 把服务器独立成了个别模块，您必须先安装 hexo-server 才能使用。
     
     ```
     npm install hexo-server --save    #安装hexo-server

     ```
     ```
     hexo clean  #(清理命令)
     hexo g   #(生成静态文件命令 hexo generate缩写)
     hexo s    #(启动服务 hexo server缩写)
     ```
     好，了解命令之后开始我们的操作。
     ```
      hexo clean
      hexo g
      hexo s --port 8777 （指定端口，默认4000）
     ```
     这时候,看到如下界面就成功了！
     
     ![upload successful](\images\pasted-11.png)
     
     我们去浏览器中打开http://localhost:8777/ 就会看到如下图：
     
     ![upload successful](\images\pasted-12.png)
     
     到这里本地的博客已经搭建完成。
     
- ##### 把本地 hexo 博客项目上传 github #####
  
  ```
  npm install hexo-deployer-git --save     #安装部署所需要的包

  ```
  ```
  hexo d   #(发布到github仓库)
  ```
  需要修改 _config.yml 站点配置文件
  
 ![upload successful](\images\pasted-15.png)
 
 部署：
 
 ```
 hexo deploy    #部署命令
 ```
 ![upload successful](\images\pasted-17.png)
 
 打开你自己的 github 博客地址，可以访问啦...
  
  如图:
  
 ![upload successful](\images\pasted-18.png)
 
 完毕!
 
- #####  更改 hexo 皮肤 #####
  
  官方网站:https://hexo.io/themes/
  
  ```
  git clone https://github.com/iissnan/hexo-theme-next themes/next
  ```
  克隆 hexo-theme-next 皮肤到themes文件夹下 起名为next文件夹
  
  命令执行成功后 需要修改 站点配置文件 _config.yml,找到里面的 theme，改为
theme: next
这时再运行一次 hexo s ，看看主题有没有生效吧。

- ##### 最后说一下 hexo 可视化编辑 #####
  
  markdown 语法:
  
  官方文档:http://markdownpad.com/
  
  1. hexo-admin插件
  2. http://marxi.co/
  3. https://typora.io/
  
  对比后发现 hexo-admin 非常好用,可能是因为他是hexo自己的东西，能够管理文章，添加分类和标签，也可以一键部署到pages。非常好用...
  
  开始吧..
  
  ```
  npm install --save hexo-admin
  ```
  执行命令后，下载了 hexo-admin 插件
  
  注意最好在博客的目录下执行。
  
  ```
  hexo server --port 8777
  ```
  浏览器打开:http://localhost:8777/admin
  
  OK!!  进去之后就可以管理你当前博客的文章了...
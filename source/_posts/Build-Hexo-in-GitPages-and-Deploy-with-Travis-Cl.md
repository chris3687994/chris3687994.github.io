title: 在GitPages上搭建Hexo博客+Travis Cl自动部署
date: 2019-04-14
tags: 
    - hexo
    - 博客
    - Travis Cl
    - GitPages
categories: 技术
---

不久前在GitPages上搭建了属于自己的Hexo博客，折腾了好几天，也是翻了很多的资料，终于大功告成，再配合上Travis Cl自动部署，给我的感觉就是两个字，舒服～所以呢，我打算把部署的过程记录下来，出一个小教程（默认在Windows系统上），供其他人参考，如有不当的地方请批评指正，多多指教啦～

# 本地安装Hexo博客

## 搭建环境

其实这个大家去访问[Hexo](https://hexo.io/zh-cn/)官方网站阅读以下文档就能搭建好环境了，主要是安装Node.js和Git。首先下载并安装[Node.js](https://nodejs.org/en/)和[Git](https://git-scm.com/)的Windows版本，前者是Hexo的运行环境，后者用来管理你博客的工具，安装完成后使用打开命令行界面，输入：  
```
node -v
git --version
```
如果出现如下界面，那么说明安装是正确的:  

![查看软件版本](https://wx2.sinaimg.cn/large/006fVPCvly1g22lu92l8tj31id0t6q4f.jpg)  

此时你的桌面上会出现一个名为Git Bash的快捷方式，运行它，运行如下命令：
```
cd /x  //x为你的盘符
mkdir hexo && cd hexo  //创建一个名为hexo的文件夹并且进入，这个目录会存放你所有Hexo文件
npm install -g hexo-cli  //下载并安装Hexo
```
完成后使用`hexo -v`检验一下，如果出现版本信息，那么代表你的Hexo安装成功！接下来，在你刚才的目录下使用`hexo init`命令，它会把hexo的文件下载到当前文件夹下，最后目录结构如下：
```
.
├── _node_modules  \\存放一些依赖文件
├── scaffolds  \\ 内存放模板文件 
├── source
|   ├── _drafts  \\存放草稿
|   └── _posts  \\存放文章
├── themes  \\主题文件夹
├── .gitignore  \\存储git时忽略的文件夹或文件
├── _config.yml  \\hexo的配置文件
├── package.json  \\记录软件相关信息
└── package-lock.json
```

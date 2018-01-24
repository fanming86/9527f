---
date: 2017-11-19 22:13:00

title: hexo搭建博客遇到的坑
tags: [hexo,linux]
categories: hexo
---


电脑重装系统后，克隆部署hexo博客的源码时，发现主题文件夹是一个空的文件夹，开始以为时下拉的时候出问题了。折腾了好一会儿才发现git仓库里面的同名文件夹打不开，变成了一个类似于文件的图标；
幸好有备份项目，打开项目，进到theme文件夹，看到里面文件一个不少，于是又重新上传。结果还是如此，上传到github就打不开文件夹

原因可能是这样的：
我的主题文件是直接从git上面拉下来的，里面包含别人仓库的配置
查看远程分支：
![这里写图片描述](http://img.blog.csdn.net/20180124112731559?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMzU2MjYyNQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

最后，重新创建了文件夹，并将之前配置好的文件复制过来，在次上传就OK了

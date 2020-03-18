---
layout: post
title: 配置yilia
date: 2019-06-13 00:41:30
tags: [blog, hexo]
---
经过一些对比，决定选用yilia作为博客的主题，这个主题比较素雅，不太花哨，移动端的表现也比较让人满意。另外主题本身也有一些其他诸如分享微信，微博，打赏之类的功能还有待探索。

关于主题的配置分别在主题目录下的_config.yml文件和Hexo的_config.yml文件内，作者的注释写的很赞，对照着页面的内容，大部分可以配置的不错，还有一些诸如打赏，分享微博，RSS之类的功能还需要以后慢慢完善。
<!--more-->

## 1.配置网页图标（favicon）
***方法一***

图片放到hexo/source/img文件夹下
找到hexo\themes\modernist\layout_partial\head.ejs，设置为

```
<% if (theme.favicon){ %>
    <link rel="icon" href="/img/favicon.ico">
  <% } %>
```

***方法二（亲测可用）***

将图片添加到文件夹themes/yilia/source/img下
配置文件中直接引用即可。路径为 themes/yilia/_config.yml，找到如下即可
```
# 网页图标
favicon:  /img/head.jpg
```
## 2.配置头像图片
同样将图片资源添加到文件夹themes/yilia/source/img下，并在主题配置文件下添加如下配置
```
# 头像图片
avatar:  /img/avatar.jpg
```
## 3.增加不蒜子统计
**安装不蒜子脚本**
在 themes\yilia\layout\_partial\after-footer.ejs最后添加
```
<script  async  src="https://busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```
**添加统计网站访问量**
修改 themes\yilia\layout\_partial\footer.ejs，包括访客数和站点访问总量
```
# PV方式，单个用户连续点击 n 篇，记录 n 次记录值 
<span id="busuanzi_container_site_pv"> 本站总访问量<span id="busuanzi_value_site_pv"></span>次</span> 
# UV方式，单个用户连续点击 n 篇，记录 1 次记录值 
<span id="busuanzi_container_site_uv"> 本站访客数<span id="busuanzi_value_site_uv"></span>人次</span>
```


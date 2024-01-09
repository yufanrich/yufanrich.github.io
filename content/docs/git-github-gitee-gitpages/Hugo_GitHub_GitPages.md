### 搭建自己的博客
#### 1 背景
```
之前也用到过博客园、开源中国、csdn等常用博客网站,但是总是感觉很分散。
再加上想重新梳理一下自己的知识体系,就萌生了重新整理一遍博客内容的想法。
这个时候,想到自己经常看到的一些有些的博客，好像有很多都是个人网站。
于是，就准备动手搭建自己的博客网站了。
本文:主要采用Hugo+GitHub+GitPages.
(ps:GetHub可以替换为Gitee)
(ps:Hugo也有同类替代品,如Hexo、Jekyll(GitHub默认首选))

其实:后面用的多了,一个项目可以同时提交到Gitee和GitHub后,完全可以同时部署在Gitee和GitHub.
(ps:一个项目如何同时提交到Gitee和GitHub? vx公众号:小程三千问)
```

### 2 实战

#### 2.1 Hugo

##### 2.1.1 hugo安装
```
官网参考:https://gohugo.io/installation/macos/
macOs : brew install hugo
```

##### 2.1.2 hugo快速入门
```
# 创建一个新的网站（本地）
hugo new site quickstart && cd quickstart

# 拉取并设置主题
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo theme = \"ananke\" >> config.toml

# 创建一篇新文章
hugo new posts/my-first-post.md

# 构建静态网站文件，并启动 HTTP 服务
hugo server -D
执行完上述操作，就可以通过浏览器访问 http://localhost:1313/ 
可以看到自己刚创建的网站与第一篇文章
```
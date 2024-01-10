# 搭建自己的博客
# 1 背景
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

# 2 实战

## 2.1 Hugo

### 2.1.1 hugo安装
```
官网参考:https://gohugo.io/installation/macos/
macOs : brew install hugo
```

### 2.1.2 hugo快速入门
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

### 2.1.3 hugo 核心目录解释
```
content: 文章存放目录
static: 静态资源存放目录, 如：图片、样式文件、脚本文件等
data: 数据模板目录，
      Hugo静态网站不会连接像MySQL这样的数据库，而此目录保存的数据相当于Hugo使用的数据库，
      生成过程用到的配置数据，可以用YAML, JSON, TOML等格式文件存储
themes: 网站主题存放目录
config.toml : 网站的配置文件，可配置网站名称、关键字、插件等

congit.toml :有一个比较重要的配置 baseURL = 'https://{you_name}.github.io/'
      推送到github时且需要借助git pages 的能力,必须修改为如上格式。
```

## 2.2 git 仓库
### 2.2.1 建立仓库的要求
```
1 仓库必须时public
2 仓库名称必须是: {you_name}.github.io
```


## 2.3 GitHub Action 实现代码提交后自动部署
### 2.3.1 创建gh-pages.yml文件
```
本地项目根目录中创建.github/workflows/gh-pages.yml
ps:.github/workflows 固定
    gh-pages:名称随意,但是.yml固定
```
### 2.3.2 gh-pages.yml 示例
```
name: github pages

on:
  push:
    branches:
      - master  # Set a branch to deploy
  pull_request:

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
        with:
           submodules: true
           fetch-depth: 0

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          # extended: true

      - name: Build
        run: hugo --minify

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        if: github.ref == 'refs/heads/master'
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```
```脚本解释


```

### 2.3.3 开启git pages
```
Build and deployment
必须指定为:Deploy form a branch
Branch 
必须指定为:gh-pages /root(代表根目录)

```

### 2.4 新建博客(md文档),提交git即可
1 本地生成网站源代码
```
hugo 

ps:注意 不是hugo server (这只是本地模拟,然后访问http://localhost:1313/ 看效果)
   hugo 才会再public文件夹下生成网站源代码
```
2 提交git后,会自动触发git actions,从而把Hugo的产出输出到指定分支,且git page 会自动监听变化,重新部署网站
# 快速排版自己博客的图片
## 背景
在前两篇文章中,我们搭建了自己的博客,并美化了自己的博客。
但是博客更重要的是内容,一般我们使用markdown来编写博客内容。
但是markdown对于图片处理的不是很友好,每次发布公众号时都需要
替换本地图片到网络图片。如果能自动替换就好了......

## 1 选择图床服务器
### 1.1 备选服务器及理由
一般可以选七牛云、腾讯云、有道云笔记等,本着简单至上的原则,我们选择程序员
都熟悉的gitee和github。

### 1.2 搭建github图床
新建仓库
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/001.png)

新建令牌
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/20240205144742.png)

手动上传
```bash
借助github网页端上传或者git客户端操作
```

### 1.3 搭建gitee图床
新建仓库
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/001.png)

新建令牌
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/002gitee%E7%94%9F%E6%88%90%E4%BB%A4%E7%89%8C.png)

手动上传
```bash
借助gitee网页端上传或者git客户端操作
```

以上,虽然我们搭建了一个简单的图床,但是每次需要手动截图，保存之后，上传图片,
且需要手动 获取图片最终的网路地址,比较费事。
有没有办法截图之后，自动上传到图床，且自动返回最终的网路地址呢？

## 2 PicGo安装 （自动上传到图床服务器:不用手动上传）
### 2.1 简介
官网地址:https://github.com/Molunerfinn/PicGo

![](https://github.com/yufanrich/yufanimgs/blob/master/img/003piggo%E7%AE%80%E4%BB%8B.png?raw=true)

### 2.2 安装 npm 以及 gitee 插件
```bash
brew install node
npm在Node v0.6.x版本之后，内建于Node系统.安装node就自带npm
node -v 
npm -v 
```
### 2.3 gitee插件进行安装
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/004.png)

### 2.4 gitee 及github配置
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/005%E5%AE%89%E8%A3%85%E6%8F%92%E4%BB%B6%E5%90%8E%E9%87%8D%E5%90%AF.png)

```json
gitee 和 github配置大同小异,github配置路径时是imgs/,而gitee是/imgs
```

### 2.5 pigco上传日志查看
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/20240205150009.png)

### 2.6 picgo上传效果展示
比如我们截图在剪贴板的图片可以直接上传,
且上传之后会把上传后的url自动塞入到剪贴板,右键粘贴即是图片地址。
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/20240205150123.png)

## 总结
科技永远是第一生产力，当你还在花费几个小时终于完成一篇公众号时,
而别人已经借助以上三篇内容实现量化公众号文章的编写，且风格更统一，
效果更好。希望有了这三板斧,大家都可以实现公众号文章爆款。
下一篇：将会对我所使用的涉及建立博客网站以及写博客的工具做一个总结。



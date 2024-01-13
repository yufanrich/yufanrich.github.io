# 美化自己的博客
# 1 背景
```
上一篇内容,我们学习了如何搭建一个自动化部署的博客网站。
我们继续来从以下几个方面来优化我们的个人博客网站。
vx search :小猿code
```

# 2 实战

## 2.1 选择一个自己喜欢的主题

```
# 访问主题官网
https://themes.gohugo.io/

# 选中一个喜欢的主题,后点击跳转过去
https://github.com/alex-shpak/hugo-book

# 学习官网如何设置此主题
git submodule add https://github.com/alex-shpak/hugo-book themes/hugo-book
theme = 'hugo-book'
```


## 2.2 文章设置层级结构
```
模仿层级结构进行编辑
content/menu/index.md with the content:

启用菜单
hugo.toml
[params]
BookMenuBundle = '/menu'
```

## 2.3 md文档引入图片
```bash
针对此hugo-book的主题,默认就是在static即可
![](logo.jpg)
```
![](/logo.jpg)

## 2.4 设置网站联系人及介绍

## 2.5 网站支持中英文搜索
```bash
- id: bookSearchConfig
  translation: |
    {
      split: " "
    }
```



欢迎wx search:小猿code
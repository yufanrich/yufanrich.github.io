# 总计个人建站所用到的工具类
## 背景
在前面三篇文章中,我们分别
从小白建站:https://mp.weixin.qq.com/s/bVO-GGXNxGSjV-qd-a3CvQ
美化站点(美化排版):https://mp.weixin.qq.com/s/UX1wYyKgEg8RVGs7fhd_Zg
美化图片排版(搭建图床服务器):https://mp.weixin.qq.com/s/p_ad-eOF7Ss61LVM7GYvwA
三个方面分别对我们的内容进行了优化,并实现了一份内容编写,
同时支持个人网站和公众号文章双部署。
下面我们对所用到的工具进行一个汇总和总结,让我们更熟练的使用各个工具


## 1 搭建个人网站和公众号所用工具汇总
### 1.1 流程图
![](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/20240205%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2%E5%92%8C%E7%BD%91%E7%AB%99%E5%B7%A5%E5%85%B7%E9%9B%86%E5%90%88.drawio.png)
### 1.2 工具介绍
Hugo:用于建立网站(纯html网站,我们使用md编写,会帮我们转换到html)

GitHub+Gitee
1）存储源代码
2）借助Git Actions 实现代码提交后,进行网站自动部署
3）借助Git Pages 实战网站部署,以及免费使用其自身提供的二级域名
4）作为免费的图床服务器

PicGo:图片上传工具，支持自动上传到多个图床

DrawIo:绘图工具

Markdown:博客内容编写

微信公众号Markdown编辑器:实现md文档转换公众号文章央视排版的能力

借助以上工具，我们实现了本地md文档的编写,同时支持个人网站和公众号文章双部署。
接下来，就是愉快的创作时间了。

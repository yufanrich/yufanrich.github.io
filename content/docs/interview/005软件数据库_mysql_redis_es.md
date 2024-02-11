# mysql
## mysql计算题
[1 mysql自增id超过上限制(有无使用自增主键)](https://mp.weixin.qq.com/s/k0w5jKwR-e2YroArRopwWg)
[2 mysql为什么建议2000万数据:主键类型/b+树索引](https://mp.weixin.qq.com/s/wEeamF6erUipFQnE4DrwlA)
[3 为什么不能使用uuid,单表自增-分布式优化的雪花算法id](https://mp.weixin.qq.com/s/oz20iPdqNp3pHvFoh0zwMA)

## 基础篇
[mysql一行记录是怎么存储的](https://xiaolincoding.com/mysql/base/row_format.html)
[mysql数据页分为哪几个部分](https://mp.weixin.qq.com/s/wEeamF6erUipFQnE4DrwlA)
[mysql数据页结构以及如何在单页和多个数据页之间检索](https://mp.weixin.qq.com/s/QHA80Y2G5UxuRhLT9LBMDg)

## 索引篇
[多个数据页时,抽象特殊的数据页-即索引页及innodb引擎的b+树](https://mp.weixin.qq.com/s/QHA80Y2G5UxuRhLT9LBMDg)
![索引也是存在磁盘上](https://raw.githubusercontent.com/yufanrich/yufanimgs/master/img/202402/20240211_索引存储位置.png)
[为什么选择b+树,io及范围查询](https://mp.weixin.qq.com/s/q2cv-cF8LszowOYmmvi97g)

# redis
## 1 概念篇
1 redis是什么,基于什么语言编写,常见的使用场景是什么，常见的数据类型有哪些，与memcached的区别
[链接](https://www.zhihu.com/question/485080754/answer/2966086644)

## 2 数据类型篇
[2.1 常见的数据类型有哪些，以及是如何实现的？](https://xiaolincoding.com/redis/base/redis_interview.html#%E4%BA%94%E7%A7%8D%E5%B8%B8%E8%A7%81%E7%9A%84-redis-%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E6%98%AF%E6%80%8E%E4%B9%88%E5%AE%9E%E7%8E%B0)
[2.2 redis为什么要重新定义字符串 sds (同上)]

## 3 持久化篇
https://xiaolincoding.com/redis/

## 4 过期策略与内存淘汰策略

## 5 高并发:网络模型篇 (单机10万qps)

## 6 高可用:集群

## 7 缓存常见问题(雪崩、穿透、击透、双写多数据源一致性问题)

## 8 数据是如何存取的（一个大的交互图）:需要后续自己完善
name ---redis里面如何存储--集群--如何读取
https://xiaolincoding.com/redis/data_struct/data_struct.html#%E9%94%AE%E5%80%BC%E5%AF%B9%E6%95%B0%E6%8D%AE%E5%BA%93%E6%98%AF%E6%80%8E%E4%B9%88%E5%AE%9E%E7%8E%B0%E7%9A%84

```

# es

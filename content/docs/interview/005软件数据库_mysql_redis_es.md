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

## 事务篇
### 问题串联
```bash
事务:有限的数据库操作序列？
四大特性以及隔离级别,以及mysql默认的隔离级别和大厂默认的隔离级别（间隙锁容易导致死锁）？
幻读的本质,幻读与不可重复读分别侧重什么？查询条数和查询内容？

```
### 问题详解
[事务隔离机制 脏读(脏) 不可重复读(两次读取的不一致) 幻读(第一次未select到,插入却冲突) 快照读 当前读](https://mp.weixin.qq.com/s/NI8R0BFfeOYaazzZw7AOeg)
```
一般而言,幻读是指查询条数不一致。（
  比如第一次没查询到(普通select)，但是插入时提示冲突（有一条）0和1不一样(delete和update默认都是当前读)）
  幻读问题的本质是:快照读和当前读混用了。如果都是快照读(没有更新)或者都是当前读（select for update加锁）就不会有问题
不可重复读是指查询数据的内容不一致

```

[幻读的本质](https://mp.weixin.qq.com/s/Ny-29jwQ02rDhEVuLoSxmA)
[rr级别由于mvcc+间隙锁基本解决了大部分幻读，但是极端场景的不能解决，因为其本质还是快照读与当前读，不能完全解决]()
[名词解释](https://mp.weixin.qq.com/s/NI8R0BFfeOYaazzZw7AOeg)
[mysql的默认隔离级别是RR,为什么不是RC.主要考虑bin log同步sql原文导致的不一致问题，但是为什么大厂又是默认RC](https://mp.weixin.qq.com/s/IW07pFvlrNnT4HYxWZkj0w)
[什么是快找读,什么是read view](https://mp.weixin.qq.com/s/IW07pFvlrNnT4HYxWZkj0w)
[(可见性规则判单 一问搞懂mvcc)三类并发场景及mvcc并发控制-主要是解决读写冲突及举例隐藏字段如何进行可见行判断的](https://mp.weixin.qq.com/s/ZVsuqpaKTAMeA0SyqRbqyw)

## 锁篇
[间隙锁到底怎么加(间隙锁是双开)，在于有没有索引，next-key临键锁就是gap+杭锁(左开右闭)](https://mp.weixin.qq.com/s/te62kTnMBexAC-P0TF0j_A)
[mysql锁到底锁的什么？RR级别下才有的next-key lock和gap lock,加锁规则：两个原则，两个优化，一个bug](https://mp.weixin.qq.com/s/fmSHG0SejfD0IdnpIYHT9w)
[mysql加锁的两个决定因素 隔离级别以及记录是否存在](https://mp.weixin.qq.com/s/TEXjgA85vUrvx2Q6O5Id1A)

# redis
## 1 概念篇
1 redis是什么,基于什么语言编写,常见的使用场景是什么，常见的数据类型有哪些，与memcached的区别
[链接](https://www.zhihu.com/question/485080754/answer/2966086644)

## 2 数据类型篇
[2.1 常见的数据类型有哪些，以及是如何实现的？](https://xiaolincoding.com/redis/base/redis_interview.html#%E4%BA%94%E7%A7%8D%E5%B8%B8%E8%A7%81%E7%9A%84-redis-%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E6%98%AF%E6%80%8E%E4%B9%88%E5%AE%9E%E7%8E%B0)
[2.2 redis为什么要重新定义字符串 sds (同上)]

## 3 持久化篇
https://xiaolincoding.com/redis/
[epoll源码分析一个对象两个数据结构三个api接口](https://zhuanlan.zhihu.com/p/552580039)

## 4 过期策略与内存淘汰策略

## 5 高并发:网络模型篇 (单机10万qps)

## 6 高可用:集群

## 7 缓存常见问题(雪崩、穿透、击透、双写多数据源一致性问题)

## 8 数据是如何存取的（一个大的交互图）:需要后续自己完善
name ---redis里面如何存储--集群--如何读取
https://xiaolincoding.com/redis/data_struct/data_struct.html#%E9%94%AE%E5%80%BC%E5%AF%B9%E6%95%B0%E6%8D%AE%E5%BA%93%E6%98%AF%E6%80%8E%E4%B9%88%E5%AE%9E%E7%8E%B0%E7%9A%84

```

# es

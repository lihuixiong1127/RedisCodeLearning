# 目录

1. 第一阶段 阅读Redis的数据结构部分，基本位于如下文件中
    - [x] [内存分配 zmalloc.c和zmalloc.h](./first_stage/Redis源码-内存分配zmalloc.md)
    - [x] [动态字符串 sds.h和sds.c](./first_stage/Redis源码-动态字符串sds.md)
    - [x] [双端链表 adlist.c和adlist.h](./first_stage/Redis源码-双端链表adlist.md)
    - [x] [字典 dict.h和dict.c](./first_stage/Redis源码-字典dict.md)
    - [x] [跳跃表 server.h文件里面关于zskiplist结构和zskiplistNode结构，以及t_zset.c中所有zsl开头的函数，比如 zslCreate、zslInsert、zslDeleteNode等等。](./first_stage/Redis源码-有序集合zset.md)
    - [x] [基数统计 hyperloglog.c 中的 hllhdr 结构， 以及所有以 hll 开头的函数](./first_stage/Redis源码-基数统计hyperloglog.md)
    - [x] [整数集合数据结构 intset.h和intset.c](./first_stage/Redis源码-整数集合intset.md)
    - [x] [缩列表数据结构 ziplist.h和ziplist.c](./first_stage/Redis源码-压缩列表ziplist.md)
    - [x] [快速列表数据结构 quicklist.h和quicklist.c](./first_stage/Redis源码-快速列表quicklist.md)（Redis3.2后新数据结构）
    - [x] [紧凑列表 listpack.c和listpack.h](./first_stage/Redis源码-紧凑列表listpack.md)（Redis5.0后新数据结构）
    - [x] [基数树 rax.c和rax.h](./first_stage/Redis源码-基数树rax.md)（Redis5.0后新数据结构）
2. 第二阶段 熟悉Redis数据类型的实现
    - [x] [对象系统 object.c](./second_stage/Redis源码-对象系统object.md)
    - [x] [字符串对象 t_string.c](./second_stage/Redis源码-字符串对象string.md)
    - [x] [列表对象 t_list.c](./second_stage/Redis源码-列表对象list.md)
    - [x] [散列对象 t_hash.c](./second_stage/Redis源码-散列对象hash.md)
    - [x] [集合对象 t_set.c](./second_stage/Redis源码-集合对象set.md)
    - [x] [有序集合对象 t_zset.c](./second_stage/Redis源码-有序集合对象zset.md)
    - [ ] [消息队列 t_stream.c和stream.h](./second_stage/Redis源码-消息队列stream.md)（Redis5.0后新数据结构）
    - [ ] HyperLogLog键 hyperloglog.c中所有以pf开头的函数
3. 第三阶段 熟悉Redis数据库的实现
    - [x] [数据库实现 redis.h文件中的redisDb结构，以及db.c文件](./third_stage/Redis源码-数据库的实现.md)
    - [x] [通知功能 notify.c](./third_stage/Redis源码-通知功能notify.md)
    - [x] [RDB持久化 rdb.c](./third_stage/Redis源码-RDB持久化.md)
    - [x] [AOF持久化 aof.c](./third_stage/Redis源码-AOF持久化.md)
    - [x] [发布和订阅 redis.h文件的pubsubPattern结构，以及pubsub.c文件](./third_stage/Redis源码-发布和订阅.md)
    - [x] [事务 redis.h文件的multiState结构以及multiCmd结构，multi.c文件](./third_stage/Redis源码-事务.md)
4. 第四阶段 熟悉客户端和服务器端的代码实现
    - [x] [事件驱动 ae.c/ae_epoll.c/...](./fourth_stage/Redis源码-事件驱动.md)
    - [x] [网络通信 anet.c和networking.c](./fourth_stage/Redis源码-网络通信.md)
    - [ ] 服务器端 server.c
    - [ ] 客户端 redis-cli.c
    - [ ] 通信协议
    - 这个时候可以阅读下面的独立功能模块的代码实现
    - [ ] lua脚本 scripting.c
    - [ ] 慢查询 slowlog.c
    - [ ] 监视 monitor.c
5. 第五阶段 这一阶段主要是熟悉Redis多机部分的代码实现
    - [ ] 复制功能 replication.c
    - [ ] Redis Sentinel sentinel.c
    - [ ] 集群 cluster.c
6. 其他代码文件介绍
    - 关于测试方面的文件有：
    - [ ] memtest.c 内存检测
    - [ ] redis_benchmark.c 用于redis性能测试的实现。
    - [ ] redis_check_aof.c 用于更新日志检查的实现。
    - [ ] redis_check_dump.c 用于本地数据库检查的实现。
    - [ ] testhelp.c 一个C风格的小型测试框架。
    - 一些工具类的文件如下：
    - [ ] bitops.c GETBIT、SETBIT 等二进制位操作命令的实现
    - [ ] debug.c 用于调试时使用
    - [ ] endianconv.c 高低位转换，不同系统，高低位顺序不同
    - [ ] help.h 辅助于命令的提示信息
    - [ ] lzf_c.c 压缩算法系列
    - [ ] lzf_d.c 压缩算法系列
    - [ ] rand.c 用于产生随机数
    - [ ] release.c 用于发布时使用
    - [ ] sha1.c sha加密算法的实现
    - [ ] util.c 通用工具方法
    - [ ] crc64.c 循环冗余校验
    - [ ] sort.c SORT命令的实现
    - 一些封装类的代码实现：
    - [ ] bio.c background I/O的意思，开启后台线程用的
    - [ ] latency.c 延迟类
    - [ ] migrate.c 命令迁移类，包括命令的还原迁移等
    - [ ] pqsort.c 排序算法类
    - [ ] rio.c redis定义的一个I/O类
    - [ ] syncio.c 用于同步Socket和文件I/O操作

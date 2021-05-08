# 时间序列数据库 TSDB

## 时序数据库有哪些？
- [OpenTSDB](https://github.com/OpenTSDB/opentsdb)
- [InfluxDB](https://github.com/influxdata/influxdb)
- [Timescale](https://www.timescale.com/) 一个基于传统关系型数据库 PostgreSQL 改造的时间序列数据库，继承了 PostgreSQL 许多优点，比如支持 SQL，支持轨迹数据存储，支持 join，可扩展等等，读写性能好。TimeScale 采用固定 schema，数据占用空间大，对于时序业务长期相对固定且对数据存储成本不敏感的业务来说，也是一种选择。
- [Prometheus](https://github.com/prometheus/prometheus)
    - [prometheus-book](https://yunlzheng.gitbook.io/prometheus-book/)
    - [编写 Prometheus Exporter: 以阿里云 Exporter 为例](https://aleiwu.com/post/aliyun-exporter-bp/)
    - [视频 | 技术分享：Prometheus 是怎么存储数据的](https://www.youtube.com/watch?v=qB40kqhTyYM) by 陈皓
- [Beringei](https://github.com/facebookarchive/beringei)
- [阿里云时序数据库](https://www.aliyun.com/product/hitsdb)
- [腾讯云时序数据库 CTSDB](https://cloud.tencent.com/document/product/652)
- 更多：[List of Time Series Databases](https://misfra.me/2016/04/09/tsdb-list/)

## 时序数据库与传统数据库有什么不同？

## 参考
- [从前世今生聊一聊，大厂为啥亲睐时序数据库](https://zhuanlan.zhihu.com/p/309749066) by 华为云开发者社区
# 时间序列

工业大数据分析主要能解决三大类问题：
- 高端装备及其制造业
    - 剩余寿命，机器还能撑多长时间，再过多长时间需要维修；
    - 故障预警，在没出故障之前，提前发现并预警，包括设备的异常检测；
    - 故障诊断，定位设备异常之处；
    - 运维优化，通过数据分析，如一些运筹优化的方式，在实际派工时提升运维的效率；
- 车间内部，我们希望提高生产效率和生产质量。正如在化工行业里面，我们怎么通过数据分析提高有效气体的产出率，怎么通过参数优化来提高整个系统的运作效率。
- 产业互联网，即互联网+，商业模式的变革，包括经营流程的变革，而数据分析则在后边起到支撑作用。数据在这里不是主导，而是辅助预测、调度优化

## 数据集
- [UCR Time Series Classification Archive](https://www.cs.ucr.edu/~eamonn/time_series_data_2018/)
- [Awesome Public Datasets](https://github.com/awesomedata/awesome-public-datasets)
- [Awesome Public Industrial Datasets](https://github.com/makinarocks/awesome-industrial-machine-datasets)
- [国家数据](https://data.stats.gov.cn/)（综合）
- [CEIC](https://www.ceicdata.com/zh-hans)（金融）
- [Tushare 大数据开放社区](https://waditu.com/)（金融）
- [JoinQuant 量化平台](https://www.joinquant.com)（金融）
- [C-MAPSS](https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/#turbofan)（工业）
- [PHM Data Challenge](https://phmsociety.org/conference/annual-conference-of-the-phm-society/annual-conference-of-the-prognostics-and-health-management-society-2015/phm-data-challenge-3/)（工业），本身是一个竞赛
    - [北航可靠性与系统工程学院在亚太区 PHM 国际数据挑战赛中荣获佳绩](https://news.buaa.edu.cn/info/1004/32053.htm) 2017
    - [独家｜PHM 数据竞赛首个中国夺冠团队经验分享](https://kknews.cc/tech/5xxzoy8.html) 2017

## 参考资料
- 剩余寿命（Remaining Useful Life，RUL）
    - [论文 | Predicting Remaining Useful Life using Time Series Embeddings based on Recurrent Neural Networks](https://www.aminer.org/pub/5a260c8117c44a4ba8a30fe8/predicting-remaining-useful-life-using-time-series-embeddings-based-on-recurrent-neural) 2017
    - [论文 | Long Short-Term Memory Network for Remaining Useful Life Estimation](https://ieeexplore.ieee.org/document/7998311/) 2017
    - [论文 | Remaining Useful Life Estimation Using Functional Data Analysis](https://ieeexplore.ieee.org/document/8819420) 2019
    - [论文 | 融合多传感器数据的发动机剩余寿命预测方法](http://hkxb.buaa.edu.cn/CN/html/20191212.html) 2019
    - [Jet Engine Remaining Useful Life (RUL) Prediction](https://medium.com/@hamalyas_/jet-engine-remaining-useful-life-rul-prediction-a8989d52f194) | [中文](https://zhuanlan.zhihu.com/p/111898696) 2019
    - [Pytorch：使用 CNN 实现 C-MAPSS 数据集里面的剩余寿命预测](https://blog.csdn.net/comli_cn/article/details/106713022) 2020
    - [Tensorflow 2.0：实现 C-MAPSS 数据集的剩余寿命预测](https://www.codeleading.com/article/70484399885/) 2020
    - [MATLAB 官方示例](https://ww2.mathworks.cn/help/predmaint/examples.html?category=predict-remaining-useful-life&s_tid=CRUX_topnav)
- [论文 | 面向物联网时间序列数据深度学习的 LSTM 方法研究](http://gb.oversea.cnki.net/KCMS/detail/detail.aspx?filename=1018145823.nh&dbcode=CMFD&dbname=CMFDREF) 2018
- [论文 | LSTM Learning With Bayesian and Gaussian Processing for Anomaly Detection in Industrial IoT](https://ieeexplore.ieee.org/document/8896029) 2020 
- [7 methods to perform Time Series forecasting (with Python codes)](https://www.analyticsvidhya.com/blog/2018/02/time-series-forecasting-methods/) | [中文](https://zhuanlan.zhihu.com/p/77063373)
- [深入浅出 LSTM 及其 Python 代码实现](https://www.toutiao.com/i6787727144882536972/?wid=1619584235647)
- [LSTM 入门例子：根据前 9 年的数据预测后 3 年的客流（PyTorch 实现）](https://zhuanlan.zhihu.com/p/94757947)
- [时间序列预测方法总结](https://zhuanlan.zhihu.com/p/67832773)
- [干货分享 | 云脑科技核心算法工程师详解时间序列](https://developer.aliyun.com/article/400147)
- [离散时间序列的几种频谱分析方法的 MATLAB 实现](https://www.bilibili.com/read/cv240064/)
- [微信后台基于时间序的海量数据冷热分级架构设计实践](https://mp.weixin.qq.com/s/XlZF0GDt7dnHyYuS1an6tg) 2017
- [微信后台基于时间序的新一代海量数据存储架构的设计实践](http://www.52im.net/thread-2970-1-1.html)
- 监控 & 运维
    - [蚂蚁集团智能监控的时序异常检测：基于 CNN 神经网络的异常检测](https://zhuanlan.zhihu.com/p/158490622)
    - [清华最新 AIOps 案例：强化学习，降低网络传输延时](https://www.bizseer.com/index.php?m=content&c=index&a=show&catid=26&id=13) 2019
    - [AIOps 在美团的探索与实践 - 故障发现篇](https://tech.meituan.com/2020/10/15/mt-aiops-horae.html) 2020
- RNN
    - [The Unreasonable Effectiveness of Recurrent Neural Networks](https://karpathy.github.io/2015/05/21/rnn-effectiveness/) | [中](https://www.itread01.com/content/1546098492.html)
    - [Pytorch 实现 RNN](https://zhuanlan.zhihu.com/p/71732459)
    - [读 PyTorch 源码学习 RNN（1）](https://zhuanlan.zhihu.com/p/32103001)
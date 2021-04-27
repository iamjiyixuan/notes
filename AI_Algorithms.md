# AI 算法模型

- ARIMA（Autoregressive Integrated Moving average，自回归移动平均模型），统计学模型，其主要通过 d 阶微分运算将非平稳时间序列转换为平稳时间序列，同时引入自相关系数之后的平稳序列进行分析处理。
- RBF（Radial Basis Function Network，径向基函数网络），
- Glove，词向量学习算法
- Word2vec，是一群用来产生词向量的相关模型。这些模型为浅层双层的神经网络，用来训练以重新建构语言学之词文本。网络以词表现，并且需猜测相邻位置的输入词，在word2vec中词袋模型假设下，词的顺序是不重要的。
- CNN（Convolutional Neural Network，卷积神经网络），是一种前馈神经网络，它的人工神经元可以响应一部分覆盖范围内的周围单元，对于大型图像处理有出色表现。
- RNN
- LSTM（Long Short-Term Memory 长短期记忆），是一种时间循环神经网络（RNN），论文首次发表于 1997 年。由于独特的设计结构，LSTM 适合于处理和预测时间序列中间隔和延迟非常长的重要事件。
- GRU（Gate Recurrent Unit），是循环神经网络（Recurrent Neural Network, RNN）的一种。和 LSTM 一样，也是为了解决长期记忆和反向传播中的梯度等问题而提出来的。
- Seq2seq，是用于自然语言处理的一系列机器学习方法。应用领域包括机器翻译，图像描述，对话模型和文本摘要。

## 聊天机器人
- 模型分类
    - 基于检索。回答是提前定义的，使用规则引擎、正则匹配或者深度学习训练好的分类器从数据库中挑选一个最佳的回复
    - 基于生成。不依赖于提前定义的回答，但是在训练的过程中，需要大量的语料，语料包含了 context 和 response 。当下流行使用 LSTM 和 RNN 训练生成的模型，这种方法最早用来完成机器翻译的任务

## 参考资料
- [深度 | 一篇文章看懂聊天机器人的历史、技术和研究进展](https://mp.weixin.qq.com/s/CsoNU4pMnuMNX1zwwW-Dag) 2016
- [盘点 | 聊天机器人的发展状况与分类](https://mp.weixin.qq.com/s?__biz=MzA5ODEzMjIyMA==&mid=2247496867&idx=4&sn=6783d807a6187ecd60b00f9a80bf1e59&source=41#wechat_redirect) 2017
- [总结 │ 解密 chatbot 人工智能聊天机器人 技术沙龙](https://mp.weixin.qq.com/s/r7vPOSdH7XK_3jc1WLqr2Q) 2017
- [独家 | 百度朱凯华：智能搜索和对话式 OS 最新技术全面解读（65PPT）](https://mp.weixin.qq.com/s/oMoPk8FoVm9xMQpQISgq6A) 2017
- [实战 | 让机器人替你聊天，还不被人看出破绽？来，手把手教你训练一个克隆版的你](https://mp.weixin.qq.com/s?__biz=Mzg4NDQwNTI0OQ==&mid=2247523882&idx=1&sn=ddc86a9cd468b1ede0842d6726021bda&source=41#wechat_redirect) 2017
- [观点 | 如何从一名软件工程师转行做人工智能？](https://mp.weixin.qq.com/s/EB469sq3TauBk_JioIVUSw) 2017
- [用 TensorFlow 实现智能机器人](https://mp.weixin.qq.com/s/bnDlLdtTfUxv9b4QUNuhNw) 2017
- [深度长文：NLP的巨人肩膀（上）](https://mp.weixin.qq.com/s/Rd3-ypRYiJObi-e2JDeOjQ) 2018
- [基于知识图谱的人机对话系统 | 公开课笔记](https://mp.weixin.qq.com/s?__biz=Mzg4NDQwNTI0OQ==&mid=2247523456&idx=2&sn=a7a7e3bd98d29b0eb29064f60f8d9a29&source=41#wechat_redirect) 2018
- [论文导读 | 阿里小蜜背后的技术秘密](https://mp.weixin.qq.com/s/2Y66uCi1qS0VTaizyCg3cA) 2018
- [为减少用户电话排队，阿里研发了智能客服调度系统](https://mp.weixin.qq.com/s/nqOvcKtxpqehWFO4XkXr5g) 2018
- [AI 技术如何打造智能客服](https://zhuanlan.zhihu.com/p/43823105) 2019
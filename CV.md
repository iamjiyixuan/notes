# 计算机视觉 Computer Vision

## 前置课程
- [《数字图像处理 · 第四版》](https://book.douban.com/subject/35075811/)
- [《动手学深度学习》](https://zh.d2l.ai/index.html)

## 后置课程
- [《机器学习系统：设计和实现》](https://openmlsys.github.io/)

## 相关顶会
- CVPR, Internaltional Conference on Computer Vision and Pattern Recogintion
- ICCV, IEEE International Conference on Computer Vision
- ECCV, Europeon Conference on Computer Vision
- NeurIPS, Conference and Workshop on Neural Information Processing Systems
- AAAI, 

[最新！AI顶会排行榜揭晓， CVPR居首 NIPS、ICML分列二、三位](https://zhuanlan.zhihu.com/p/82288889)

## 细分领域
- 图像分类 Image Classification
- 目标检测 Object Detection
    - One-stage：
    - Two-stage：先提出区域（region proposal），然后对这些区域进行分类和位置修正预测
- 目标跟踪 Object Tracking
- 语义分割 Semantic Segmentation
- 样式迁移 Style Transfer
- 图像超分辨率 Image Super-Resolution

## 硬件
- 单目相机 Monocular
- 双目相机 Stereo
- 深度相机 RGB-D
- 激光雷达 LiDAR

## 数据集
- MNIST、Fashion-MNIST
    - MNIST 包括 6 万张 28x28 的训练样本，1 万张测试样本
- [CIFAR-10 and CIFAR-100 datasets](https://www.cs.toronto.edu/~kriz/cifar.html)
    - CIFAR-10 数据集由 10 个类的 60000 个 32x32 彩色图像组成，每个类有 6000 个图像，共 50000 个训练图像和 10000 个测试图像。
- [ImageNet](https://www.image-net.org/)
    - [【知乎】ImageNet 这八年：李飞飞和她改变的 AI 世界](https://zhuanlan.zhihu.com/p/28142670 )
- https://www.payititi.com/
- [百度飞桨](https://aistudio.baidu.com/aistudio/datasetoverview)
- https://www.kaggle.com/datasets
- 目标检测
    - COCO https://cocodataset.org/#home
    - VOC http://host.robots.ox.ac.uk/pascal/VOC 有 VOC2007 和 VOC2012 两个数据集。包含约 10,000 张带有边界框的图片用于训练和验证，含有 20 个类别

## 编程语言
- Python
- C++

## 开源项目 / 框架
- https://opencv.org/
- [OpenMMLab](https://github.com/open-mmlab)
- [PaddleX](https://github.com/PaddlePaddle/PaddleX)
- https://paperswithcode.com/
- 扩展阅读
    - [【知乎】GluonCV、OpenMMLab、Paddle 系列算法框架对比与思考](https://zhuanlan.zhihu.com/p/361038957)

## 图像处理
- 

## 网络结构
- backbone：主干网络，CV 中用于特征提取，常见的有 VGG、ResNet、MobileNet 等

## 指标
- Precision 精确率，是针对预测结果而言的，它表示的是预测为正的样本中有多少是真正的正样本。那么预测为正就有两种可能了，一种就是把正类预测为正类（TP），另一种就是把负类预测为正类（FP），也就是 `Precision = TP / (TP + FP)`
- Recall 召回率，也称 Sensitivity 敏感性，是针对原来的样本而言的，它表示的是样本中的正例有多少被预测正确了。那也有两种可能，一种是把原来的正类预测成正类（TP），另一种就是把原来的正类预测为负类（FN），也就是 `Recall = TP / (TP + FN)`
- mAP（mean Average Precision，平均精度均值）是目标检测算法的主要评估指标
- FLOPs（Floating Point Operations）指浮点运算数，理解为计算量。可以用来衡量算法/模型的复杂度。
- params

## Benchmark
- [Deep Learning GPU Benchmarks 2021](https://www.aime.info/blog/deep-learning-gpu-benchmarks-2021/)
- Apple M1 GPU
    - [【B站】PyTorch 支持 M1 GPU 加速了! 提升有多大?](https://www.bilibili.com/video/BV1a341137Sb/?spm_id_from=333.788)
    - [Running PyTorch on the M1 GPU](https://sebastianraschka.com/blog/2022/pytorch-m1-gpu.html)

## 部署
- GPU
    - TensorRT - 可以在 NVIDIA 各种 GPU 硬件平台下运行的一个 C++ 推理框架。我们利用 Pytorch、TF 或者其他框架训练好的模型，可以转化为 TensorRT 的格式，然后利用 TensorRT 推理引擎去运行我们这个模型，从而提升这个模型在英伟达 GPU 上运行的速度。在 GPU 服务器上部署的话 TensorRT 是首选！
- CPU
    - OpenVINO - 英特尔 CPU 端（x86 处理器）部署首选！
- ARM（移动端）
    - MNN
    - TNN
    - NCNN
    - TVM
- 参考
    - [老潘的 AI 部署以及工业落地学习之路](https://mp.weixin.qq.com/s/1FitAKulp43hRyPYUzWuzg)
    - [【知乎】谷歌抛弃 TensorFlow，押宝 JAX，其中都有哪些值得关注的信息？](https://www.zhihu.com/question/537823429/answer/2538173977)
    - [【知乎】机器学习平台基础架构](https://zhuanlan.zhihu.com/p/538160449) by 云音乐技术团队 2022-07-06

## 论文精读 & 复现
<table>
    <tr>
        <td>LeNet</td>
        <td>classification</td>
        <td>
            <em>1998, Gradient-based learning applied to document recognition</em> <a href="http://vision.stanford.edu/cs598_spring07/papers/Lecun98.pdf">pdf</a><br />
            <br />
            <a href="https://zh.d2l.ai/chapter_convolutional-neural-networks/lenet.html">《动手学深度学习》6.6. 卷积神经网络（LeNet）</a><br />
            <a href="https://zhuanlan.zhihu.com/p/63910035">【知乎】再认识 Yann LeCun，一个可能是拥有最多中文名的男人【AI大咖】by 言有三</a>
        </td>
    </tr>
    <tr>
        <td>AlexNet</td>
        <td>classification</td>
        <td>
            NIPS-2012, ImageNet Classification with Deep Convolutional Neural Networks <a href="https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf">pdf</a><br />
            <br />
            深度卷积神经网络在大规模数据集的开篇巨作<br />
            <br />
            <a href="https://www.bilibili.com/video/BV1ih411J7Kz/">【B站】9年后重读深度学习奠基作之一：AlexNet【论文精读】by 李沐</a><br />
            <a href="https://www.bilibili.com/video/BV1hq4y157t1/">【B站】AlexNet 论文逐段精读【论文精读】by 李沐</a><br />
            <a href="https://zhuanlan.zhihu.com/p/62645723">【知乎】认真认识一代 AI 教父 Hinton 【AI大咖】by 言有三</a>
        </td>
    </tr>
    <tr>
        <td rowspan="4">GoogLeNet</td>
        <td rowspan="4">classification</td>
        <td>
            CVPR-2015, Going deeper with convolutions <a href="https://www.cs.unc.edu/~wliu/papers/GoogLeNet.pdf">pdf</a><br />
            提出多尺度卷积模块<br />
        </td>
    </tr>
    <tr>
        <td>
            arXiv-2015, Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift <a href="http://data-science.wiki/images/Batch_Normalization-_Accelerating_Deep_Network_Training_by_Reducing_Internal_Covariate_Shift_1502.03167v3.pdf">pdf</a><br />
            提出 BN 层<br />
        </td>
    </tr>
    <tr>
         <td>
            CVPR-2016, Rethinking the Inception Architecture for Computer Vision <a href="https://openaccess.thecvf.com/content_cvpr_2016/papers/Szegedy_Rethinking_the_Inception_CVPR_2016_paper.pdf">pdf</a><br />
            提出卷积分解<br />
        </td>
    </tr>
    <tr>
         <td>
            AAAI-2017, Inception-v4, Inception-ResNet and the Impact of Residual Connections on Learning <a href="https://www.cs.cmu.edu/~jeanoh/16-785/papers/szegedy-aaai2017-inception-v4.pdf">pdf</a><br />
        </td>
    </tr>
    <tr>
        <td>VGGNet</td>
        <td>classification</td>
        <td>
            ICLR-2015, Very Deep Convolutional Networks for Large-Scale Image Recognition <a href="https://arxiv.org/pdf/1409.1556.pdf">pdf</a><br />
            <br />
            VGGNet 可以看成是加深版的 AlexNet，5 个卷积 stage、3 层全连接层、softmax 层，层与层之间使用 max-pooling，激活函数均为 ReLU。常见结构 VGG16 和 VGG19，两者并没有本质上的区别，只是网络深度不一样。VGG16 包含了 16 个隐藏层（13 个卷积层和 3 个全连接层），而 VGG19 包含了 19 个隐藏层（16 个卷积层和 3 个全连接层）<br />
            <br />
            预训练模型：<a href="https://github.com/open-mmlab/mmclassification/tree/master/configs/vgg">https://github.com/open-mmlab/mmclassification/tree/master/configs/vgg</a><br />
        </td>
    </tr>
    <tr>
        <td rowspan="2">ResNet</td>
        <td rowspan="2">classification</td>
        <td>
            CVPR-2016, Deep Residual Learning for Image Recognition <a href="https://openaccess.thecvf.com/content_cvpr_2016/papers/He_Deep_Residual_Learning_CVPR_2016_paper.pdf">pdf</a><br />
            预训练模型：<a href="https://github.com/open-mmlab/mmclassification/tree/master/configs/resnet">https://github.com/open-mmlab/mmclassification/tree/master/configs/resnet</a><br />
            <a href="https://www.bilibili.com/video/BV1Fb4y1h73E/?spm_id_from=333.788">【B站】撑起计算机视觉半边天的 ResNet【论文精读】by 李沐</a><br />
            <a href="https://www.bilibili.com/video/BV1P3411y7nn/?spm_id_from=333.788.recommend_more_video.0">【B站】ResNet 论文逐段精读【论文精读】by 李沐</a><br />
        </td>
    </tr>
    <tr>
        <td>
            ResNeXt：CVPR-2017, Aggregated Residual Transformations for Deep Neural Networks <a href="https://openaccess.thecvf.com/content_cvpr_2017/papers/Xie_Aggregated_Residual_Transformations_CVPR_2017_paper.pdf">pdf</a><br />
            预训练模型：<a href="https://github.com/open-mmlab/mmclassification/tree/master/configs/resnext">https://github.com/open-mmlab/mmclassification/tree/master/configs/resnext</a>
        </td>
    </tr>
    <tr>
        <td>DenseNet</td>
        <td>classification</td>
        <td>
            CVPR-2017, Densely Connected Convolutional Networks <a href="https://openaccess.thecvf.com/content_cvpr_2017/papers/Huang_Densely_Connected_Convolutional_CVPR_2017_paper.pdf">pdf</a><br />
            <a href="https://zhuanlan.zhihu.com/p/37189203">【知乎】DenseNet：比 ResNet 更优的 CNN 模型</a>
        </td>
    </tr>
    <tr>
        <td rowspan="3">MobileNet</td>
        <td rowspan="3">轻量级网络</td>
        <td>
            arXiv-2017, MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications <a href="https://arxiv.org/pdf/1704.04861.pdf">pdf</a><br />
            <a href="https://zhuanlan.zhihu.com/p/70703846">【知乎】轻量级神经网络“巡礼”（二）—— MobileNet，从 V1 到 V3</a><br />
        </td>
    </tr>
    <tr>
        <td>
            CVPR-2018, MobileNetV2: Inverted Residuals and Linear Bottlenecks <a href="https://arxiv.org/pdf/1801.04381.pdf">pdf</a><br />
        </td>
    </tr>
    <tr>
        <td>
            ICCV-2019, Searching for MobileNetV3 <br />
        </td>
    </tr>
    <tr>
        <td rowspan="2">ShuffleNet</td>
        <td rowspan="2">轻量级网络</td>
        <td>
            CVPR-2018, ShuffleNet: An Extremely Efficient Convolutional Neural Network for Mobile Devices <a href="https://openaccess.thecvf.com/content_cvpr_2018/papers/Zhang_ShuffleNet_An_Extremely_CVPR_2018_paper.pdf">pdf</a><br />
            预训练模型：<a href="https://github.com/open-mmlab/mmclassification/tree/master/configs/shufflenet_v1">https://github.com/open-mmlab/mmclassification/tree/master/configs/shufflenet_v1</a><br />
        </td>
    </tr>
    <tr>
        <td>
            ECCV-2018, Shufflenet v2: Practical guidelines for efficient cnn architecture design <a href="https://openaccess.thecvf.com/content_ECCV_2018/papers/Ningning_Light-weight_CNN_Architecture_ECCV_2018_paper.pdf">pdf</a><br />
            <a href="https://zhuanlan.zhihu.com/p/67009992">【知乎】轻量级神经网络“巡礼”（一）—— ShuffleNetV2</a><br />
            预训练模型：<a href="https://github.com/open-mmlab/mmclassification/tree/master/configs/shufflenet_v2">https://github.com/open-mmlab/mmclassification/tree/master/configs/shufflenet_v2</a>
        </td>
    </tr>
    <tr>
        <td>
            R-CNN 2014 <br />
            Fast R-CNN 2015 <br />
            Faster R-CNN 2015 <br />
            Mask R-CNN 2017
        </td>
        <td>detection</td>
        <td></td>
    </tr>
    <tr>
        <td>SSD</td>
        <td>detection（one-stage）</td>
        <td>
            ECCV 2016, Single Shot MultiBox Detector <a href="https://www.cs.unc.edu/~wliu/papers/ssd.pdf">pdf</a><br />
            <a href="https://zhuanlan.zhihu.com/p/31427288">【知乎】SSD 目标检测 by 白裳</a><br />
            <a href="https://www.yuque.com/docs/share/5da9151c-14ee-4473-8975-28f9badd9197">【语雀】Pytorch—SSD 模型训练（VOC 数据集）【目标检测实战】</a>
        </td>
    </tr>
    <tr>
        <td rowspan="10">YOLO</td>
        <td rowspan="10">detection（one-stage）</td>
        <td>
            YOLO 官网：<a href="https://pjreddie.com/">https://pjreddie.com/</a><br />
            <a href="https://zhuanlan.zhihu.com/p/136382095">【知乎】目标检测之 YOLO 算法：YOLOv1,YOLOv2,YOLOv3,TinyYOLO,YOLOv4,YOLOv5,YOLObile,YOLOF,YOLOX 详解</a><br />
        </td>
    </tr>
    <tr>
        <td>
            CVPR-2016, You Only Look Once: Unified, Real-Time Object Detection <a href="https://pjreddie.com/media/files/papers/yolo_1.pdf">pdf</a><br />
        </td>
    </tr>
    <tr>
        <td>
            CVPR-2017, YOLO9000: Better, Faster, Stronger <a href="https://openaccess.thecvf.com/content_cvpr_2017/papers/Redmon_YOLO9000_Better_Faster_CVPR_2017_paper.pdf">pdf</a><br />
        </td>
    </tr>
    <tr>
        <td>
            arXiv-2018, YOLOv3: An Incremental Improvement <a href="https://pjreddie.com/media/files/papers/YOLOv3.pdf">pdf</a><br />
            <a href="https://zhuanlan.zhihu.com/p/108440835">【知乎】YOLO 之父 Joseph Redmon 宣布退出 CV 界，坦言无法忽视自己工作带来的负面影响</a><br />
            <a href="https://www.bilibili.com/video/BV1Hp4y1y788?spm_id_from=333.1007.top_right_bar_window_default_collection.content.click">【B站】Pytorch 搭建自己的 YOLO3 目标检测平台</a><br />
        </td>
    </tr>
    <tr>
        <td>
            arXiv-2020, YOLOv4: Optimal Speed and Accuracy of Object Detection <a href="https://arxiv.org/pdf/2004.10934v1.pdf">pdf</a>, <a href="https://github.com/AlexeyAB/darknet">code</a><br />
            <a href="https://zhuanlan.zhihu.com/p/135909702">【知乎】大神接棒，YOLOv4 来了！</a><br />
        </td>
    </tr>
    <tr>
        <td>
            YOLO-v5（非官方）：<a href="https://github.com/ultralytics/yolov5">https://github.com/ultralytics/yolov5</a> <br />
        </td>
    </tr>
    <tr>
        <td>
            YOLOF：CVPR-2021, You Only Look One-level Feature <a href="https://openaccess.thecvf.com/content/CVPR2021/papers/Chen_You_Only_Look_One-Level_Feature_CVPR_2021_paper.pdf">pdf</a><br />
        </td>
    </tr>
    <tr>
        <td>
            YOLOX：arXiv-2021, Exceeding YOLO Series in 2021 <a href="https://arxiv.org/pdf/2107.08430v2.pdf">pdf</a><br />
        </td>
    </tr>
    <tr>
        <td>
            YOLO-v6（by 美团，非官方）：<a href="https://github.com/meituan/YOLOv6">https://github.com/meituan/YOLOv6</a><br />
            <a href="https://tech.meituan.com/2022/06/23/yolov6-a-fast-and-accurate-target-detection-framework-is-opening-source.html">YOLOv6：又快又准的目标检测框架开源啦</a>
        </td>
    </tr>
    <tr>
        <td>
            arXiv-2022, YOLOv7: Trainable bag-of-freebies sets new state-of-the-art for real-time object detectors <a href="https://arxiv.org/pdf/2207.02696v1.pdf">pdf</a>, <a href="https://github.com/WongKinYiu/yolov7">code</a><br />
            <a href="https://zhuanlan.zhihu.com/p/538930719">【知乎】YOLOv4 团队打造 YOLOv7！最先进的实时目标检测网络来了！</a>
        </td>
    </tr>
    <tr>
        <td>FCN 2014</td>
        <td>segmentation</td>
        <td>Fully Convolutional Networks</td>
    </tr>
    <tr>
        <td>
            U-Net 2015
        </td>
        <td>segmentation</td>
    </tr>
    <tr>
        <td>
            <a href="https://arxiv.org/abs/1708.02002">RetinaNet</a> 2017
        </td>
        <td>detection</td>
        <td>
            <a href="https://zhuanlan.zhihu.com/p/346198300">【知乎】轻松掌握 MMDetection 中常用算法(一)：RetinaNet 及配置详解</a>
        </td>
    </tr>
    <tr>
        <td>PointRCNN 2019</td>
        <td>3D detection</td>
        <td>
            <a href="https://www.bilibili.com/video/BV1cE411L7mL?spm_id_from=333.1007.top_right_bar_window_default_collection.content.click">【B站】PointRCNN & Part-A2 Net</a>
        </td>
    </tr>
    <tr>
        <td>ViT 2020</td>
        <td></td>
        <td>
            Transformer 杀入 CV 界，推翻了 2012 Alexnet 提出的 CNN 在 CV 的统治地位。
        </td>
    </tr>
    <tr>
        <td>Swin Transformer 2021</td>
    </tr>
    <tr>
        <td>MAE 2021</td>
        <td></td>
        <td>
            BERT 的 CV 版
        </td>
    </tr>
    <tr>
        <td>更多。。。</td>
        <td></td>
        <td>
            <a href="https://github.com/mli/paper-reading">https://github.com/mli/paper-reading</a> <br />
            <a href="https://github.com/amusi/CVPR2022-Papers-with-Code">https://github.com/amusi/CVPR2022-Papers-with-Code</a>
        </td>
    </tr>
</table>

## 参考资料
- [2021 年 CV 算法工程师技术入门路线图](https://jishuin.proginn.com/p/763bfbd5cab6)
- [综述计算机视觉五大技术：图像分类、对象检测、目标跟踪、语义分割和实例分割](https://bbs.cvmart.net/articles/655/1)

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
- https://aistudio.baidu.com/aistudio/datasetoverview
- https://www.kaggle.com/datasets
- 目标检测
    - COCO https://cocodataset.org/#home
    - VOC http://host.robots.ox.ac.uk/pascal/VOC 有 VOC2007 和 VOC2012 两个数据集。包含约 10,000 张带有边界框的图片用于训练和验证，含有 20 个类别

## 编程语言
- Python
- C++

## 开源项目
- https://opencv.org/
- [OpenMMLab](https://github.com/open-mmlab)
- https://paperswithcode.com/

## 图像处理
- 

## 网络结构
- backbone：主干网络，CV 中用于特征提取，常见的有 VGG、ResNet、MobileNet 等

## Benchmark
- [Deep Learning GPU Benchmarks 2021](https://www.aime.info/blog/deep-learning-gpu-benchmarks-2021/)
- Apple M1 GPU
    - [【B站】PyTorch 支持 M1 GPU 加速了! 提升有多大?](https://www.bilibili.com/video/BV1a341137Sb/?spm_id_from=333.788)
    - [Running PyTorch on the M1 GPU](https://sebastianraschka.com/blog/2022/pytorch-m1-gpu.html)

## 论文精读 & 复现
<table>
    <tr>
        <td>LeNet 1989</td>
    </tr>
    <tr>
        <td>AlexNet</td>
        <td>classification</td>
        <td>
            NIPS-2012, ImageNet Classification with Deep Convolutional Neural Networks <a target="_blank" href="https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf">pdf</a><br />
            <br />
            深度卷积神经网络在大规模数据集的开篇巨作<br />
            <br />
            <a target="_blank" href="https://www.bilibili.com/video/BV1ih411J7Kz/">【B站】9年后重读深度学习奠基作之一：AlexNet【论文精读】by 李沐</a><br />
            <a target="_blank" href="https://www.bilibili.com/video/BV1hq4y157t1/">【B站】AlexNet 论文逐段精读【论文精读】by 李沐</a>
        </td>
    </tr>
    <tr>
        <td>GoogLeNet</td>
        <td>classification</td>
        <td>
            CVPR-2015, Going deeper with convolutions <a target="_blank" href="https://www.cs.unc.edu/~wliu/papers/GoogLeNet.pdf">pdf</a><br />
            提出多尺度卷积模块<br />
            <hr />
            arXiv-2015, Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift <a target="_blank" href="http://data-science.wiki/images/Batch_Normalization-_Accelerating_Deep_Network_Training_by_Reducing_Internal_Covariate_Shift_1502.03167v3.pdf">pdf</a><br />
            提出 BN 层<br />
            <hr />
            CVPR-2016, Rethinking the Inception Architecture for Computer Vision <a target="_blank" href="https://openaccess.thecvf.com/content_cvpr_2016/papers/Szegedy_Rethinking_the_Inception_CVPR_2016_paper.pdf">pdf</a><br />
            提出卷积分解<br />
            <hr />
            AAAI-2017, Inception-v4, Inception-ResNet and the Impact of Residual Connections on Learning <a target="_blank" href="https://www.cs.cmu.edu/~jeanoh/16-785/papers/szegedy-aaai2017-inception-v4.pdf">pdf</a><br />
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
        <td>ResNet</td>
        <td>classification</td>
        <td>
            CVPR-2016, Deep Residual Learning for Image Recognition <a target="_blank" href="https://openaccess.thecvf.com/content_cvpr_2016/papers/He_Deep_Residual_Learning_CVPR_2016_paper.pdf">pdf</a><br />
            <br />
            预训练模型：<a href="https://github.com/open-mmlab/mmclassification/tree/master/configs/resnet">https://github.com/open-mmlab/mmclassification/tree/master/configs/resnet</a><br />
            <a target="_blank" href="https://www.bilibili.com/video/BV1Fb4y1h73E/?spm_id_from=333.788">【B站】撑起计算机视觉半边天的 ResNet【论文精读】by 李沐</a><br />
            <a target="_blank" href="https://www.bilibili.com/video/BV1P3411y7nn/?spm_id_from=333.788.recommend_more_video.0">【B站】ResNet 论文逐段精读【论文精读】by 李沐</a><br />
            <hr />
            ResNeXt：CVPR-2017, Aggregated Residual Transformations for Deep Neural Networks <a target="_blank" href="https://openaccess.thecvf.com/content_cvpr_2017/papers/Xie_Aggregated_Residual_Transformations_CVPR_2017_paper.pdf">pdf</a><br />
            <br />
            预训练模型：<a href="https://github.com/open-mmlab/mmclassification/tree/master/configs/resnext">https://github.com/open-mmlab/mmclassification/tree/master/configs/resnext</a>
        </td>
    </tr>
    <tr>
        <td>DenseNet</td>
        <td>classification</td>
        <td>
            CVPR-2017, Densely Connected Convolutional Networks <a target="_blank" href="https://openaccess.thecvf.com/content_cvpr_2017/papers/Huang_Densely_Connected_Convolutional_CVPR_2017_paper.pdf">pdf</a><br />
            <a href="https://zhuanlan.zhihu.com/p/37189203">【知乎】DenseNet：比 ResNet 更优的 CNN 模型</a>
        </td>
    </tr>
    <tr>
        <td>MobileNet</td>
        <td>轻量级网络</td>
        <td>
            arXiv-2017, MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications <br />
            <br />
            <a href="https://zhuanlan.zhihu.com/p/70703846">【知乎】轻量级神经网络“巡礼”（二）—— MobileNet，从V1到V3</a><br />
            <hr />
            CVPR-2018, MobileNetV2: Inverted Residuals and Linear Bottlenecks <br />
            <hr />
            ICCV-2019, Searching for MobileNetV3 <br />
        </td>
    </tr>
    <tr>
        <td>ShuffleNet</td>
        <td>轻量级网络</td>
        <td>
            CVPR-2018, ShuffleNet: An Extremely Efficient Convolutional Neural Network for Mobile Devices <a href="https://openaccess.thecvf.com/content_cvpr_2018/papers/Zhang_ShuffleNet_An_Extremely_CVPR_2018_paper.pdf">pdf</a><br />
            <br />
            预训练模型：<a href="https://github.com/open-mmlab/mmclassification/tree/master/configs/shufflenet_v1">https://github.com/open-mmlab/mmclassification/tree/master/configs/shufflenet_v1</a><br />
            <hr />
            ECCV-2018, Shufflenet v2: Practical guidelines for efficient cnn architecture design <a href="https://openaccess.thecvf.com/content_ECCV_2018/papers/Ningning_Light-weight_CNN_Architecture_ECCV_2018_paper.pdf">pdf</a><br />
            <br />
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
            <a href="https://zhuanlan.zhihu.com/p/31427288">【知乎】SSD 目标检测</a><br />
            <a href="https://www.yuque.com/docs/share/5da9151c-14ee-4473-8975-28f9badd9197">【语雀】【目标检测实战】Pytorch—SSD 模型训练（VOC 数据集）</a>
        </td>
    </tr>
    <tr>
        <td>YOLO</td>
        <td>detection（one-stage）</td>
        <td>
            YOLO 官网：<a target="_blank" href="https://pjreddie.com/">https://pjreddie.com/</a><br />
            <a target="_blank" href="https://zhuanlan.zhihu.com/p/136382095">【知乎】目标检测之 YOLO 算法：YOLOv1,YOLOv2,YOLOv3,TinyYOLO,YOLOv4,YOLOv5,YOLObile,YOLOF,YOLOX 详解</a><br />
            <hr />
            CVPR-2016, You Only Look Once: Unified, Real-Time Object Detection <a target="_blank" href="https://pjreddie.com/media/files/papers/yolo_1.pdf">pdf</a><br />
            <hr />
            CVPR-2017, YOLO9000: Better, Faster, Stronger <a href="https://openaccess.thecvf.com/content_cvpr_2017/papers/Redmon_YOLO9000_Better_Faster_CVPR_2017_paper.pdf">pdf</a><br />
            <hr />
            arXiv-2018, YOLOv3: An Incremental Improvement <a target="_blank" href="https://pjreddie.com/media/files/papers/YOLOv3.pdf">pdf</a><br />
            <a target="_blank" href="https://zhuanlan.zhihu.com/p/108440835">【知乎】YOLO 之父 Joseph Redmon 宣布退出 CV 界，坦言无法忽视自己工作带来的负面影响</a><br />
            <a target="_blank" href="https://www.bilibili.com/video/BV1Hp4y1y788?spm_id_from=333.1007.top_right_bar_window_default_collection.content.click">【B站】Pytorch 搭建自己的 YOLO3 目标检测平台</a><br />
            <hr />
            arXiv-2020, YOLOv4: Optimal Speed and Accuracy of Object Detection <a href="">pdf</a><br />
            <a target="_blank" href="https://zhuanlan.zhihu.com/p/135909702">【知乎】大神接棒，YOLOv4 来了！</a><br />
            <hr />
            YOLO-v5（非官方承认）：<a target="_blank" href="https://github.com/ultralytics/yolov5">https://github.com/ultralytics/yolov5</a> <br />
            <hr />
            YOLOF：CVPR-2021, You Only Look One-level Feature <a href="https://openaccess.thecvf.com/content/CVPR2021/papers/Chen_You_Only_Look_One-Level_Feature_CVPR_2021_paper.pdf">pdf</a><br />
            <hr />
            YOLOX：arXiv-2021, Exceeding YOLO Series in 2021 <a href="https://arxiv.org/pdf/2107.08430v2.pdf">pdf</a><br />
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
            <a target="_blank" href="https://arxiv.org/abs/1708.02002">RetinaNet</a> 2017
        </td>
        <td>detection</td>
        <td>
            <a target="_blank" href="https://zhuanlan.zhihu.com/p/346198300">【知乎】轻松掌握 MMDetection 中常用算法(一)：RetinaNet 及配置详解</a>
        </td>
    </tr>
    <tr>
        <td>PointRCNN 2019</td>
        <td>3D detection</td>
        <td>
            <a target="_blank" href="https://www.bilibili.com/video/BV1cE411L7mL?spm_id_from=333.1007.top_right_bar_window_default_collection.content.click">【B站】PointRCNN & Part-A2 Net</a>
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
            <a target="_blank" href="https://github.com/mli/paper-reading">https://github.com/mli/paper-reading</a> <br />
            <a href="https://github.com/amusi/CVPR2022-Papers-with-Code">https://github.com/amusi/CVPR2022-Papers-with-Code</a>
        </td>
    </tr>
</table>

## 参考资料
- [2021 年 CV 算法工程师技术入门路线图](https://jishuin.proginn.com/p/763bfbd5cab6)
- [综述计算机视觉五大技术：图像分类、对象检测、目标跟踪、语义分割和实例分割](https://bbs.cvmart.net/articles/655/1)

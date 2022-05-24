# 计算机视觉 Computer Vision

## 前置课程
- [《数字图像处理 · 第四版（DIP4E）》](https://book.douban.com/subject/35075811/)
- [《动手学深度学习》](https://zh.d2l.ai/index.html)

## 后置课程
- [《机器学习系统：设计和实现》](https://openmlsys.github.io/)

## 相关顶会
- CVPR, Internaltional Conference on Computer Vision and Pattern Recogintion
- ICCV, IEEE International Conference on Computer Vision
- ECCV, Europeon Conference on Computer Vision
- NeurIPS, Conference and Workshop on Neural Information Processing Systems

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
- https://www.payititi.com/
- https://aistudio.baidu.com/aistudio/datasetoverview
- https://www.kaggle.com/datasets

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

## 论文精读 & 复现

<table>
    <tr>
        <td>LeNet 1989</td>
    </tr>
    <tr>
        <td>
            <a href="https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf">AlexNet</a> 2012 
        </td>
        <td>classification</td>
        <td>
            卷积神经网络（Convolutional Neural Network, CNN）在大规模数据集的开篇巨作。网络结构：5 卷积 + 3 全连接<br />
            <br />
            <a href="https://www.bilibili.com/video/BV1ih411J7Kz/">【B站】9年后重读深度学习奠基作之一：AlexNet【论文精读】by 李沐</a><br />
            <a href="https://www.bilibili.com/video/BV1hq4y157t1/">【B站】AlexNet 论文逐段精读【论文精读】by 李沐</a>
        </td>
    </tr>
    <tr>
        <td>VGG 2014</td>
    </tr>
    <tr>
        <td>ResNet 2015</td>
        <td>classification</td>
        <td>
            残差网络 <br />
            <br />
            <a href="https://www.bilibili.com/video/BV1Fb4y1h73E/?spm_id_from=333.788">【B站】撑起计算机视觉半边天的 ResNet【论文精读】by 李沐</a> <br />
            <a href="https://www.bilibili.com/video/BV1P3411y7nn/?spm_id_from=333.788.recommend_more_video.0">【B站】ResNet 论文逐段精读【论文精读】by 李沐</a>
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
        <td>YOLO-v1 2016</td>
        <td>detection</td>
        <td>
            You Only Look Once: Unified, Real-Time Object Detection <a href="https://pjreddie.com/media/files/papers/yolo_1.pdf">pdf</a><br />
            <br />
            官网：<a href="https://pjreddie.com/">https://pjreddie.com/</a><br />
            <br />
            <a href="https://zhuanlan.zhihu.com/p/136382095">【知乎】目标检测之 YOLO 算法：YOLOv1,YOLOv2,YOLOv3,TinyYOLO,YOLOv4,YOLOv5,YOLObile,YOLOF,YOLOX 详解</a>
        </td>
    </tr>
    <tr>
        <td>YOLO-v2 2017</td>
        <td>detection</td>
        <td>
            YOLO9000: Better, Faster, Stronger <br />
        </td>
    </tr>
    <tr>
        <td>YOLO-v3 2018</td>
        <td>detection</td>
        <td>
            YOLOv3: An Incremental Improvement <a href="https://pjreddie.com/media/files/papers/YOLOv3.pdf">pdf</a><br />
            <br />
            <a href="https://zhuanlan.zhihu.com/p/108440835">【知乎】YOLO 之父 Joseph Redmon 宣布退出 CV 界，坦言无法忽视自己工作带来的负面影响</a><br />
            <a href="https://www.bilibili.com/video/BV1Hp4y1y788?spm_id_from=333.1007.top_right_bar_window_default_collection.content.click">【B站】Pytorch 搭建自己的 YOLO3 目标检测平台</a>
        </td>
    </tr>
    <tr>
        <td>YOLO-v4 2020</td>
        <td>detection</td>
        <td>
            YOLOv4: Optimal Speed and Accuracy of Object Detection <br />
            <br />
            <a href="https://zhuanlan.zhihu.com/p/135909702">【知乎】大神接棒，YOLOv4 来了！</a>
        </td>
    </tr>
    <tr>
        <td>YOLO-v5 2020</td>
        <td>detection</td>
        <td>
            <a href="https://github.com/ultralytics/yolov5">https://github.com/ultralytics/yolov5</a> <br />
        </td>
    </tr>
    <tr>
        <td>YOLOF 2021</td>
        <td>detection</td>
        <td>
            YOLOF: You Only Look One-level Feature <br />
        </td>
    </tr>
    <tr>
        <td>YOLOX 2021</td>
        <td>detection</td>
        <td>
            YOLOX: Exceeding YOLO Series in 2021 <br />
        </td>
    </tr>
    <tr>
        <td>SSD 2015</td>
        <td>detection</td>
        <td>Single Shot MultiBox Detector</td>
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
        <td>MobileNet</td>
        <td>轻量级主干网络</td>
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
            <a href="https://github.com/mli/paper-reading">https://github.com/mli/paper-reading</a>
        </td>
    </tr>
</table>

## 参考资料
- [2021 年 CV 算法工程师技术入门路线图](https://jishuin.proginn.com/p/763bfbd5cab6)
- [综述计算机视觉五大技术：图像分类、对象检测、目标跟踪、语义分割和实例分割](https://bbs.cvmart.net/articles/655/1)

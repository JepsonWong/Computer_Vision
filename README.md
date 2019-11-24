# 计算机视觉 (Computer Vision)

## 图像分类 (Image Classification)

## 目标检测 (Object Detection)

* R-CNN
* Fast RCNN
* Faster R-CNN
* YOLO

## 语义分割 (Semantic Segmentation)

per-pixel class labels

* FCN
* SegNet
* Dilated Convolution Net
* DeconvolutionNet
* DANet: Dual Attention Network for Scene Segmentation

### DANet

We append two types of attention modules on top of dilated FCN, which model the semantic interdependencies in spatial and channel dimensions respectively.

[Non-local Neural Networks及自注意力机制思考](https://blog.csdn.net/l7H9JA4/article/details/85815753)

[双重注意力网络：中科院自动化所提出新的自然场景图像分割框架（附源码）](http://bbs.cvmart.net/topics/634/1)

[Dual Attention Network for Scene Segmentation](https://www.jianshu.com/p/06742d8bd8ff)

## 实例分割 (Instance Segmentation)

目标检测 + 语义分割 (per-object mask and class label)

* Instance-aware Semantic Segmentation via Multi-task Network Cascades
* Instance-sensitive Fully Convolutional Networks
* DeepMask
* SharpMask
* MultiPathNet
* Mask R-CNN
* FCIS

## 全景分割 (Panoramic segmentation)

语义分割 + 实例分割 (per-pixel class+instance labels)

# 参考

[实例分割、语义分割、全景分割的区别](https://blog.csdn.net/wangdongwei0/article/details/83013114)

[图像分类、物体检测、物体分割、实例分割、语义分割](https://www.cnblogs.com/augustone/p/10533132.html)

[Instance Segmentation 比 Semantic Segmentation 难很多吗？](https://www.zhihu.com/question/51704852/answer/142762733)

[(重要，未看)深度特征融合---高低层特征融合](https://blog.csdn.net/xys430381_1/article/details/88370733)

[(kaiminghe)Learning Deep Representations for Visual Recognition](http://kaiminghe.com/eccv18tutorial/eccv2018_tutorial_kaiminghe.pdf)

[(重要，未看)一文了解什么是语义分割及常用的语义分割方法有哪些](https://www.jiqizhixin.com/articles/2018-06-04-17)


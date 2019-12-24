# 计算机视觉 (Computer Vision)

## 图像分类 (Image Classification)

* LeNet
* AlexNet：突破
* VGG16/VGG19：网络加深
* Inception v1/v2/v3/v4：增强卷积模块功能（**v1增加了网络的宽度，增加了网络对尺度的适应性**）
* ResNet、ResNetXt（**ResNet和Inception思想的集合**）、DenseNet、SENet（**在ResNet的Block之后增加特征间通道之间的关系**）、SE-ResNeXt（**就是把SENet中bottleneck换成ResNeXt的bottleneck**）

[Res-Family: From ResNet to SE-ResNeXt](https://www.cnblogs.com/Matrix_Yao/p/9563063.html)

[Res-Family: From ResNet to SE-ResNeXt](https://blog.csdn.net/qq_38462278/article/details/82252888)

### Inception

从空间维度来提升信息，**嵌入多尺度信息**，聚合多种不同感受野上的特征来获得性能增益

### ResNet

* 残差模块：Block结构（中间的通道数比较少，会减少参数量，计算会快）

### ResNeXt

结合Inception和ResNet

### SENet

显式建模特征通道之间的相互依赖关系，通过学习的方式来自动获取到每个通道的重要程度，然后按照这个重要程度去提升有用的特征并抑制对当前任务用处不大的特征。**可以把SENet看成是channel-wise的attention**。其包含两个重要结构：

* Squeeze：顺着空间维度进行特征压缩，将每个二维的特征通道变成一个实数，这个实数某种程度上具有全局的感受野。
* Excitation：为每个通道生成权重，建模特征通道间的相关性。
* Reweight：将Excitation输出的权重看作是经过特征选择后每个特征通道的重要性，然后通过乘法逐通道加权到先前的特征上，完成在通道维度上对原始特征的重标定。

对于Inception结构，可以在Inception执行完后加一个SE模块；对于Resnet结构，需要在残差模块Addition前进行加入SE模块，**避免对主干进行scale操作**。

[SENet](http://www.sohu.com/a/161633191_465975)

[PyTorch implementation of SENet](https://github.com/moskomule/senet.pytorch)

## 目标检测 (Object Detection)

* OverFeat
* R-CNN
* Fast RCNN
* Faster R-CNN
* YOLO

RCNN系列：RCNN可以看作是RegionProposal+CNN这一框架的开山之作，在imgenet/voc/mscoco上基本上所有top的方法都是这个框架，可见其影响之大。RCNN的主要缺点是重复计算，后来MSRA的kaiming组的SPPNET做了相应的加速。

OverFeat系列：说的简单一点就是特征提取算子，就相当于SIFT，HOG等这些算子一样。 Along with this paper, we release a feature extractor named “OverFeat”，这是有一篇文献对overfeat定义的原话。

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


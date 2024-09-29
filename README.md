# Introduction

> 图：确定我们的研究方向，使用韦恩图。是**A**: tomato disease分类任务；和**B**：移动设备轻量级图片分类模型的交际。我们的任务是A和B的交集（公共部分）。

- 对西红柿病害进行分类
- 不需要互联网连接, 可以现场拍照识别
- 模型轻量化模型，可在便携设备部署使用
- **Related work**: 选择添加一个

> 图：[图1]<类别1>  | [图2]<类别 2> ....

# This work

- 澳洲广袤的地区没有移动信号覆盖
- 目前很少/几乎没有在澳洲田间使用移动设备对西红柿病虫害进行分类判断的研究
- 大部分深度学习模型需要大量的计算资源

> 图：澳洲移动信号覆盖图

# Contributions
- 提出了轻量级的, 可以in place使用的对西红柿病虫害分类判断的解决方案
- 对不同模型进行对比分析

# Our approach
- Pre-processing:
  - [原始图片, 大小不一] --Resizing--> [227*227标准图像] -|-Data augumentation(Train Only)--> [原始图像旋转, 镜像]--Normalisation--> [图片背景等颜色调节]

# The Proposed Framework

- 原始图片 -> [Preprocessing] -> [Pretrained base model(MobileNet/Effnet/Transformer)] -> [Dense Layer] -> [Dropout Layer] -> [Softmax Layer] -> [类别0的概率, 类别1的概率,...类别n-1的概率(例如，使用直方图)]

# Base Model 1: MobileNet V2
![mobilenet](https://github.com/jxyzhang/840ss/blob/main/arch-mobilenet.png)
# Base Model 2: EfficientNet
![effnet](https://github.com/jxyzhang/840ss/blob/main/archefficientnet.png)
# Base Model 3: Vit
![vit](https://github.com/jxyzhang/840ss/blob/main/archvit.png)

# Results
- 在Taiwan和PlantVillage数据集上进行测试(...url)
> 图：把result.xlsx文件作为图片
> 图：训练过程准确率提升的图片(optional)

# Conclusion
- We proposed
  -  一个轻量级的可用于移动设备的西红薯病虫害分类的解决方法/模型
  -  适用于信号不能覆盖, 缺乏大量计算资源的场景
- We demonstrated
  - 我们的模型能够在不同数据集上取得较高的准确率(>95%)
  - Vit/Transformer模型相对其他作为base model准确率更高

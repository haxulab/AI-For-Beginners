# 人体分割

来自 [AI for Beginners Curriculum](https://github.com/microsoft/ai-for-beginners) 的实验作业。

## 任务

在视频制作中，例如在天气预报中，我们经常需要将相机中的人体图像剪切出来并将其放置在其他镜头之上。这通常通过 **色度键** 技术完成，当人类在一个均匀的颜色背景前拍摄时，该背景随后被去除。在本实验中，我们将训练一个神经网络模型来剪切人体轮廓。

## 数据集

我们将使用来自Kaggle的 [Segmentation Full Body MADS Dataset](https://www.kaggle.com/datasets/tapakah68/segmentation-full-body-mads-dataset)。请从Kaggle手动下载该数据集。

## 声明Notebook

通过打开 [BodySegmentation.ipynb](BodySegmentation.ipynb) 开始实验。

## 收获

人体分割只是我们可以使用人物图像进行的常见任务之一。其他重要任务还包括 **骨架检测** 和 **姿态检测**。查看 [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) 库，了解这些任务如何实现。
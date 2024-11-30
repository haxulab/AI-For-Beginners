# 宠物脸分类

来自 [AI for Beginners Curriculum](https://github.com/microsoft/ai-for-beginners) 的实验任务。

## 任务

想象一下，您需要为宠物托儿所开发一个应用程序来分类所有的宠物。这样一个应用程序的一个绝佳功能是可以通过一张照片自动识别出宠物的品种。这可以通过神经网络成功地完成。

您需要训练一个卷积神经网络来使用 **Pet Faces** 数据集对不同品种的猫和狗进行分类。

## 数据集

我们将使用 **Pet Faces** 数据集，其来源于 [Oxford-IIIT](https://www.robots.ox.ac.uk/~vgg/data/pets/) 宠物数据集。它包含35种不同品种的猫和狗。

![我们将处理的数据集](images/data.png)

要下载数据集，请使用以下代码片段：

```python
!wget https://mslearntensorflowlp.blob.core.windows.net/data/petfaces.tar.gz
!tar xfz petfaces.tar.gz
!rm petfaces.tar.gz
```

## 开始笔记本

通过打开 [PetFaces.ipynb](PetFaces.ipynb) 来开始这次实验任务

## 收获

您已经从头解决了一个相对复杂的图像分类问题！有很多类别，您仍然能够获得合理的准确性！因为一些即使对人类来说也不是明显不同的类别很容易混淆，所以衡量 top-k 准确率也是有意义的。
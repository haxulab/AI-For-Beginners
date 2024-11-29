# 使用迁移学习对牛津宠物进行分类

[AI for Beginners Curriculum](https://github.com/microsoft/ai-for-beginners) 的实验作业。

## 任务

想象你需要开发一个宠物托儿所应用程序来为所有宠物进行分类。这样的应用程序的一个重要功能将是从照片中自动识别宠物的品种。在此作业中，我们将使用迁移学习来对 [Oxford-IIIT](https://www.robots.ox.ac.uk/~vgg/data/pets/) 宠物数据集中的真实宠物图像进行分类。

## 数据集

我们将使用原始的 [Oxford-IIIT](https://www.robots.ox.ac.uk/~vgg/data/pets/) 宠物数据集，该数据集中包含35种不同品种的狗和猫。

要下载数据集，请使用以下代码片段:

```python
!wget https://www.robots.ox.ac.uk/~vgg/data/pets/data/images.tar.gz
!tar xfz images.tar.gz
!rm images.tar.gz
```

## 启动笔记本

通过打开 [OxfordPets.ipynb](OxfordPets.ipynb) 来启动实验。

## 收获

迁移学习和预训练网络使我们能够相对轻松地解决现实世界的图像分类问题。然而，预训练网络在处理相似类型的图像效果较好，如果我们开始分类完全不同的图像（例如医疗图像），我们可能会得到更差的结果。
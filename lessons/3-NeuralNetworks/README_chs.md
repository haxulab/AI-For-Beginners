# 神经网络介绍

![神经网络介绍内容摘要](../sketchnotes/ai-neuralnetworks.png)

如我们在介绍中讨论的那样，实现智能的一种方式是训练一个**计算机模型**或一个**人工大脑**。自20世纪中叶以来，研究人员尝试了不同的数学模型，直到最近几年这种方向才被证明是非常成功的。这些大脑的数学模型称为**神经网络**。

> 有时神经网络被称为*人工神经网络*，即ANNs，用以表明我们讨论的模型，而不是真正的神经元网络。

## 机器学习

神经网络属于一个更大的学科，称为**机器学习**，其目标是使用数据训练能够解决问题的计算机模型。机器学习构成了人工智能的很大一部分，然而，我们在本课程中不涵盖经典的机器学习。

> 访问我们的独立课程 **[初学者的机器学习](http://github.com/microsoft/ml-for-beginners)** 以了解更多关于经典机器学习的信息。

在机器学习中，我们假设有一些例子数据集**X**和相应的输出值**Y**。例子通常是由**特征**组成的N维向量，而输出称为**标签**。

我们将考虑两种最常见的机器学习问题：

* **分类**，我们需要将输入对象分类为两个或多个类别。
* **回归**，我们需要预测每个输入样本的数值。

> 当将输入和输出表示为张量时，输入数据集是大小为M&times;N的矩阵，其中M是样本数，N是特征数。输出标签Y是大小为M的向量。

在本课程中，我们将只关注神经网络模型。

## 神经元模型

从生物学我们知道，大脑由神经细胞组成，每个神经细胞具有多个“输入”（轴突）和一个输出（树突）。轴突和树突可以传导电信号，且它们之间的连接可以表现出不同程度的传导性（由神经递质控制）。

![神经元模型](images/synapse-wikipedia.jpg) | ![神经元模型](images/artneuron.png)
----|----
真实神经元 *（[图片](https://en.wikipedia.org/wiki/Synapse#/media/File:SynapseSchematic_lines.svg)来自维基百科）* | 人工神经元 *（图片来自作者）*

因此，神经元的最简单数学模型包含多个输入X<sub>1</sub>, ..., X<sub>N</sub> 和一个输出Y，以及一系列权重W<sub>1</sub>, ..., W<sub>N</sub>。输出的计算如下：

<img src="images/netout.png" alt="Y = f\left(\sum_{i=1}^N X_iW_i\right)" width="131" height="53" align="center"/>

其中f是某种非线性**激活函数**。

> 早期的神经元模型在1943年由Warren McCullock和Walter Pitts的经典论文 [《神经活动中的逻辑演算》](https://www.cs.cmu.edu/~./epxing/Class/10715/reading/McCulloch.and.Pitts.pdf) 中进行了描述。Donald Hebb在他的书 "[行为的组织：神经心理学理论](https://books.google.com/books?id=VNetYrB8EBoC)" 中提出了这些网络的训练方法。

## 本章节内容

在本章节中我们将学习：
* [感知器](03-Perceptron/README.md)，一种最早的两类分类神经网络模型
* [多层网络](04-OwnFramework/README.md) 和配套笔记本 [如何构建我们自己的框架](04-OwnFramework/OwnFramework.ipynb)
* [神经网络框架](05-Frameworks/README.md)，包括以下笔记本：[PyTorch](05-Frameworks/IntroPyTorch.ipynb) 和 [Keras/Tensorflow](05-Frameworks/IntroKerasTF.ipynb)
* [过拟合](05-Frameworks#overfitting)
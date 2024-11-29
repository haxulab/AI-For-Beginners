# 语言建模

语义嵌入，例如Word2Vec和GloVe，实际上是**语言建模**的第一步——创建一种能够*理解*（或*表示*）语言本质的模型。

## [课前测验](https://red-field-0a6ddfd03.1.azurestaticapps.net/quiz/115)

语言建模背后的主要思想是以无监督方式在未标记的数据集上进行训练。这很重要，因为我们有大量的未标记文本可用，而标记文本的数量总是受到我们可以花费在标记上的努力的限制。通常，我们可以构建语言模型来**预测文本中缺失的单词**，因为在文本中随机屏蔽一个单词并用它作为训练样本是很容易的。

## 训练嵌入

在之前的例子中，我们使用了预训练的语义嵌入，但看看这些嵌入是如何训练的也是很有趣的。有几种可能的想法可以使用：

* **N-Gram**语言建模，我们通过查看前N个标记（N-gram）来预测一个标记
* **连续词袋模型**（CBoW），我们在一个标记序列$W_{-N}$, ..., $W_N$中预测中间标记$W_0$
* **跳词模型**（Skip-gram），我们从中间标记$W_0$预测一组相邻标记{$W_{-N},\dots, W_{-1}, W_1,\dots, W_N$}

![来自论文的图像,展示了将单词转换为向量的算法示例](../14-Embeddings/images/example-algorithms-for-converting-words-to-vectors.png)

> 图片来自[这篇论文](https://arxiv.org/pdf/1301.3781.pdf)

## ✍️ 示例笔记本：训练CBoW模型

在以下笔记本中继续学习：

* [使用TensorFlow训练CBoW Word2Vec](CBoW-TF.ipynb)
* [使用PyTorch训练CBoW Word2Vec](CBoW-PyTorch.ipynb)

## 结论

在上一课中，我们看到了单词嵌入的神奇之处！现在我们知道训练单词嵌入并不是一项非常复杂的任务，如果需要的话，我们应该能够训练我们自己的领域特定文本的单词嵌入。

## [课后测验](https://red-field-0a6ddfd03.1.azurestaticapps.net/quiz/215)

## 复习与自学

* [官方PyTorch语言建模教程](https://pytorch.org/tutorials/beginner/nlp/word_embeddings_tutorial.html)
* [官方TensorFlow训练Word2Vec模型教程](https://www.TensorFlow.org/tutorials/text/word2vec)
* 在**gensim**框架中使用几行代码训练最常用的嵌入的描述[在此文档](https://pytorch.org/tutorials/beginner/nlp/word_embeddings_tutorial.html)

## 🚀 [任务：训练Skip-Gram模型](lab/README.md)

在实验中，我们挑战你修改本课的代码来训练跳词（Skip-gram）模型而不是CBoW。[阅读详情](lab/README.md)
# 训练 Skip-Gram 模型

来自 [AI for Beginners 课程](https://github.com/microsoft/ai-for-beginners) 的实验任务。

## 任务

在本实验中，我们挑战你使用 Skip-Gram 技术训练 Word2Vec 模型。训练一个带有嵌入的网络来预测 $N$ 个词令宽 Skip-Gram 窗口中的相邻词。你可以使用[本课的代码](../CBoW-TF.ipynb)，并稍微修改它。

## 数据集

你可以使用任何书籍。在 [Project Gutenberg](https://www.gutenberg.org/) 可以找到许多免费文本，例如，这里是刘易斯·卡罗尔的[爱丽丝梦游仙境](https://www.gutenberg.org/files/11/11-0.txt)的直接链接。或者，你可以使用莎士比亚的剧作，可以使用以下代码获取：

```python
path_to_file = tf.keras.utils.get_file(
   'shakespeare.txt', 
   'https://storage.googleapis.com/download.tensorflow.org/data/shakespeare.txt')
text = open(path_to_file, 'rb').read().decode(encoding='utf-8')
```

## 探索！

如果你有时间并且想深入研究这个主题，尝试探索几件事：

* 嵌入维度对结果有何影响？
* 不同的文本风格对结果有何影响？
* 选择几种非常不同类型的词及其同义词，获取它们的向量表示，应用 PCA 将维度减少到 2，并将它们绘制在二维空间中。你能看到任何模式吗？

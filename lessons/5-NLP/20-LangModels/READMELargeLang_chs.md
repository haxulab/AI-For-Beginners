# 预训练大语言模型

在我们之前的所有任务中，我们都是使用标注数据集来训练神经网络以执行某项任务。而对于大型transformer模型如BERT，我们使用自监督方式进行语言建模，构建出一个语言模型，然后经过进一步的领域特定训练，将其专门化用于具体的下游任务。然而，已经证明了大型语言模型也可以在没有任何领域特定训练的情况下解决许多任务。这种能够做到这一点的一类模型被称为**GPT**：生成预训练转换器。

## [课前测验](https://red-field-0a6ddfd03.1.azurestaticapps.net/quiz/120)

## 文本生成和困惑度

在[《语言模型是无监督的多任务学习者》](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf)论文中，提出了神经网络能够在没有下游训练的情况下完成一般任务的想法。主要思想是很多其他任务可以通过**文本生成**来建模，因为理解文本本质上意味着能够生成文本。由于模型训练在包含人类知识的大量文本数据上，它因此也了解广泛的主题。

> 理解和生成文本也意味着对周围世界有所了解。人类也在很大程度上通过阅读来学习，GPT网络在这方面类似。

文本生成网络通过预测下一个单词的概率$$P(w_N)$$来工作。然而，下一个单词的无条件概率等于这个单词在文本中的频率。GPT能够给出**下一个单词的条件概率**（给定前面的单词）：$$P(w_N | w_{n-1}, ..., w_0)$$

> 您可以在我们的[初学者数据科学课程](https://github.com/microsoft/Data-Science-For-Beginners/tree/main/1-Introduction/04-stats-and-probability)中阅读更多关于概率的内容。

语言生成模型的质量可以用**困惑度**来定义。这是一个内在的度量，允许我们在没有任何任务特定数据集的情况下衡量模型的质量。这基于*句子的概率*的概念——模型对看似真实的句子赋予高概率（即，模型并不**感到困惑**），而对不合理的句子（例如*它会做什么？*）赋予低概率。当我们提供给模型来自真实文本语料库的句子时，我们希望它们具有高概率和低**困惑度**。数学上，它定义为测试集的归一化逆概率：
$$
\mathrm{Perplexity}(W) = \sqrt[N]{1\over P(W_1,...,W_N)}
$$ 

**您可以使用[来自Hugging Face的GPT驱动的文本编辑器](https://transformer.huggingface.co/doc/gpt2-large) 实验文本生成**。在这个编辑器中，您开始编写文本，按**[TAB]**键将为您提供多个完成选项。如果它们太短或您不满意，按[TAB]键，您将有更多选项，包括更长的文本片段。

## GPT是一个家族

GPT不是单一模型，而是一组由[OpenAI](https://openai.com)开发和训练的模型。

在GPT模型下，我们有：

| [GPT-2](https://huggingface.co/docs/transformers/model_doc/gpt2#openai-gpt2) | [GPT 3](https://openai.com/research/language-models-are-few-shot-learners) | [GPT-4](https://openai.com/gpt-4) |
| -- | -- | -- |
|语言模型，参数多达15亿| 语言模型，参数多达1750亿 | 100万亿参数并接受图像和文本输入，输出文本。|

GPT-3和GPT-4模型可通过[来自Microsoft Azure的认知服务](https://azure.microsoft.com/en-us/services/cognitive-services/openai-service/#overview?WT.mc_id=academic-77998-cacaste)以及[OpenAI API](https://openai.com/api/)获取。

## 提示工程

由于GPT经过大量数据的训练以理解语言和代码，它们在响应输入（提示）时提供输出。提示是GPT的输入或查询，通过这些输入，用户为模型提供下一步完成任务的说明。为了引出所需的结果，您需要最有效的提示，这涉及选择正确的单词、格式、短语甚至符号。这种方法称为[提示工程](https://learn.microsoft.com/en-us/shows/ai-show/the-basics-of-prompt-engineering-with-azure-openai-service?WT.mc_id=academic-77998-bethanycheum)。

[本文档](https://learn.microsoft.com/en-us/semantic-kernel/prompt-engineering/?WT.mc_id=academic-77998-bethanycheum)提供了有关提示工程的更多信息。

## ✍️ 示例笔记本: [使用OpenAI-GPT进行实验](GPT-PyTorch.ipynb)

在以下笔记本中继续您的学习：

* [使用OpenAI-GPT和Hugging Face Transformers生成文本](GPT-PyTorch.ipynb)

## 结论

新的通用预训练语言模型不仅建模语言结构，还包含大量的自然语言。因此，它们可以在零样本或少量样本设置中有效解决一些NLP任务。

## [课后测验](https://red-field-0a6ddfd03.1.azurestaticapps.net/quiz/220)
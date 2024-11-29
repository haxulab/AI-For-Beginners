# 命名实体识别（NER）

来自 [AI for Beginners Curriculum](https://github.com/microsoft/ai-for-beginners) 的实验任务。

## 任务

在本次实验中，您需要训练一个用于医学术语的命名实体识别模型。

## 数据集

要训练 NER 模型，我们需要一个适当标注了医学实体的数据集。[BC5CDR 数据集](https://biocreative.bioinformatics.udel.edu/tasks/biocreative-v/track-3-cdr/) 包含了从1500多篇论文中标注的疾病和化学实体。您可以在他们的网站注册后下载数据集。

BC5CDR 数据集如下所示：

```
6794356|t|新生儿三尖瓣返流和碳酸锂中毒。
6794356|a|描述了一名有大量三尖瓣返流、心房扑动、充血性心力衰竭和高血清锂水平的新生儿。这是第一例最初表现为三尖瓣返流和心房扑动的患者，也是第11例在怀孕早期暴露于锂化合物的婴儿中的具有心脏病的患者。这些婴儿中63％有三尖瓣参与。碳酸锂可能是怀孕早期服用时先天性心脏病发病率增加的因素之一。它在分娩前食用时还会导致神经抑制、青紫症和心律不齐。
6794356	0	29	三尖瓣返流	疾病	D014262
6794356	34	51	碳酸锂	化学品	D016651
6794356	52	60	毒性	疾病	D064420
...
```

在这个数据集中，第一行是论文的标题，第二行是摘要，接着是每个独立的实体及其在标题+摘要块中的起始和结束位置。除了实体类型，还会给出该实体在某个医学本体中的本体ID。

您需要编写一些Python代码将其转换为BIO编码格式。

## 网络

首次尝试NER可以使用LSTM网络，就像您在课程中看到的例子一样。然而，在NLP任务中，[转换器架构](https://en.wikipedia.org/wiki/Transformer_(machine_learning_model))，尤其是[BERT语言模型](https://en.wikipedia.org/wiki/BERT_(language_model))，显示出更好的结果。预训练的BERT模型理解语言的总体结构，并可以用相对较小的数据集和计算成本进行针对具体任务的微调。

由于我们计划将NER应用于医疗场景，因此使用在医疗文本上训练的BERT模型是有意义的。微软研究院发布了一个预训练模型，称为[PubMedBERT][PubMedBERT]（[发表文章][PubMedBERT-Pub]），该模型使用[PubMed](https://pubmed.ncbi.nlm.nih.gov/)库中的文本微调过。

训练转换器模型的事实上的标准是[Hugging Face Transformers](https://huggingface.co/)库。它还包含了一个社区维护的预训练模型库，包括PubMedBERT。要加载并使用此模型，我们只需几行代码：

```python
model_name = "microsoft/BiomedNLP-PubMedBERT-base-uncased-abstract"
classes = ... # 类别数量：2*实体+1
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = BertForTokenClassification.from_pretrained(model_name, classes)
```

这为我们提供了一个 `model`，它针对标记分类任务构建，使用 `classes` 数量的类别，还有一个 `tokenizer` 对象，可以将输入文本拆分为标记。您需要将数据集转换为BIO格式，并考虑PubMedBERT的分词。您可以使用[这段Python代码](https://gist.github.com/shwars/580b55684be3328eb39ecf01b9cbbd88)作为灵感。

## 收获

这个任务非常接近实际中的任务，如果您想深入分析大量自然语言文本。在我们的案例中，我们可以将我们训练的模型应用于[与COVID相关的论文数据集](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge)，看看我们能得到哪些见解。[这篇博客文章](https://soshnikov.com/science/analyzing-medical-papers-with-azure-and-text-analytics-for-health/) 和 [这篇论文](https://www.mdpi.com/2504-2289/6/1/4) 描述了使用NER在这批文献语料库上可以进行的研究。
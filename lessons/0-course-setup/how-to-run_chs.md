# 如何运行代码

本课程包含大量可执行示例和实验，您可能希望运行这些内容。为了做到这一点，您需要能够在本课程提供的 Jupyter 笔记本中执行 Python 代码。您有几种运行代码的选择：

## 在您自己的计算机上本地运行

要在本地计算机上运行代码，您需要安装某个版本的 Python。我个人推荐安装 **[miniconda](https://conda.io/en/latest/miniconda.html)** - 这是一种相当轻量的安装包，支持用于不同 Python **虚拟环境**的 `conda` 包管理器。

安装 miniconda 后，您需要克隆仓库并创建用于本课程的虚拟环境：

```bash
git clone http://github.com/microsoft/ai-for-beginners
cd ai-for-beginners
conda env create --name ai4beg --file .devcontainer/environment.yml
conda activate ai4beg
```

### 使用带 Python 扩展的 Visual Studio Code

使用本课程的最佳方式可能是通过 [Visual Studio Code](http://code.visualstudio.com/?WT.mc_id=academic-77998-cacaste) 结合 [Python 扩展](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-77998-cacaste) 打开它。

> **注意**: 克隆并在 VS Code 中打开目录后，它将自动建议您安装 Python 扩展。您还需要按照上述说明安装 miniconda。

> **注意**: 如果 VS Code 建议您在容器中重新打开仓库，您需要拒绝以使用本地 Python 安装。

### 使用浏览器中的 Jupyter

您也可以直接在浏览器中使用您自己的计算机运行 Jupyter 环境。实际上，经典的 Jupyter 和 Jupyter Hub 都提供了相当方便的开发环境，具有自动完成、代码高亮等功能。

要在本地启动 Jupyter，请转到课程目录并执行：

```bash
jupyter notebook
```
或
```bash
jupyterhub
```
然后您可以导航到任何 `.ipynb` 文件，打开它们并开始工作。

### 在容器中运行

Python 安装的一个替代方案是在容器中运行代码。因为我们的仓库包含一个特殊的 `.devcontainer` 文件夹，指示如何为该仓库构建容器，VS Code 将为您提供在容器中重新打开代码的选项。这需要 Docker 安装，并且会更复杂，因此我们建议更有经验的用户使用这种方法。

## 在云中运行

如果您不想在本地安装 Python，并且可以访问一些云资源 - 一个不错的替代方案是在云中运行代码。您可以通过以下几种方式实现：

* 使用 **[GitHub Codespaces](https://github.com/features/codespaces)**，这是一个在 GitHub 上为您创建的虚拟环境，通过 VS Code 浏览器界面访问。如果您可以访问 Codespaces，只需点击仓库中的 **Code** 按钮，启动一个代码空间，不久就可以开始运行。
* 使用 **[Binder](https://mybinder.org/v2/gh/microsoft/ai-for-beginners/HEAD)**。[Binder](https://mybinder.org) 是在云中为人们提供的免费计算资源，用于测试 GitHub 上的一些代码。在主页上有一个按钮可以在 Binder 中打开仓库 - 这会迅速将您带到 Binder 网站，它会为您无缝构建底层容器并启动 Jupyter 网页界面。

> **注意**: 为防止滥用，Binder 已屏蔽了某些网页资源的访问。这可能会阻止一些代码运行，这些代码从公共互联网获取模型和/或数据集。您可能需要找到一些解决方法。此外，由于 Binder 提供的计算资源相当基础，因此在后期更复杂的课程中，训练速度会很慢。

## 使用 GPU 在云中运行

本课程中的一些后续内容将大大受益于 GPU 支持，否则训练将非常慢。如果您通过 [Azure for Students](https://azure.microsoft.com/free/students/?WT.mc_id=academic-77998-cacaste) 或通过您的机构访问云，有几种选择：

* 创建 [Data Science Virtual Machine](https://docs.microsoft.com/learn/modules/intro-to-azure-data-science-virtual-machine/?WT.mc_id=academic-77998-cacaste) 并通过 Jupyter 连接到它。然后您可以在该机器上克隆仓库并开始学习。NC系列虚拟机支持 GPU。

> **注意**: 包括 Azure for Students 在内的一些订阅不默认提供 GPU 支持。您可能需要通过技术支持请求额外的 GPU 内核。

* 创建 [Azure Machine Learning Workspace](https://azure.microsoft.com/services/machine-learning/?WT.mc_id=academic-77998-cacaste) 并使用其中的 Notebook 功能。 [这段视频](https://azure-for-academics.github.io/quickstart/azureml-papers/) 演示了如何将存储库克隆到 Azure ML 笔记本并开始使用它。

您也可以使用 Google Colab，它提供一些免费的 GPU 支持，并上传 Jupyter 笔记本在其中逐一执行。
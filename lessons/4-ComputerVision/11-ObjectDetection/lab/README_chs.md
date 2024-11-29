# 使用Hollywood Heads数据集进行头部检测

[AI for Beginners Curriculum](https://github.com/microsoft/ai-for-beginners)的实验作业。

## 任务

在视频监控摄像机流中计算人数是一个重要的任务，它可以帮助我们估算商店的访客数量、餐馆的繁忙时间等。要解决这个任务，我们需要能够从不同角度检测人头。为了训练对象检测模型来检测人头，我们可以使用[Hollywood Heads数据集](https://www.di.ens.fr/willow/research/headdetection/)。

## 数据集

[Hollywood Heads数据集](https://www.di.ens.fr/willow/research/headdetection/release/HollywoodHeads.zip)包含在224,740张好莱坞电影帧中的369,846个人头。它以[PASCAL VOC](https://host.robots.ox.ac.uk/pascal/VOC/)格式提供，对于每张图片都有一个XML描述文件，如下所示：

```xml
<annotation>
	<folder>HollywoodHeads</folder>
	<filename>mov_021_149390.jpeg</filename>
	<source>
		<database>HollywoodHeads 2015 Database</database>
		<annotation>HollywoodHeads 2015</annotation>
		<image>WILLOW</image>
	</source>
	<size>
		<width>608</width>
		<height>320</height>
		<depth>3</depth>
	</size>
	<segmented>0</segmented>
	<object>
		<name>head</name>
		<bndbox>
			<xmin>201</xmin>
			<ymin>1</ymin>
			<xmax>480</xmax>
			<ymax>263</ymax>
		</bndbox>
		<difficult>0</difficult>
	</object>
	<object>
		<name>head</name>
		<bndbox>
			<xmin>3</xmin>
			<ymin>4</xmin>
			<xmax>241</xmax>
			<ymax>285</ymax>
		</bndbox>
		<difficult>0</difficult>
	</object>
</annotation>
```

在这个数据集中，只有一类对象`head`，对于每一个头部，你将获得边界框的坐标。你可以使用Python库解析XML，或者使用[这个库](https://pypi.org/project/pascal-voc/)直接处理PASCAL VOC格式。

## 训练对象检测

你可以使用以下几种方式来训练一个对象检测模型：

* 使用[Azure Custom Vision](https://docs.microsoft.com/azure/cognitive-services/custom-vision-service/quickstarts/object-detection?tabs=visual-studio&WT.mc_id=academic-77998-cacaste)和它的Python API来编程化地在云中训练模型。Custom Vision不能使用超过几百张图像来训练模型，所以你可能需要限制数据集。
* 使用[Keras教程](https://keras.io/examples/vision/retinanet/)中的例子来训练RetunaNet模型。
* 使用[torchvision.models.detection.RetinaNet](https://pytorch.org/vision/stable/_modules/torchvision/models/detection/retinanet.html)中内置的模块。

## 收获

对象检测是工业中频繁需要的任务。虽然有些服务可以用于执行对象检测（例如[Azure Custom Vision](https://docs.microsoft.com/azure/cognitive-services/custom-vision-service/quickstarts/object-detection?tabs=visual-studio&WT.mc_id=academic-77998-cacaste)），了解对象检测的工作原理并能够训练自己的模型是很重要的。
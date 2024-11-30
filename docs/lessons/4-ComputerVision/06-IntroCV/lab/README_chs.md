# 使用光流检测运动

来自[面向初学者的AI课程](https://aka.ms/ai-beginners)的实验任务。

## 任务

考虑[这个视频](palm-movement.mp4)，视频中，一个人的手掌在稳定的背景下向左/向右/向上/向下移动。

<img src="../images/palm-movement.png" width="30%" alt="手掌运动帧"/>

**你的目标**是能够使用光流法来确定视频中的哪些部分包含向上/向下/向左/向右的运动。

**扩展目标**是实际使用肤色跟踪手掌/手指的运动，如[这篇博客文章](https://dev.to/amarlearning/finger-detection-and-tracking-using-opencv-and-python-586m)或[这里](http://www.benmeline.com/finger-tracking-with-opencv-and-python/)所描述的那样。

## 起始笔记本

打开[MovementDetection.ipynb](MovementDetection.ipynb)开始实验。

## 收获

有时，诸如运动检测或指尖检测之类的相对复杂的任务可以纯粹通过计算机视觉来解决。因此，了解像OpenCV这样的库能够做什么是非常有帮助的。
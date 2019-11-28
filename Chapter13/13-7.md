---
layout: post
title:  "13-7 Stacking"
category: [liuyubo play with machine-learning]
tags: []
---

> 这个系列课程不错，墙裂推荐  
> 本文只是对课程内容做笔记，建议读者看原视频学习  
> 因为看本文只能知道一些知识点，但看原视频明理解这些知识点  

![](/images/2019/282.jpg)

stackgin的思路：假设使用三个算法分别得到机器学习的结果，但是不像前面那么直接将三个结果综合，而是用这三个算法作为输出，训练一个新的模型，使用这个模型的输出作为最终的输出。  

![](http://windmissing.github.io/images/2019/283.jpg)

训练方法：将数据集分成2分，一份用于训练第一层的3个模型，第二份用于训练第二层的模型。最终得到整体模型。  

这个模型还可以更复杂，比如：
![](http://windmissing.github.io/images/2019/284.jpg)
要训练这个模型需要把数据分成3份，每一份用于训练一层模型。  

这样的模型非常容易过拟合。  
这样的模型有点类似于神经网络。这是深度学习的范畴。  
scikit-learn没有提供stacking模型的接口。
---
layout: post
title:  "11-3 Soft Margin和SVM的正则化"
category: [liuyubo play with machine-learning]
tags: []
---

> 这个系列课程不错，墙裂推荐  
> 本文只是对课程内容做笔记，建议读者看原视频学习  
> 因为看本文只能知道一些知识点，但看原视频明理解这些知识点  

hard Margin:  
![](http://windmissing.github.io/images/2019/220.jpg)  
使用这种方法，对下面这张图中的样本，hard SVM会给出这样一根决策边界
![](http://windmissing.github.io/images/2019/221.jpg)  
hard SVM非常明显地受到一个蓝点的影响，而这个蓝点很有可能是outlier或者是个错误点。  
![](http://windmissing.github.io/images/2019/222.jpg)
这根决策边界可能是一根更好的决策边界。  
而对于下图这样的样本点，线性不可分的情况，hard SVN是无解的。  
![](http://windmissing.github.io/images/2019/223.jpg)
hard SVM需要更好的容错性。  
改进：增加一个宽松量

<!-- more -->

![](http://windmissing.github.io/images/2019/224.jpg)
即允许一些点出现在图中虚线和实线之间的位置。  
这里的宽松量不是一个定值，它对每一个样本都是不同的。  
同时还要最小化所有的宽松量。  
目标函数变成了：
![](http://windmissing.github.io/images/2019/225.jpg)   

# L1正则、L2正则

![](http://windmissing.github.io/images/2019/226.jpg)   

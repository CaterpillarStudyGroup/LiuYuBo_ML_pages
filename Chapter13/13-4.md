---
layout: post
title:  "13-4 更多关于bagging的讨论"
category: [liuyubo play with machine-learning]
tags: []
---

> 这个系列课程不错，墙裂推荐  
> 本文只是对课程内容做笔记，建议读者看原视频学习  
> 因为看本文只能知道一些知识点，但看原视频明理解这些知识点  

OOB：out of bag  
放回取样导致一部分样本很有可能没有取到。  
平均大约有37%的样本没有取到。  
不使用train_test_split，而是使用这部分没有取到的样本做测试/验证。  

<!-- more -->

使用13-1中的数据，但不做train_test_split  

```python
from sklearn.tree import DecisionTreeClassifier
from sklearn.ensemble import BaggingClassifier

bagging_clf = BaggingClassifier(DecisionTreeClassifier(),n_estimators=500, max_samples=100, bootstrap=True, oob_score=True)
bagging_clf.fit(X, y)
bagging_clf.oob_score_
```

输出：0.918  

bagging的思路极易并行化处理，n_jobs  
针对特征进行随机采样： Random Subspaces  
当样本的特征非常多的时使用这种方法，比如图像样本  
既针对样本，又针对特征进行随机采样：Random Patches

## Random Subspaces

```python
random_subspaces_clf = BaggingClassifier(DecisionTreeClassifier(),n_estimators=500, max_samples=500, bootstrap=True, oob_score=True, n_jobs=-1, max_features=1, bootstrap_features=True)
random_subspaces_clf.fit(X, y)
random_subspaces_clf.oob_score_
```

输出：0.838

## Random Patches

```python
random_subspaces_clf = BaggingClassifier(DecisionTreeClassifier(),n_estimators=500, max_samples=100, bootstrap=True, oob_score=True, n_jobs=-1, max_features=1, bootstrap_features=True)
random_subspaces_clf.fit(X, y)
random_subspaces_clf.oob_score_
```

输出：0.874

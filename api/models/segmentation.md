---
title: Segmentation Models
description: List of Networks for Segmentation
published: true
date: 2020-08-24T05:29:52.271Z
tags: 
editor: markdown
---

# [RetinaNet](https://arxiv.org/abs/1708.02002)
Instantiates the retinanet architecture. 

| Backbones supported | `ResNet50` `ResNet101` `ResNet152` `DenseNet121` `DenseNet169` `DenseNet201` `Detnet`|
| -- | --| 


```py
cral.models.object_detection.RetinanetConfig(
    sizes, 
    strides, 
    ratios, 
    scales, 
    min_side, 
    max_side)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | ---- | --- | --- |
|**sizes**|list|[32, 64, 128, 256, 512]|List of sizes to use. Each size corresponds to one feature level|
|**strides**|list|[8, 16, 32, 64, 128]|List of strides to use. Each stride correspond to one feature level|
|**ratios**|list|[0.5, 1, 2]| List of ratios to use per location in a feature map|
|**scales**|list|[1, 1.25, 1.5]|List of scales to use per location in a feature map|
|**min_side**|int|800|the minimum dimension(width in case of portrait mode and height in case of landscape mode) of image for training|
|**max_side**|int|1333|the maximum dimension(height in case of portrait mode and width in case of landscape mode) of image for training|

> For more info about parameters , you can read: [Retinanet hyperparameter tuning](https://blog.segmind.com/an-introduction-to-retinanet-and-how-we-make-it-easier-to-use/).
{.is-info}
---
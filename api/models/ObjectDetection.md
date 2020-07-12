---
title: Object Detection Models
description: 
published: true
date: 2020-07-12T15:37:03.747Z
tags: 
editor: markdown
---

# ObjectDetection Models

## Retinanet
Instantiates the retinanet architecture 
Supports backbones of Resnet and DenseNet family
For more info follow [link](https://blog.segmind.com/an-introduction-to-retinanet-and-how-we-make-it-easier-to-use/)

```py
cral.models.object_detection.RetinanetConfig(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**sizes**|list|.|List of sizes to use. Each size corresponds to one feature level|
|**strides**|list|.|List of strides to use. Each stride correspond to one feature level|
|**ratios**|list|.| List of ratios to use per location in a feature map|
|**scales**|list|.|List of scales to use per location in a feature map|

---

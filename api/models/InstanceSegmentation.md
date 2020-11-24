---
title: Instance Segmentation Models
description: 
published: true
date: 2020-11-24T07:25:08.525Z
tags: 
editor: markdown
dateCreated: 2020-11-24T07:22:16.978Z
---

# [MaskRCNN](https://arxiv.org/pdf/1703.06870.pdf)
Instantiates the Deeplabv3+ architecture. 

| Backbones supported | `Resnet50` `Resnet101` |
| -- | --| 

```py
cral.models.instance_segmentation.MaskRCNNConfig(
    height, 
    width)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|-|Input shape dimension|
|**width**|int|-|Input shape dimension|


---


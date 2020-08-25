---
title: Segmentation Models
description: List of Networks for Segmentation
published: true
date: 2020-08-25T06:00:41.928Z
tags: 
editor: markdown
---
# [Deeplabv3+](https://arxiv.org/pdf/1802.02611.pdf)
Instantiates the Deeplabv3+ architecture. 

| Backbones supported | `Xception` `Resnet50` `Mobilenetv2` |
| -- | --| 

```py
cral.models.semantic_segmentation.Deeplabv3Config(
    height, 
    width, output_stride)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|-|Input shape dimension|
|**width**|int|-|Input shape dimension|
|**output_stride**|int|-|Ratio of the input image size to the output feature map size|


---

# [UNet](https://arxiv.org/pdf/1505.04597.pdf)
Instantiates the UNet architecture. 

| Backbones supported | `VGG16` `VGG19` `Resnet50` `Resnet101` `Resnet152` `Mobilenet` |
| -- | --| 

```py
cral.models.semantic_segmentation.UNetConfig(
    height, 
    width)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|-|Input shape dimension|
|**width**|int|-|Input shape dimension|

---

# [PspNet](https://arxiv.org/pdf/1612.01105.pdf)
Instantiates the PspNet architecture. 

| Backbones supported | `VGG16` `VGG19` `Resnet50` `Resnet101` `Resnet152` `Resnet50v2` `Resnet101v2` `Resnet152v2` `Mobilenet` |
| -- | --| 

```py
cral.models.semantic_segmentation.PspNetConfig(
    height, 
    width)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|-|Input shape dimension|
|**width**|int|-|Input shape dimension|
|**down_sample_factor**|int|8|Ratio of the input image size to the smallest feature map size generated|


---

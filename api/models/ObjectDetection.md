---
title: Object Detection Models
description: List of Networks for Object Detection
published: true
date: 2020-11-23T07:46:12.487Z
tags: 
editor: markdown
dateCreated: 2020-07-12T15:26:21.530Z
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

# [YoloV3](https://pjreddie.com/media/files/papers/YOLOv3.pdf)
Instantiates the YoloV3 architecture. 

| Backbones supported | `DarkNet53` |
| -- | --| 

```py
cral.models.object_detection.YoloV3Config(
    size, 
    anchors, 
    anchor_masks, 
    iou_threshold, 
    score_threshold)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**size**|list|416|All Images will be resized to this size before being fed into the model|
|**anchors**|list|.|List of Anchors with the same scale as size|
|**anchor_masks**|list|.|List of Masks to be used with the anchors|
|**max_boxes**|int|100|Max number of objects that can be present in the images|
|**iou_threshold**|float|0.5|Any bboxes with iou greater thanthreshold will be merged by NMS|
|**score_threshold**|float|0.5| Any prediction with lower score will be ignored in NMS|

---

# [FasterRCNN](https://arxiv.org/pdf/1506.01497.pdf)
Instantiates the FasterRCNN architecture. 

| Backbones supported | `ResNet50` `ResNet101`  |
| -- | --| 

```py
cral.models.object_detection.FasterRCNNConfig(
    height, 
    width)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|list|-|Input Image dimension|
|**width**|list|-|All Images will be resized to this size before being fed into the model|


---
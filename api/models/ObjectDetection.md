---
title: Object Detection Models
description: List of Networks for Object Detection
published: true
date: 2020-08-03T11:09:13.252Z
tags: 
editor: markdown
---

# [RetinaNet](https://arxiv.org/abs/1708.02002)
Instantiates the retinanet architecture. 

| Backbones supported | `ResNet50` `ResNet101` `ResNet152` `DenseNet121` `DenseNet169` `DenseNet201` `Detnet`|
| -- | --| 


```py
cral.models.object_detection.RetinanetConfig(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | ---- | --- | --- |
|**sizes**|list|[32, 64, 128, 256, 512]|List of sizes to use. Each size corresponds to one feature level|
|**strides**|list|[8, 16, 32, 64, 128]|List of strides to use. Each stride correspond to one feature level|
|**ratios**|list|[0.5, 1, 2]| List of ratios to use per location in a feature map|
|**scales**|list|[2\*\*0, 2\*\*(1.0/3.0), 2\*\*(2.0/3.0)]|List of scales to use per location in a feature map|

> For more info about parameters , you can read: [Retinanet hyperparameter tuning](https://blog.segmind.com/an-introduction-to-retinanet-and-how-we-make-it-easier-to-use/).
{.is-info}
---

# [YoloV3](https://pjreddie.com/media/files/papers/YOLOv3.pdf)
Instantiates the YoloV3 architecture. 

| Backbones supported | `DarkNet53` |
| -- | --| 

```py
cral.models.object_detection.Yolov3Config(*args, **kwargs)
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

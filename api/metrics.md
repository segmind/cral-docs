---
title: Metrics
description: Evaluate the performance of your trained model 
published: true
date: 2020-07-31T15:55:32.362Z
tags: 
editor: markdown
---

After training, you can use the model to get predictions on your test set.
Calling `prediction_model` will give you a function, `prediction_func`, that can be used to get predictions on images. Refer [here](https://cral.segmind.com/api/object-detection-pipeline#predict).
```py
prediction_func = pipeline.prediction_model(checkpoint_file)
```

# Object Detection
## [COCO metrics](https://cocodataset.org/#detection-eval)
Evaluates detection using 12 metrics. 


```py
from cral.metrics.object_detection import coco_mAP
coco_mAP(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**prediction_func**|class method|.|prediction function for the trained model|
|**test_images_dir**|str|.|path to test images|
|**test_anno_dir**|str|.|path to test annotations|
|**annotation_format**|str|.|one of `coco` or `pascal_voc`|

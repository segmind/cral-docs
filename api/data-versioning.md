---
title: Data Versioning
description: Version controlling your datasets
published: true
date: 2020-06-13T15:31:31.426Z
tags: 
editor: markdown
---

# cral.data_versioning
Your datasets change over time during the lifecycle of an experiment and your project. New data usually keeps getting added weekly or monthly. Training data plays an important factor in reproducing your experiments and version controlling them helps you achive the same.

## log_classification_dataset 
Parses the classification data and logs the hash to tracking server


```py
cral.data_versioning.log_classification_dataset(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
| **train_images_dir** | string | . | path to images |
|  **val_images_dir** | string | . | (*optional*) path to validation images  |
|  **split** | float | 1          | (*optional*) fraction to divide training dataset into training and validation sets |

---

## log_segmentation_dataset
Parses the segmentation data and logs the hash to tracking server

```py
cral.data_versioning.log_segmentation_dataset(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
| **annotation_format** | enum | coco | Options: `coco` `pascal` |
|  **train_images_dir** | string | . | (*optional*) path to validation images  |
|  **train_anno_dir** | float | 1          | (*optional*) fraction to divide training dataset into training and validation sets |
| **img_to_anno** | function | | Function to convert image name to annotation name |
| **val_images_dir** |
| **val_anno_dir** | 
| **split** |
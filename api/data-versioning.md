---
title: Data Versioning
description: Version controlling your datasets
published: true
date: 2020-06-13T15:14:00.601Z
tags: 
editor: markdown
---

# cral.data_versioning
Your datasets change over time during the lifecycle of an experiment and your project. New data usually keeps getting added weekly or monthly. Training data plays an important factor in reproducing your experiments and version controlling them helps you achive the same.

## log_classification_dataset
Parses the classification data and logs to tracking server


```py
cral.data_versioning.log_classification_dataset()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
| **train_images_dir** | string | . | path to images |
|  **val_images_dir** | string | . | (*optional*) path to validation images  |
|  **split** | float | 1          | (*optional*) fraction to divide training dataset into training and validation sets |
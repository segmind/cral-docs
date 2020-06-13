---
title: Data Versioning
description: Version controlling your datasets
published: true
date: 2020-06-13T14:38:12.367Z
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
|                       | FPN Layer 1 | FPN Layer 2 | FPN Layer 3 | FPN Layer 4 | FPN Layer 5 |
|-----------------------|-------------|-------------|-------------|-------------|-------------|
| scale/size            | 16          | 32          | 64          | 128         | 256         |
|  209/256 = 0.81640625 | 13.0625     | 26.125      | 52.25       | 104.5       | 209         |
|  9/16 = 0.5625        | 9           | 18          | 36          | 72          | 144         |
|  310/256 =  1.2109375 | 19.375      | 38.75       | 77.5        | 155         | 310         |
|  107/128 = 0.8359375  | 13.375      | 26.75       | 53.5        | 107         | 214         |

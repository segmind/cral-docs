---
title: Release Notes
description: Version update notes for CRAL
published: true
date: 2020-08-27T11:17:20.673Z
tags: 
editor: markdown
---

# Release Notes
## 0.3.1
<small> August 27, 2020 </small>
**Features**
  1. Added `Unet` with backbones: `VGG16` `VGG19` `Resnet50` `Resnet101` `Resnet152` `Mobilenet`
  2. Added `PSPnet` backbones: `Resnet50` `Resnet101` `Resnet152` `Resnet50v2` `Resnet101v2` `Resnet152v2` `VGG16` `VGG19` `Mobilenet` `Mobilenetv2`

## 0.3.0
<small>Aug 11, 2020</small>
**Features**
1. Segmentation Pipeline
1. `Deeplabv3+` for semantic segemntation
1. Log artifacts
1. Auto upload checkpoints
1. Upload `model.summary()` as artifact

**Bug Fixes**
1. Train `Yolov3` correctly on custom dataset
## 0.2.2 
<small>Aug 4, 2020</small>
**Features**
1. Added object detection network: Yolo V3
1. Added coco metrics API for object detection

**Bug fixes**
1. Fixed artifacts logging.

## 0.2.1
<small>July 27, 2020</small>
**Features**
1. `DenseNet` (121, 169, 201) & `DetNet` added as backbones for RetinaNet
1. Support for RGBA data (ignore alpha channel)
1. Now logging GPU Metrics & parameters.
1. Multi GPU support for training

**Bug fixes**
1. [OD] Added negative images (images without annotations) to training.


## 0.2.0
<small>July 17, 2020</small>
**Features**
1. Added 11 classification networks
1. Added OD network RetinaNet with 3 backbones (Resnet 50, 101, 152)
1. Added Pipeline - Classification and Object Detection




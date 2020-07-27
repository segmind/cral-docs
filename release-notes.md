---
title: Release Notes
description: Version update notes for CRAL
published: true
date: 2020-07-27T08:32:08.855Z
tags: 
editor: markdown
---

# Release Notes

## 0.2.0
<small>July 17, 2020</small>
**Features**
1. Added 11 classification networks
1. Added OD network RetinaNet with 3 backbones (Resnet 50, 101, 152)
1. Added Pipeline - Classification and Object Detection

## 0.2.1
<small>July 27, 2020</small>
**Features**
1. DenseNet (121, 169, 201) & DetNet added as backbones for RetinaNet
1. Support for RGBA data (ignore alpha channel)
1. Now logging GPU Metrics & parameters.
1. Multi GPU support for training

**Bug fixes**
1. [OD] Added negative images (images without annotations) to training.

## 0.2.2 (planned)
**Features**
1. Add object detection network: Yolo V3
1. Add coco metrics API for object detection

**Bug fixes**
1. Fix artifacts logging.


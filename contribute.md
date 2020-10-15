---
title: Contribute
description: How to contribute to CRAL
published: true
date: 2020-10-15T11:28:38.610Z
tags: 
editor: markdown
dateCreated: 2020-08-10T20:33:00.375Z
---

# Contributing to CRAL

## Roadmap
Coming soon

## **General Guidelines**

1. All Implimentations on Keras (tf.keras); TensorFlow version > 2.2.0
1. Use [Flake8](https://pypi.org/project/flake8/) for Linter and [isort](https://pypi.org/project/isort/) to sort imports. Configs here [links to configs]. Link to *pre-commit config* here.
1. Python 3.6+ 

## Guides

- [Contributing a new object detection network to CRAL](/contribute/object-detection)
- [Contributing a new segmentation network to CRAL](/contribute/segmentation)
{.links-list}

## Architecture

| API | Methods | 
|---|---|
|**cral.models** <br /><small>Training ready models</small>|[`cral.models.object_detection`](/api/models/ObjectDetection) [`cral.models.semantic_segmentation`](/api/models/segmentation) [`cral.models.classification`](/api/models/classification) `cral.models.instance_segmentation` |
|**cral.data** <br /><small>Data ingesion and conversion tools </small>| | 
|**cral.metrics**|`cral.object_detection.coco_iou` `cral.seg.sparse_mean_iou`|
|**cral.post_processing**|`cral.post_processing.object_detection.soft_nms` `cral.post_processing.display.object_detection`|
|**cral.pipeline**||

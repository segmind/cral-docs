---
title: CNN Research Abstraction Library
description: Build better computer vision models faster with less code.
published: true
date: 2020-07-21T06:08:34.132Z
tags: 
editor: undefined
---

CRAL is a deep learning computer vision library for data scientists, researchers, and developers. With main focus on applied deep learning, CRAL library encourages rapid development and comes with ready-to-use state-of-the-art networks and other pragmatic tools for a variety of applications in the computer vision space.

Our aim is also to make the results of various DLCV algorithms developed in academia and industrial labs easier to reproduce and extend.

## Guiding Principles

**Simple:** To make it easy for deep learning engineers & students alike to use neural networks to build computer vision applications of their choice, using low code approach.

**Fast:** To go from experimentation to a working model, faster.

**Reproducible:** Implementations that can easily be trained and reproduced on your own data.

## Components
| Components | Methods | Description |
|---|---|---|
| Tracking | [`Metrics`]() [`Parameters`]() [`Artifacts`]() [`Training Data`](/api/data-versioning) | Log and query your experiments. |
| CNN Models | [`Classification`](api/models/classification) [`Object Detection`](/api/models/ObjectDetection) [`Semantic Segmentation`]() | Ready to use implimentations of SOTA algorithms. |
| Pipeline tools | [`Data Ingesion`]() [`Data Validation`]() | Load and validate your data before you start training. |

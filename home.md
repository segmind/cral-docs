---
title: CNN Research Abstraction Library
description: Build better computer vision models faster with less code.
published: true
date: 2020-07-25T18:40:43.127Z
tags: 
editor: markdown
---

The CNN Research Abstraction Library (CRAL) is a deep learning computer vision library for data scientists, researchers, and developers. With a primary focus on applied deep learning, the CRAL library encourages rapid development and comes with ready-to-use state-of-the-art networks and other pragmatic tools for a variety of applications in the computer vision space.

Our aim is also to make it easier to reproduce and extend the results of various Deep Learning-powered Computer Vision (DLCV) algorithms developed in academia and industrial labs.

## Guiding Principles

**Simple:** To make it easy for deep learning engineers & students alike to use neural networks to build computer vision applications of their choice, using low code approach.

**Fast:** To accelerate going from experimentation to a working model.

**Reproducible:** To offer implementations that can easily be trained and reproduced on your own data.

## Components
| Components | Methods | Description |
|---|---|---|
| Tracking | [`Metrics`]() [`Parameters`]() [`Artifacts`]() [`Training Data`](/api/data-versioning) | Log and query your experiments. |
| CNN models | [`Classification`](api/models/classification) [`Object Detection`](/api/models/ObjectDetection) [`Semantic Segmentation`]() | Ready to use implementations of SOTA algorithms. |
| Pipeline tools | [`Data Ingestion`]() [`Data Validation`]() | Load and validate your data before you start training. |

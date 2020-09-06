---
title: Contributing a new object detection network
description: guide to contribute a new model for object detection
published: true
date: 2020-09-06T19:53:42.969Z
tags: 
editor: markdown
---

# Contributing a new object detection network

## 0. Required prediction model structure
The prediction model should have 3 outputs tensors as follows:
    1. `bboxes(int32)` : shape should be (N,4) where each row has bbox format (x1,y1,x2,y2). NB: If an algorithm resizes an input image having original dimension 640x480 into an array of 300x300 for prediction, make sure that the bboxes are scaled up so that the coordinates are relative to the original dimension of 640x480 
    2. `scores(float32)` : shape should be (N,)
    3. `labels(int32)` : shape should be (N,)


Input images should be of format 3-channel RGB.

## 1. Deliverables

create a new branch from branch `cral-dev`.

Suppose you want to integrate a new network called `DetectorPro` into cral. You need to make a new module called **Model** under **cral.object_detection** and prepare the endpoints below.

### 1.1 DetectorProGenerator:
A generator based on tf.data api which takes in a ModelConfig Object and tfrecord paths, to creates groundtruths from them.

tfrecords are basically the serialized images and their annotation in protocol buffer format.
Google highly recommends to use tfrecords along with tf.data api for best performance.

the parser should be able to parse an example having the following fields:
```
feature={
    'image/height': tf.train.Feature(int64_list=tf.train.Int64List(value=[height])),
    'image/width': tf.train.Feature(int64_list=tf.train.Int64List(value=[width])),
    'image/encoded': tf.train.Feature(bytes_list=tf.train.BytesList(value=[image_string])),
    'image/object/bbox/xmin': tf.train.Feature(float_list=tf.train.FloatList(value=xmins)),
    'image/object/bbox/xmax': tf.train.Feature(float_list=tf.train.FloatList(value=xmaxs)),
    'image/object/bbox/ymin': tf.train.Feature(float_list=tf.train.FloatList(value=ymins)),
    'image/object/bbox/ymax': tf.train.Feature(float_list=tf.train.FloatList(value=ymaxs)),
    'image/f_id': tf.train.Feature(int64_list=tf.train.Int64List(value=[image_id])),
    'image/object/class/label': tf.train.Feature(int64_list=tf.train.Int64List(value=labels)),
}
```

### 1.2 DetectorProConfig
A template class which stores all model hyper parameters specific to algorithm `DetectorPro`

### 1.3 DetectorPro_loss:
 the default loss function

### 1.4 log_model_config_params: 
a function which takes in an object of ModelConfig and logs it to track

### 1.5 create_training_model:
a function which takes in a tf.keras.Model object of a backbone and an object of ModelConfig and creates the training model

### 1.6 create_inference_model:
a function that takes in a tf.keras.Model object of the training model and converts into prediction model
### 1.7 test checkpoint:
A checkpoint trained on a **chess-dataset**, this will be used later in unittest.

So after the above have been done we should be able to do:

```
from cral.object_detection.DetectorPro import ModelGenerator, ModelConfig, DetectorPro_loss
from cral.object_detection.DetectorPro import log_model_config_params, create_training_model 
from cral.object_detection.DetectorPro import create_inference_model
```

## 2. Pipeline Usage Layout blueprint

Note down the final endpoints in an **ipynb notebook** as to how will it be used on **ObjectDetection_pipeline**, right from `add_data` method to inference part which includes annotating images with predicted bboxes like [RetinaNet](https://colab.research.google.com/github/segmind/cral-notebooks/blob/master/OD_tutorial.ipynb)

## 3. Integration

After all the deliverables in **section-1** have been made, use them for integrating the new network into the pipeline.

NB: all the metadata of pipeline, including **DetectorProConfig** are stored into an asset file along with model weights and model structure in the checkpoint file 

## 4. Unit testing

Write testcases for the network which should do the following

- load `tf.keras.Model` instance of `DetectorPro`
- load weights into it via `model.load_weights()`, from the checkpoint file submitted as a deliverable in **section-1**
- convert the model into prediction model(if required) into the **required prediction model structure as specified in section-0**.
- predict on a set of test images from **chess-dataset** for which bboxes have already been calculated.


After unittest have passed, merge requests should be raised, for mergeing the code into cral-dev. The ipynb notebook submitted in section 2 will be run, if it works end to end then the merge request will be accepted.
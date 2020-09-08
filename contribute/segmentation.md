---
title: Contributing a new segmentation network to CRAL
description: Guide to contribute a new model for segmentation
published: true
date: 2020-09-08T03:56:43.489Z
tags: 
editor: markdown
---

# Contributing a new Segmentation network
## 0. Required prediction model structure
The prediction model should have 1 output tensor as follows:
    1. `y(float32)` : shape should be (N, H, W, num_classes) where N is the batch size, H and W are the input dimensions and num_classes is the number of different segmentation classes in the dataset. 
Input images should be of format 3-channel RGB.
## 1. Deliverables
create a new branch from branch `cral-dev`.
Suppose you want to integrate a new network called `SegmentorPro` into cral. You need to make a new module called **SegmentorPro** under **cral.models.semantic_segmentation** and prepare the endpoints below.
### 1.1 SegmentorProGenerator:
A generator based on tf.data api which takes in a ModelConfig Object and tfrecord paths, to creates groundtruths from them.
tfrecords are basically the serialized images and their annotation in protocol buffer format.
Google highly recommends to use tfrecords along with tf.data api for best performance.
the parser should be able to parse an example having the following fields:
```
feature={
    'image/height': tf.train.Feature(int64_list=tf.train.Int64List(value=[height])),
    'image/width': tf.train.Feature(int64_list=tf.train.Int64List(value=[width])),
    'image/depth': tf.train.Feature(int64_list=tf.train.Int64List(value=[depth])),
    'image_raw': tf.train.Feature(float_list=tf.train.FloatList(value=[image_raw])),
    'mask/height': tf.train.Feature(int64_list=tf.train.Int64List(value=[height])),
    'mask/width': tf.train.Feature(int64_list=tf.train.Int64List(value=[width])),
    'mask/depth': tf.train.Feature(int64_list=tf.train.Int64List(value=[depth])),
    'mask_raw': tf.train.Feature(float_list=tf.train.FloatList(value=[mask_raw])),
}
```
### 1.2 SegmentorProConfig
A template class which stores all model hyper parameters specific to algorithm `SegmentorPro`
### 1.3 SegmentorPro_loss:
 the default loss function
### 1.4 log_model_config_params: 
a function which takes in an object of ModelConfig and logs it to track
### 1.5 create_training_model:
```
def training_model_vgg16(config, weights):
		from cral.common import classification_networks    
    base_model, preprocessing_function = classification_networks['vgg16']
    #construct rest of the model using base_model and config
def create_training_model(backbone, config, weights='imagenet):
	assert isisntance(config, SegmentorProconfig)
	if backbone == 'vgg16':
     return training_model_vgg16(config, weights)
	elif backbone == 'resnet50':
     return training_model_resnet50(config, weights)
```
a function which takes in 3 arguments i.e `backbone, config and weights` and creates the training model.
for each backbone supported by `SegmentorPro`, there should be a function which builds tf.keras.Model of SegmentorPro from the tf.keras.Model of the given backbone. PLease look at the example of function `training_model_vgg16`.
NB: All backbone networks should be built from the dictionary `classification_networks` imported from `cral.common`
### 1.6 create_inference_model:
a function that takes in a tf.keras.Model object of the training model and converts into prediction model
### 1.7 test checkpoint:
A checkpoint trained on a **semantic-drone-dataset**, this will be used later in unittest.

So after the above have been done we should be able to do:
```
from cral.models.semantic_segmentation.SegmentorPro import SegmentorProGenerator, SegmentorProConfig, SegmentorPro_loss
from cral.models.semantic_segmentation.SegmentorPro import log_model_config_params, create_training_model 
from cral.models.semantic_segmentation.SegmentorPro import create_inference_model
```
## 2. Pipeline Usage Layout blueprint
Note down the final endpoints in an **ipynb notebook** as to how will it be used on **Segmentation_pipeline**, right from `add_data` method to inference part which includes overlaying segmented mask on original image like [UNet](https://colab.research.google.com/github/segmind/cral-notebooks/blob/master/OD_tutorial.ipynb)
## 3. Integration
After all the deliverables in **section-1** have been made, use them for integrating the new network into the pipeline.
NB: all the metadata of pipeline, including **SegmentorProConfig** are stored into an asset file along with model weights and model structure in the checkpoint file 
## 4. Unit testing
Write testcases for the network which should do the following
- load `tf.keras.Model` instance of `SegmentorPro`
- load weights into it via `model.load_weights()`, from the checkpoint file submitted as a deliverable in **section-1**
- convert the model into prediction model(if required) into the **required prediction model structure as specified in section-0**.
- predict on a set of test images from **semantic-drone-dataset** for which bboxes have already been calculated.
After unittest have passed, merge requests should be raised, for mergeing the code into cral-dev. The ipynb notebook submitted in section 2 will be run, if it works end to end then the merge request will be accepted.
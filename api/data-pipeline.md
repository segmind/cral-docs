---
title: Pipeline
description: 
published: true
date: 2020-06-18T05:01:05.720Z
tags: 
editor: markdown
---

# ClassificationPipe 
Cral pipeline for classification task


## Add Data
Parses dataset once for generating metadata and versions the data

```py
from cral.pipeline import ClassificationPipe
pipeline=ClassificationPipe()
pipeline.add_data(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**train_images_dir**| str |.|path to images|
|**val_images_dir**| str|.| (*optional*) path to validation images
|**split**| float|0.2| (*optional*) float to divide training dataset into training and validation

---

## Lock Data
Parse Data and makes tf-records and creates meta-data

```py
pipeline.lock_data(gen_stats=False)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**gen_stats**| bool| False|(*optional*) If True uses tfdv to create stats graph

---

## Set Augmentation
Sets the augmentation pipeline
```py
pipeline.set_aug(aug)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|aug| list| -| List of Image Augmentations from Albumentations|
## Set Algo
Set model for training and prediction

```py
pipeline.set_algo(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|model| str,Keras Model|.| Can be a model name as Str or can be a keras model|
|weights|string|`imagenet`|one of `None` ,`imagenet`,or the path to the weights file
|fully_connected_layer| list, tuple| . | A list or tuple indicating number of neurons per hidden layer
|dropout_rate| list, tuple|.|A list or tuple indicating the dropout rate per hidden layer|
|hidden_layer_activation| list, tuple|`relu`|A list or tuple indicating the activation function per hidden layer|
|final_layer_activation| str|`softmax`| (*optional*) str indicating the activation function of the final prediction layer|
|base_trainable| bool|False|(*optional*) If set False the base models layers will not be trainable useful fortransfer learning|
|preprocessing_fn| Function|None| (*optional*) needs to to be set if a in built model is not being used|

---

## Train
This function starts the training loop, with metric logging enabled

```py
pipeline.train(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|num_epochs int |int|.| number of epochs to run training on|
|snapshot_prefix| str|.|prefix to assign to the checkpoint file
|snapshot_path| str|.|a valid folder path where the checkpoints are to be stored
|snapshot_every_n|int|.|take a snapshot at every nth epoch
|height| int |.|height of images
|width| int |.|width of images
|batch_size| int|1|(*optional*)batch size
|validation_batch_size| int|None| (*optional*) the batch size for validation loop, if None(default) then equal to batch_size argument
|validate_every_n| int|1| (*optional*) - Run validation every nth epoch
|callbacks list| list||(*optional*) - list of keras callbacks to be passed to model.fit() method
|steps_per_epoch| int|None| (*optional*) - steps size of each epoch
|compile_options|dict|None| (*optional*) - A dictionary to be passed to model.compile method

---

## Predict
Predicts output for list of images
```py
pipeline.predict(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|img_list |list|.| list of path to images for which predictions are going to be made
|return_names| bool|False| (*optional*) If True returns class-label-names else class-label-ints



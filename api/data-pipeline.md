---
title: Pipeline
description: 
published: true
date: 2020-06-23T20:04:45.783Z
tags: 
editor: markdown
---

# ClassificationPipe 
Cral pipeline for classification task


## add_data
Parses dataset once for generating metadata and versions the data.

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

## lock_data
Parse Data and makes tf-records and creates meta-data.

```py
pipeline.lock_data(gen_stats=False)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**gen_stats**| bool| False|(*optional*) If True uses tfdv to create stats graph

---

## set_aug
Sets augmentations for the pipeline
```py
pipeline.set_aug(aug)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|aug| list| -| List of Image Augmentations from Albumentations|
## set_algo
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

## train
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


## More information & examples

### Adding Custom model and preprocessing function to pipeline
Lets say you want to your own custom model and preprocessing to the pipeline 
```py
# After adding data
# Model Definationfrom tensorflow.keras import models,layers
custom_model = models.Sequential()
custom_model.add(layers.Conv2D(32, (3, 3), activation='relu', input_shape=(300, 300, 3)))
custom_model.add(layers.MaxPooling2D((2, 2)))
custom_model.add(layers.Conv2D(64, (3, 3), activation='relu'))
custom_model.add(layers.MaxPooling2D((2, 2)))
custom_model.add(layers.Conv2D(64, (3, 3), activation='relu'))
custom_model.add(layers.Flatten())
custom_model.add(layers.Dense(64, activation='relu'))
custom_model.add(layers.Dense(2, activation='softmax'))

# custom_model.compile(
# 	optimizer='adam',
#   loss=tf.keras.losses.CategoricalCrossentropy(),
#   metrics='accuracy')
  
# Preprocessing Function 
def preprocessing_func(x):
    """Normalize Input image to 0 - 1"""
    return x/255.0
  
pipeline.set_algo(model=custom_model,preprocessing_fn=preprocessing_func)

```
### Adding Custom callback to pipeline
Lets say you want to stop training when Validation Loss has stopped improving
```py
#after adding data and setting model

custom_callback=tf.keras.callbacks.EarlyStopping(monitor='val_loss')
callback_list=[custom_callback]

pipeline.train(
     num_epochs=8,
     snapshot_prefix='prefix',
     snapshot_path='/tmp',
     snapshot_every_n=4,
     batch_size=8,
     height=300,
     width=300,
     callbacks=callback_list)

```

### Adding custom Losses,Optimizer and Metrics
Lets say you want to use
Loss = CategoricalCrossentropy
Optimizer= adam
Metrics = accuracy, precision and recall
```py
#after adding data and setting model
compile_options={}
compile_options['loss'] = tf.keras.losses.CategoricalCrossentropy()
compile_options['optimizer'] = tf.keras.optimizers.Adam()
compile_options['metrics'] = [tf.keras.metrics.Accuracy(),
							 tf.keras.metrics.Precision(),
  													  tf.keras.metrics.Recall()]

pipeline.train(
     num_epochs=8,
     snapshot_prefix='prefix',
     snapshot_path='/tmp',
     snapshot_every_n=4,
     batch_size=8,
     height=300,
     width=300,
     compile_options=compile_options)

```




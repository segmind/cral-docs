---
title: Instance Segmentation Pipeline
description: 
published: true
date: 2020-11-24T07:33:02.459Z
tags: 
editor: markdown
dateCreated: 2020-11-24T07:32:33.613Z
---

# InstanceSegPipe 
Cral end to end pipeline for Instance Segmentation task


## add_data
Parses dataset once for generating metadata and versions the data.

```py
from cral.pipeline.instance_segmentation_pipeline import InstanceSegPipe
pipeline=InstanceSegPipe()
pipeline.add_data(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|---|---|---|---|
|**train_images_dir**| str |.|path to training images|
|**train_anno_dir**| str |.|path to training annotations|
|**annotation_format**|str|.|`grayscale`
|**val_images_dir**| str |.|path to validation images|
|**val_anno_dir**| str |.|path to validation annotation|
|**names_file**| str |.| (*optional*) Path to names file for YOLO format|
|**split**| float|0.2| (*optional*) float to divide training dataset into training and validation
|**img_to_anno**|function|.| (optional) Function to convert image name to annotation name

---

## lock_data
Parse Data and makes tf-records and creates meta-data.

```py
pipeline.lock_data()
```

## set_algo
Set model for training and prediction

```py
pipeline.set_algo(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|---|---|---|---|
|**feature_extractor**| str |.|Name of the backbone for instance segmentation|
|**config**| Config |.|[Config](https://cral.segmind.com/api/models/segmentation) object of the Segmentation Model|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**base_trainable**| bool|False|(*optional*) If set False the base models layers will not be trainable useful fortransfer learning|
|**preprocessing_fn**| Function|None| (*optional*) needs to to be set if a in built model is not being used|
|**optimizer**|tensorflow optimizer|Adam|The optimizer for the model|
|**distribute_strategy**||||

---

## train
This function starts the training loop, with metric logging enabled

```py
pipeline.train(*args, **kwargs)
```

**Arguments**
| Name                  | Type        | Default     | Description                            |
|---|---|---|---|
|**num_epochs**|int|.| number of epochs to run training on|
|**snapshot_prefix**| str|.|prefix to assign to the checkpoint file
|**snapshot_path**| str|.|a valid folder path where the checkpoints are to be stored
|**snapshot_every_n**|int|.|take a snapshot at every nth epoch
|**height**| int |.|height of images
|**width**| int |.|width of images
|**batch_size**| int|1|(*optional*)batch size
|**validation_batch_size**| int|None| (*optional*) the batch size for validation loop, if None(default) then equal to batch_size argument
|**validate_every_n**| int|1| (*optional*) - Run validation every nth epoch
|**callbacks**| list||(*optional*) - list of keras callbacks to be passed to model.fit() method
|**steps_per_epoch**| int|None| (*optional*) - steps size of each epoch
|**compile_options**|dict|None| (*optional*) - A dictionary to be passed to model.compile method
|**distribute_strategy**||||

---

## Predict
Predicts output for list of images
```py
pipeline.prediction_model(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|---|---|---|---|
|checkpoint_path |str|.| Path to the checkpoint where the trained model is stored


## More information & examples
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
compile_options['metrics'] = [ tf.keras.metrics.Accuracy() ,
                               tf.keras.metrics.Precision() ,
                               tf.keras.metrics.Recall() ]

pipeline.train(
     num_epochs=8,
     snapshot_prefix='prefix',
     snapshot_path='/tmp',
     snapshot_every_n=4,
     batch_size=8,
     compile_options=compile_options)

```




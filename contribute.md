---
title: Contribute
description: How to contribute to CRAL
published: true
date: 2020-08-25T08:58:03.976Z
tags: 
editor: markdown
---

# Contributing to CRAL

You can contribute to CRAL under the following categories:

| | |
|---|---|
| Add a new algo | `Classification` `Object Detection` `Semantic Segmentation` `Instance Segmentation` `Panoptic Segmentation` `Pre-processing` `Post-processing` |
| Add/Update features | `Pipeline tools` `Data validation` `Data conversion` `Data ingesion` `Data versioning` | 
| Bug fixes & other updates | `Bugs` `Performance updates` `Typos` `Documentation updates`|

## Basic Requirements
- Linux
- Python 3.6+
- TensorFlow 2.2+

## Roadmap
Refer to this following link

- [Networks/Algos](https://docs.google.com/spreadsheets/d/e/2PACX-1vRaLketbBCL-9KrqSvEWYt96r3UC-Oof9Negm2oupUveaG1LdP0y-xxn6gemYUW-U_M7i-4M9NA_st8/pubhtml)
- [Current Pipeline/Trello](https://trello.com/b/YbizwO0D/segmind)
{.links-list}

## Contribution checklist
### Coding style
Coming soon

### Add a new algo
### Classification
1. Find a Keras (tf.keras 2.2.0 ) implementation of the network.
2. Quick test on some dataset(less epochs)
3. Port the generator, so that it uses tf.data api which consumes tfrecords to create y_true which is fed to the loss function 
4. Add it to cral.models.classification module
5. Add the keras definition in a .py file and put it cral→models→classification
6. Add alias of it int cral→models→__init__.py
7. Check that the implementation is working properly
8. Add to classification pipe

### Segmentation
- To add any new semantic segmentation architecture (example deeplabv3):
1. Create a folder with the name as deeplabv3 inside cral -> models -> semantic segmentation.
2. Add tfrecord_parser.py inside this folder which is the same for all the other semantic segmentation models.
3. Add utils.py which will contain the Upsample class, the model config class, log_config_params class and the predictor class. These all classes will be similar to the earlier added models. Only minor changes would be there according to the network being added. 
4. Also a file which will have the model definition would be added which will have a function that will return the model architecture. 
5. Add the aliases of the classes and functions in __init__.py inside cral -> models -> semantic segmentation -> deeplabv3 folder.
6. Call the newly created model from the set_algo function in cral -> pipeline -> semantic_segmentation_pipeline.py whenever the config of that particular model is called. 
7. Also for adding the prediction part, add the architecture call inside the prediction_model function inside the semantic_segmentation_pipeline.py file. 
- To add a backbone to the network:
1. Find a Keras (tf.keras) implementation of the deeplab backbone that works. 
2. Quick test on some dataset.
3. Put the model definition file in cral -> models -> semantic segmentation -> deeplabv3. 
4. Call the model from create_DeepLabv3Plus function in the deeplab.py file  inside the above mentioned folder. 
5. Check that the implementation is working properly by providing the added feature_extractor as the argument while calling the set_algo function in the semantic segmentation pipeline.

### Object Detection
1. Create a new folder with the name of the architecture
2. Place all the model specific classes and functions in a file called base.py
3. Place all utility functions in utils.py
4. In utils.py create a class called <arch_name>Config, initialise all the architecture specific hyperparameters in it.
5. Place the generator in a file called tfrecord_parser.py
6. Create the model with the required parameters in the set_algo function of the object detection pipeline.
7. Write the prediction logic of the model in prediction_model. It should return a function which accepts image path and returns the boxes, scores and labels, in that order.


- Training time benchmark
- Accuracy benchmark
> Network implimentations should be in tf.keras
{.is-info}

### Add tools

### Bug fixes

### Performance updates


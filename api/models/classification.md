---
title: Classification models
description: List of all the image classification models
published: true
date: 2020-07-24T06:22:48.905Z
tags: 
editor: markdown
---

## DenseNet (121, 169, 201)
Instantiates the DenseNet architecture.
```py
cral.models.classification.DenseNet121(*args, **kwargs)
cral.models.classification.DenseNet169(*args, **kwargs)
cral.models.classification.DenseNet201(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|

---

## InceptionResNetV2
Instantiates the InceptionResNetV2 architecture.

```py
cral.models.classification.InceptionResNetV2(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|

---

## InceptionV3
Instantiates the InceptionV3 architecture.

```py
cral.models.classification.InceptionV3(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|

---

## MobileNet
Instantiates the MobileNet architecture.
```py
cral.models.classification.MobileNet(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**alpha**| float|1.0|Controls the width of the network|
|**depth_multiplier**|float|1|Depth multiplier for depthwise convolution|
|**dropout**| float|0.001|Dropout rate|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|

---

## MobileNetV2
Instantiates the MobileNetV2 architecture.
```py
cral.models.classification.MobileNetV2(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**alpha**| alpha_type|1.0|Controls the width of the network|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|

---

## NASNET (Large, Mobile)
Instantiates the NASNET architecture.
```py
cral.models.classification.NASNetLarge(*args, **kwargs)
cral.models.classification.NASNetMobile(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|

---

## ResNet (50, 101, 152)
Instantiates the ResNet architecture.
```py
cral.models.classification.ResNet50(*args, **kwargs)
cral.models.classification.ResNet101(*args, **kwargs)
cral.models.classification.ResNet152(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**| string|`imagenet`| one of `None`,`imagenet` or the path to weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|

---

## ResNetV2 (50, 101, 152)
Instantiates the ResNetV2 architecture.
```py
cral.models.classification.ResNet50V2(*args, **kwargs)
cral.models.classification.ResNet101V2(*args, **kwargs)
cral.models.classification.ResNet152V2(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|

---

## VGG (16, 19)
Instantiates the VGG architecture.
```py
cral.models.classification.VGG16(*args, **kwargs)
cral.models.classification.VGG19(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|

---

## Xception
Instantiates the Xception architecture.
```py
cral.models.classification.Xception(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|

---

## EfficientNet (B0-B7)
Instantiates the EfficientNet architecture.
```py
cral.models.classification.EfficientNetB0(*args, **kwargs)
cral.models.classification.EfficientNetB1(*args, **kwargs)
cral.models.classification.EfficientNetB2(*args, **kwargs)
cral.models.classification.EfficientNetB3(*args, **kwargs)
cral.models.classification.EfficientNetB4(*args, **kwargs)
cral.models.classification.EfficientNetB5(*args, **kwargs)
cral.models.classification.EfficientNetB6(*args, **kwargs)
cral.models.classification.EfficientNetB7(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|

---
## DarkNet53
Instantiates the DarkNet53 architecture.
```py
cral.models.classification.DarkNet53(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(416, 416, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|


---

## Detnet
Instantiates the Detnet architecture.
```py
cral.models.classification.Detnet(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| :---: | :----: | :---: | :---: |
|**include_top**|bool|False|Flag for fully-connected prediction layer at the top of the network|
|**weights**|string|`imagenet`|One of `None`,`imagenet` or the path to the weights file|
|**input_tensor**|Tensor|None|(*optional*) Keras tensor to use as image input for the model|
|**input_shape**|tuple|None|(*optional*) Shape tuple E.g. `(224, 224, 3)` would be valid|
|**pooling**|string|None|One of `None` ,`avg` or `max`|
|**classes**|int|1000|(*optional*) number of classes to classify images into|
|**classifier_activation**|string or callable|`softmax`|The activation function to use on the "top" layer|


## Model source
| Model | Source |
| -- | -- |
| `DenseNet` `InceptionResNetV2` `InceptionV3` `MobileNet` `MobileNetV2` `NASNET` `ResNet` `ResNetV2` `VGG` `Xception` `EfficientNet`| [Keras Applications](https://keras.io/api/applications/) | 
|`DarkNet53` |  [Github](https://github.com/qqwweee/keras-yolo3) |
|`Detnet` |  [Github](https://github.com/becauseofAI/DetNet-Keras/blob/master/detnet59.py) |



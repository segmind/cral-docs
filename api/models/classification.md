---
title: Classification models
description: List of all the image classification models
published: true
date: 2020-06-16T16:27:37.561Z
tags: 
editor: markdown
---

# Header
## DenseNet (121, 169, 201)
Instantiates the DenseNet architecture.
```py
cral.models.classification.DenseNet121()
cral.models.classification.DenseNet169()
cral.models.classification.DenseNet201()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |

---

## InceptionResNetV2
Instantiates the InceptionResNetV2 architecture.
```py
cral.models.classification.InceptionResNetV2()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |
|**classifier_activation**| string or callable|'softmax'|  The activation function to use on the "top" layer|

---

## InceptionV3
Instantiates the InceptionV3 architecture.

```py
cral.models.classification.InceptionV3()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |
|**classifier_activation**| string or callable|'softmax'|  The activation function to use on the "top" layer|

---

## MobileNet
Instantiates the MobileNet architecture.
```py
cral.models.classification.MobileNet()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |
|**alpha**| float|1.0|  Controls the width of the network |
|**depth_multiplier**| float|1| Depth multiplier for depthwise convolution |
|**dropout**| float|0.001| Dropout rate  |
|**classifier_activation**| string or callable|'softmax'|  The activation function to use on the "top" layer|

---

## MobileNetV2
Instantiates the MobileNetV2 architecture.
```py
cral.models.classification.MobileNetV2()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |
|**alpha**| alpha_type|1.0| Controls the width of the network |
|**classifier_activation**| string or callable|'softmax'|  The activation function to use on the "top" layer|

---
## NASNET (Large, Mobile)
Instantiates the NASNET architecture.
```py
cral.models.classification.NASNetLarge()
cral.models.classification.NASNetMobile()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |

---
## ResNet (50, 101, 152)
Instantiates the ResNet architecture.
```py
cral.models.classification.ResNet50()
cral.models.classification.ResNet101()
cral.models.classification.ResNet152()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |

---
## ResNetV2 (50, 101, 152)
Instantiates the ResNetV2 architecture.
```py
cral.models.classification.ResNet50V2()
cral.models.classification.ResNet101V2()
cral.models.classification.ResNet152V2()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |
|**classifier_activation**| string or callable|'softmax'|  The activation function to use on the "top" layer|

---
## VGG (16, 19)
Instantiates the VGG architecture.
```py
cral.models.classification.VGG16()
cral.models.classification.VGG19()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |
|**classifier_activation**| string or callable|'softmax'|  The activation function to use on the "top" layer|

---
## Xception
Instantiates the InceptionV3 architecture.
Xception
```py
cral.models.classification.Xception()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| bool |True| flag for fully-connected layer at the top of the network |
|**weights**| string|'imagenet'| one of `None`,`imagenet`,or the path to the weights file|
|**input_tensor**| Tensor|.| (*optional*) Keras tensor to use as image input for the model. |
|**input_shape**| tuple|.|(*optional*) shape tuple E.g. `(224, 224, 3)` would be one valid value.  |
|**pooling**| string|.| One of `None` ,`avg` or `max`  |
|**classes**| int |1000| (*optional*) number of classes to classify images into |
|**classifier_activation**| string or callable|'softmax'|  The activation function to use on the "top" layer|

---
## EfficientNet (b0,b1,b2,b3,b4,b5,b6,b7)
Instantiates the EfficientNet architecture.
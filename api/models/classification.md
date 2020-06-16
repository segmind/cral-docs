---
title: Classification models
description: List of all the image classification models
published: true
date: 2020-06-16T16:07:05.758Z
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
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**input_shape**| input_shape_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |

---

## InceptionResNetV2
Instantiates the InceptionResNetV2 architecture.
```py
cral.models.classification.InceptionResNetV2()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**input_shape**| input_shape_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |
|**classifier_activation**| classifier_activation_type|softmax|  |

---

## InceptionV3
Instantiates the InceptionV3 architecture.

```py
cral.models.classification.InceptionV3()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**input_shape**| input_shape_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |
|**classifier_activation**| classifier_activation_type|softmax|  |

---

## MobileNet
Instantiates the MobileNet architecture.
```py
cral.models.classification.MobileNet()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**input_shape**| input_shape_type|None|  |
|**alpha**| alpha_type|1.0|  |
|**depth_multiplier**| depth_multiplier_type|1|  |
|**dropout**| dropout_type|0.001|  |
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |
|**classifier_activation**| classifier_activation_type|softmax|  |

---

## MobileNetV2
Instantiates the MobileNetV2 architecture.
```py
cral.models.classification.MobileNetV2()
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
|**input_shape**| input_shape_type|None|  |
|**alpha**| alpha_type|1.0|  |
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |
|**classifier_activation**| classifier_activation_type|softmax|  |

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
|**input_shape**| input_shape_type|None|  |
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |

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
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**input_shape**| input_shape_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |

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
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**input_shape**| input_shape_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |
|**classifier_activation**| classifier_activation_type|softmax|  |

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
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**input_shape**| input_shape_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |
|**classifier_activation**| classifier_activation_type|softmax|  |

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
|**include_top**| include_top_type|True|  |
|**weights**| weights_type|imagenet|  |
|**input_tensor**| input_tensor_type|None|  |
|**input_shape**| input_shape_type|None|  |
|**pooling**| pooling_type|None|  |
|**classes**| classes_type|1000|  |
|**classifier_activation**| classifier_activation_type|softmax|  |

---
## EfficientNet (b0,b1,b2,b3,b4,b5,b6,b7)
Instantiates the EfficientNet architecture.
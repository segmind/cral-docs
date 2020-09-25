---
title: Segmentation Models
description: List of Networks for Segmentation
published: true
date: 2020-09-19T04:01:10.207Z
tags: 
editor: markdown
---

# [Deeplabv3+](https://arxiv.org/pdf/1802.02611.pdf)
Instantiates the Deeplabv3+ architecture. 

| Backbones supported | `Xception` `Resnet50` `Mobilenetv2` |
| -- | --| 

```py
cral.models.semantic_segmentation.Deeplabv3Config(
    height, 
    width, 
    output_stride)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|576|Input shape dimension|
|**width**|int|576|Input shape dimension|
|**output_stride**|int|8|Ratio of the input image size to the output feature map size|


---

# [UNet](https://arxiv.org/pdf/1505.04597.pdf)
Instantiates the UNet architecture. 

| Backbones supported | `VGG16` `VGG19` `Resnet50` `Resnet101` `Resnet152` `Mobilenet` |
| -- | --| 

```py
cral.models.semantic_segmentation.UNetConfig(
    height, 
    width)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|576|Input shape dimension|
|**width**|int|576|Input shape dimension|

---

# [PspNet](https://arxiv.org/pdf/1612.01105.pdf)
Instantiates the PspNet architecture. 

| Backbones supported | `VGG16` `VGG19` `Resnet50` `Resnet101` `Resnet152` `Resnet50v2` `Resnet101v2` `Resnet152v2` `Mobilenet` `Mobilenetv2`|
| -- | --| 

```py
cral.models.semantic_segmentation.PspNetConfig(
    height, 
    width, 
    down_sample_factor)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|576|Input shape dimension|
|**width**|int|576|Input shape dimension|
|**down_sample_factor**|int|8|Ratio of the input image size to the smallest feature map size generated|


---

# [SegNet](https://arxiv.org/pdf/1511.00561.pdf)
Instantiates the SegNet architecture. 

| Backbones supported | `VGG16` `VGG19` `Resnet50` `Resnet101` `Resnet152` `Resnet50v2` `Resnet101v2` `Resnet152v2` `Mobilenet` `Mobilenetv2`|
| -- | --| 

```py
cral.models.semantic_segmentation.SegNetConfig(
    height, 
    width, 
    num_upsample_layers)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|576|Input shape dimension|
|**width**|int|576|Input shape dimension|
|**num_upsample_layers**|int|3|Number of upsample layers after the encoder part|


---

# [Unet++](https://arxiv.org/abs/1807.10165)
Instantiates the Unet++ architecture. 

| Backbones supported | `VGG16` `VGG19` `Resnet50` `Resnet101` `Resnet152` `Resnet50v2` `Resnet101v2` `Resnet152v2` `Mobilenet` `Mobilenetv2`|
| -- | --| 

```py
cral.models.semantic_segmentation.UnetPlusPlusConfig(
    height, 
    width, 
    num_upsample_layers, 
    filters, 
    deep_supervision)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|320|Input shape dimension|
|**width**|int|320|Input shape dimension|
|**num_upsample_layers**|int|3|Number of upsample layers after the encoder part|
|**filters**|list|[64,128,256,512,1024]|List of filters to use. Each filter size correspond to 1 upsample layer|
|**deep_supervision**|bool|True|True for averaging the outputs otherwise false|


---

# [FpnNet](https://openaccess.thecvf.com/content_cvpr_2018_workshops/papers/w4/Seferbekov_Feature_Pyramid_Network_CVPR_2018_paper.pdf)
Instantiates the FpnNet architecture. 

| Backbones supported | `VGG16` `VGG19` `Resnet50` `Resnet101` `Resnet152` `Resnet50v2` `Resnet101v2` `Resnet152v2` `Mobilenet` `Mobilenetv2`|
| -- | --| 

```py
cral.models.semantic_segmentation.FpnNetConfig(
    height, 
    width)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
| --- | --- | --- | --- |
|**height**|int|320|Input shape dimension|
|**width**|int|320|Input shape dimension|


---


## Model source
| Model | Source |
|---|---|
|`Deeplabv3+` |  [Github](https://github.com/bonlime/keras-deeplab-v3-plus) |
|`UNet` |  [Github](https://github.com/divamgupta/image-segmentation-keras) |
|`PspNet` |  [Github](https://github.com/divamgupta/image-segmentation-keras) |
|`SegNet` |  [Github](https://github.com/divamgupta/image-segmentation-keras) |
|`UnetPlusPlus` |  [Github](https://github.com/CarryHJR/Nested-UNet) |
|`FpnNet` |  [Github](https://github.com/qubvel/segmentation_models) |




---
title: Data Versioning
description: Version controlling your datasets
published: true
date: 2020-06-17T11:07:19.954Z
tags: 
editor: markdown
---

# cral.data_versioning
Your datasets change over time during the lifecycle of an experiment and your project. New data usually keeps getting added weekly or monthly. Training data plays an important factor in reproducing your experiments and version controlling them helps you achive the same.

## log_classification_dataset 
Parses the classification data and logs the hash to tracking server


```py
cral.data_versioning.log_classification_dataset(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
| **train_images_dir** | string | . | path to training images |
|  **val_images_dir** | string | . | (*optional*) path to validation images  |
|  **split** | float | 0.2 | (*optional*) fraction to divide training dataset into training and validation sets |

---


## log_object_detection_dataset
Parses the object detection data and logs to tracking server

```py
cral.data_versioning.log_object_detection_dataset(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
| **annotation_format** | enum | coco | Options: `coco` `pascal` |
|  **train_images_dir** | string | . | (*optional*) path to training images  |
|  **train_anno_dir** | float | 1 | (*optional*) path to training annotations |
| **img_to_anno** | function | f(x) = x | (*optional*) Function to map image name to annotation name. |
| **val_images_dir** | string | . | (*optional*) path to validation images |
| **val_anno_dir** | string | . | (*optional*) path to validation annotations |
| **split** | string | 0.2 | (*optional*) fraction to divide training dataset into training and validation sets. Ignored if validation dirs are specified. |

---

## log_segmentation_dataset
Parses the segmentation data and logs the hash to tracking server

```py
cral.data_versioning.log_segmentation_dataset(*args, **kwargs)
```
**Arguments**
| Name                  | Type        | Default     | Description                            |
|-----------------------|-------------|-------------|----------------------------------------|
| **annotation_format** | enum | coco | Options: `coco` `pascal` |
|  **train_images_dir** | string | . | (*optional*) path to training images  |
|  **train_anno_dir** | float | 1 | (*optional*) path to training annotations |
| **img_to_anno** | function | f(x) = x | (*optional*) Function to map image name to annotation name. |
| **val_images_dir** | string | . | (*optional*) path to validation images |
| **val_anno_dir** | string | . | (*optional*) path to validation annotations |
| **split** | string | 0.2 | (*optional*) fraction to divide training dataset into training and validation sets. Ignored if validation dirs are specified. |

## More information & examples

### How to use image_to_anno function to map images to annotations?
Let say your Dataset is Structured like

──>Images
───>Image_1.jpg
───>Image_2.jpg
───>Image_3.jpg
...
──>Annotations
───>Annotation_1.xml
───>Annotation_2.xml
───>Annotation_3.xml
...
Then the Image to Annotation Function would be
```py
def image_to_annotation(Image_name):
	return "Annotation"+Image_name[-2:]
```
### How long does it take to run these logging tasks?
For a Dataset with 32 classes 10k images (2.18gb) it takes 25s for the whole process
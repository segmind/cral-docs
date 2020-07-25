---
title: Requirements
description: Prerequisites to install CRAL
published: true
date: 2020-07-25T18:59:19.566Z
tags: 
editor: markdown
---

CRAL is built on top of **TensorFlow 2** and uses the built-in Keras module internally. Training is a computationally intensive operation, especially in the computer vision space with giga or terabytes of training data. Hence, we strongly recommend using a powerful GPU-based system to run training jobs.

# Hardware Requirements
- 4 Core CPU
- 8GB RAM or higher
- NVIDIA® GPU card with CUDA® compute capability 3.5 or higher. 

To understand the compute capability of the GPU on your system, see: [CUDA GPUs](https://developer.nvidia.com/cuda-gpus).

# Software Requirements
CRAL is tested and supported on the following 64-bit systems:

- Python 3.5–3.8
- Ubuntu 16.04 or later
- NVIDIA® GPU driver 418.x or higher (for CUDA 10.1)
- TensorFlow 2
- opencv-python==3.4.2.17

We recommend using our [Docker image](/install/docker) with GPU support to simplify the installation process.

If you are installing directly on a Linux machine, please check for the requirements [here](https://www.tensorflow.org/install/gpu).

## Internet Access
`CRAL.tracking` needs an Internet connection to log your experiments. 


---
title: Installing CRAL
description: Get started by installing CRAL on your machine.
published: true
date: 2020-06-15T08:59:11.187Z
tags: 
editor: markdown
---

# Installing CRAL
## PyPI Distribution
```
pip3 install cral
```
## Binary Distribution
Before installation, please make sure all the [requirements]() are met.

Download the appropriate whl package from [here]() and then, run installation.
```
pip3 install /path/to/*.whl
```
## Docker

The following docker image contains all the dependencies needed for CRAL including TF 2.2 and OpenCV. Once your docker is running, install the the latest version of CRAL from PyPI.
```
# Pull & Run Docker image
sudo docker run --gpus all -it -v /local/path:/docker/path segmind/cral:tf-2.2-py3-jupyter
```

> If you need help getting started with docker, please refer this [post](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04)

> Note that Nvidia Driver and Nvidia Container Toolkit is needed on the host machine. 

To Install the Nvidia Container Toolkit to add NVIDIA® GPU support to Docker. For Ubuntu 16.04/18.04, run the following commands.
```
# Add the package repositories
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker
```
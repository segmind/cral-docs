---
title: Installing CRAL
description: Get started by installing CRAL on your machine.
published: true
date: 2020-06-14T11:25:21.867Z
tags: 
editor: markdown
---

# Installing CRAL
## Pip Distribution
## Docker

```
# Pull & Run Docker image
sudo docker run --gpus all -it -v /local/path:/docker/path segmind/cral:tf-2.2-py3-jupyter
```
> Please update the pip package inside the docker to the latest one from the [downloads page](https://docs.segmind.com/download) before using the APIs.

> If you need help getting started with docker, please refer this [post](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04)

> Note that Nvidia Driver is needed on the host machine. 

Install the Nvidia Container Toolkit to add NVIDIA® GPU support to Docker. For Ubuntu 16.04/18.04, run the following commands.

```
# Add the package repositories
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker
```
## Binary Distribution

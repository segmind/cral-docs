---
title: Docker
description: Getting started with the Docker image
published: true
date: 2020-07-15T11:23:53.604Z
tags: 
editor: undefined
---

> Before proceeding, make sure you meet the system [requirements](/test).
{.is-info}
# Using the Docker image

> If you need help installing docker, please refer this [post](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04) on Digitalocean. You can learn more about Dockers in this article: [Docker — Containerization for Data Scientists](https://medium.com/towards-artificial-intelligence/docker-container-and-data-scientist-bae208ce8268).
{.is-info}

### Auto-start Jupyter
```
sudo docker run --gpus all -it -v /home/ubuntu:/mnt/myspace -p 8888:8888 segmind/cral:tf2.2-jupyter
```

### Manually start Jupyter
You can append `bash` to the above command to enter into bash mode. This will not start the jupyter notebook.
Once you are inside the Docker environment, run the following command to start a jupyter-notebook session.
```
jupyter-notebook --port=8888 --ip=0.0.0.0 --allow-root
```

### Notebook URL
Once you run this command you will see the following message
```
The Jupyter Notebook is running at:
http://127.0.0.1:8888/?token=xxxxx
```
Open up the above link in a browser to create and run notebooks on your machine.

> Note that Nvidia Driver and Nvidia Container Toolkit are needed to add NVIDIA® GPU support to Docker.
{.is-warning}
## Installing Nvidia Container Toolkit for GPU Support
To install the Nvidia Container Toolkit for Ubuntu 16.04/18.04, run the following commands.

```
# Add the package repositories
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker
```
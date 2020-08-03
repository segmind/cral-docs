---
title: Docker
description: Installing CRAL using a Docker image
published: true
date: 2020-08-03T10:53:53.322Z
tags: 
editor: markdown
---

> Make sure you meet all the hardware and software [requirements](/install/requirements) before you proceed.
{.is-info}
# Installing CRAL using a Docker image

>For instructions on installing Docker, please see this [post](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04) on Digitalocean. You can learn more about Docker here: [Docker — Containerization for Data Scientists](https://medium.com/towards-artificial-intelligence/docker-container-and-data-scientist-bae208ce8268).
{.is-info}

The following procedure describes how to use CRAL on a docker image. Once you run the command below, docker will pull the image and start a jupyter notebook instance for you. 

### Start Docker
```
sudo docker run --gpus all -it -v /home/ubuntu:/mnt/myspace -p 8888:8888 segmind/cral:tf2.2-jupyter
```

**Notebook URL:** Once the docker starts, you will see the notebook URL along with the token on the terminal as shown below. Copy/paste the link in a browser to create and run notebooks on your machine.

```
The Jupyter Notebook is running at:
http://127.0.0.1:8888/?token=xxxxx
```


#### Manually start Jupyter
If you open the docker in bash mode (adding `bash` to the `docker run` will run a docker in bash mode), you'll need to manually start Jupyter. Once you are inside the Docker environment, run the following command to start a jupyter-notebook session.
```
jupyter-notebook --port=8888 --ip=0.0.0.0 --allow-root
```


> Note that the NVIDIA Driver and NVIDIA Container Toolkit are needed to add NVIDIA® GPU support to Docker.
{.is-warning}



## Installing NVIDIA Container Toolkit for GPU Support
To install the NVIDIA Container Toolkit for Ubuntu 16.04/18.04, run the following commands.

```
# Add the package repositories
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker
```
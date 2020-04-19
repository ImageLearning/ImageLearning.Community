---
layout: default
title: Container Install
nav_order: 1
parent: Installing Tensorflow
grand_parent: Tensorflow & Keras
has_children: false
---

# Running in a Container

**Running in a container is the fastest way to get going with Tensorflow**

## Linux

[https://hub.docker.com/r/nvidia/cuda/](https://hub.docker.com/r/nvidia/cuda/)
On Linux using [Nvidia Docker](https://github.com/NVIDIA/nvidia-docker) you can virtualize the GPU

[https://gitlab.com/nvidia/container-images/cuda](https://gitlab.com/nvidia/container-images/cuda)

Nvidia's Container work is spread across GitLab, and GitHub:
- https://gitlab.com/nvidia
- https://github.com/NVIDIA/

## Windows

[https://hub.docker.com/_/microsoft-windows](https://hub.docker.com/_/microsoft-windows)

On Windows the GPU [Can be Virtualized, However 3rd party frameworks like CUDA cannot today](https://docs.microsoft.com/en-us/virtualization/windowscontainers/deploy-containers/gpu-acceleration). It appears microsoft is working activly in this space.


[Docker Install Instructions](https://github.com/MicrosoftDocs/Virtualization-Documentation/tree/master/windows-container-samples/directx)

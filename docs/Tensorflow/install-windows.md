---
layout: default
title: Windows Install
nav_order: 2
parent: Installing Tensorflow
grand_parent: Tensorflow Home
has_children: false
---

# Instructions

We will be installing Tensorflow 2, with GPU support (Nvidia GPU's w/ CUDA) on windows. Today, since the [Container option](install-container.md) does not support the CUDA features we need, we will not use that. When that does, that will be the reccommend path.


## Tensorflow 2.1 Install

[2.1 Tensorflow Release Notes](https://github.com/tensorflow/tensorflow/releases/tag/v2.1.0)

[Source Zip](https://github.com/tensorflow/tensorflow/archive/v2.1.0.zip)

The tensorflow pip package is built with CUDA 10.1 and cuDNN 7.6.

### Windows

- [Visual C++ Redist](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads)
- [Cuda Toolkit](https://developer.nvidia.com/cuda-toolkit-archive) You want 10.1 for Tensorflow 2.1
    - [Cuda Toolkit Update 2](https://developer.nvidia.com/cuda-10.1-download-archive-update2)
    - Use the Default Install Path
    - Add it to your _%PATH%_ Variable
- [cuDNN](https://developer.nvidia.com/cudnn) You want 7.6 for Tensorflow 2.1
    - [cuDNN Download](https://developer.nvidia.com/rdp/cudnn-download)
    - Put in the Install path used for Cuda
    - Add it to your _%PATH%_ Variable
- [TensorRT Installation Guide](https://docs.nvidia.com/deeplearning/sdk/tensorrt-install-guide/index.html)
    - [TensorRT](https://developer.nvidia.com/tensorrt)


### External Instructions

[Towards Data Science](https://towardsdatascience.com/installing-tensorflow-with-cuda-cudnn-and-gpu-support-on-windows-10-60693e46e781)

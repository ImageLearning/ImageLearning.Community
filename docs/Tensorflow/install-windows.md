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

1. [Visual C++ Redist](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads)
1. [Cuda Toolkit](https://developer.nvidia.com/cuda-toolkit-archive) _You want 10.1 for Tensorflow 2.1_
    - [Cuda Toolkit Update 2](https://developer.nvidia.com/cuda-10.1-download-archive-update2)
    1. Use the Default Install Path
    1. Add the Bin folder to your _%PATH%_ variable
        - Likely 'C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin'
    1. Add the libnvvp folder to your_%PATH%_ variable
        - Likely 'C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\libnvvp'
1. [cuDNN](https://developer.nvidia.com/cudnn) _You want 7.6 for Tensorflow 2.1_
    - [cuDNN Download](https://developer.nvidia.com/rdp/cudnn-download)
    1. Put the files from 'cuda\' in the Install path used for Cuda set 
        - likely 'CUDA\v10.1\' 
    - You added this to your _%PATH%_ variable in the last step. no need to do it now
1. [TensorRT Installation Guide](https://docs.nvidia.com/deeplearning/sdk/tensorrt-install-guide/index.html)
    - [TensorRT](https://developer.nvidia.com/tensorrt)
1. [Python](https://www.python.org/downloads/) _You want version 3.7.7_
    - [3.7.7 Download and Release Notes](https://www.python.org/downloads/release/python-377/)

#### Tesla Compute Cluster

**From the Nvidia Website:** : _The TCC (Tesla Compute Cluster) driver is a Windows driver that supports CUDA C/C++ applications. The driver enables remote desktop services, and reduces the CUDA kernel launch overhead on Windows. Note that the TCC driver disables graphics on the Tesla products._

If you wish to install multiple GPU's with an NVLink and setup a [Tesla compute cluster](https://docs.nvidia.com/gameworks/content/developertools/desktop/nsight/tesla_compute_cluster.htm) you need to make sure that your Nvidia driver, and CUDA install installed the NVSMI folder. If it was not installed but your driver, that is not unusual, some OEM's remove it, and in some driver revisions it is missing. It should exist here : "c:\Program Files\NVIDIA Corporation\NVSMI", if it does not, you can try the following
- Try installing a different driver
    - _The 442.50 and 436.30 series drivers both had it, however I had a lot of trouble in summer 2019 with the late 390 / early 400's_
- Try copying it from a different machine. _AFAIK, it's just a front end and toggles some settings that users can't touch_
- Google for it, then see if a driver upgrade _(when you have the folder)_ upgrades it


Once you have it correctly installed
- Open an Admin Level Command prompt
- CD to "c:\Program Files\NVIDIA Corporation\NVSMI"
- Run "nvidia-smi.exe -L"  to list your devices
- run "nvidia-smi.exe -i # -dm TCC" replacing # with the # from the step above for every GPU you wish to add to the telsa compute cluster

### External Instructions

[Towards Data Science Tensorflow 1.X with GPU Support](https://towardsdatascience.com/installing-tensorflow-with-cuda-cudnn-and-gpu-support-on-windows-10-60693e46e781)

[NVLink on Quadro and Geforce RTX](https://www.pugetsystems.com/labs/support-hardware/How-to-Enable-and-Test-NVIDIA-NVLink-on-Quadro-and-GeForce-RTX-Cards-in-Windows-10-1266/#EnablingNVLinkonGeForceandQuadroRTXVideoCards)

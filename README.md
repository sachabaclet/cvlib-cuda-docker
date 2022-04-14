# Tensorflow, OpenCV, cvlib with CUDA Docker image

A Dockerfile to build a Docker image with [Tensorflow](https://github.com/tensorflow/tensorflow) and [OpenCV](https://github.com/opencv/opencv) both compiled with NVIDIA CUDA support, with Python 3 bindings, as well as [cvlib](https://github.com/arunponnusamy/cvlib), a high-level and easy-to-use Computer Vision library for Python. 
The [opencv-contrib](https://github.com/opencv/opencv_contrib) modules are included.
This image is based on the [official NVIDIA Tensorflow Docker image](https://catalog.ngc.nvidia.com/orgs/nvidia/containers/tensorflow).

This work is based on [opencv-cuda-docker by Julian Aßmann](https://github.com/JulianAssmann/opencv-cuda-docker).

## Pre-requisites

- Latest [NVIDIA GPU drivers](https://docs.nvidia.com/datacenter/tesla/tesla-installation-notes/index.html) (v.510 at the time of writing)
- [Docker Engine](https://docs.docker.com/engine/install/)
- [NVIDIA Docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker)

Note: You will also need some available storage (more than 30GB is recommended).

## How to build

```bash
cd <Dockerfile_directory/>
sudo docker build -t cvlib_cuda .
```

This may take several hours depending on your specs.  
Multiple warnings may pop up during the compilation of OpenCV.

## How to run

```bash
sudo docker run --gpus all -it cvlib_cuda
```

# Tensorflow, OpenCV, cvlib with CUDA Docker image

A Dockerfile to build a Docker image which includes:
- [Tensorflow](https://github.com/tensorflow/tensorflow) with CUDA support,
- [OpenCV](https://github.com/opencv/opencv) with CUDA support, cuDNN support and Python 3 bindings,
- [opencv-contrib](https://github.com/opencv/opencv_contrib),
- [cvlib](https://github.com/arunponnusamy/cvlib), a high-level and easy-to-use Computer Vision library for Python.

This image is based on the [official NVIDIA Tensorflow Docker image](https://catalog.ngc.nvidia.com/orgs/nvidia/containers/tensorflow).
The Dockerfile is based on a modification of [opencv-cuda-docker by Julian Aßmann](https://github.com/JulianAssmann/opencv-cuda-docker).

## Pre-requisites

- Latest [NVIDIA GPU drivers](https://docs.nvidia.com/datacenter/tesla/tesla-installation-notes/index.html) (v.510 at the time of writing)
- [Docker Engine](https://docs.docker.com/engine/install/)
- [NVIDIA Container Runtime / nvidia-docker2](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker)

Note: You will also need some available storage (more than 30GB is recommended).

## How to build

```bash
cd <Dockerfile_directory/>
sudo docker build -t cvlib_cuda .
```

Building the image may take one to several hours depending on your specs.  
Multiple warnings may pop up during the compilation of OpenCV.

## How to run

```bash
sudo docker run --gpus all -it cvlib_cuda
```

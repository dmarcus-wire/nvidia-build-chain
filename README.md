# nvidia-build-chain

from https://ngc.nvidia.com/catalog/containers/nvidia:cuda

Three flavors of images are provided:

1. base: Includes the CUDA runtime (cudart)
1. runtime: Builds on the base and includes the CUDA math libraries, and NCCL. A runtime image that also includes cuDNN is available.
1. devel: Builds on the runtime and includes headers, development tools for building CUDA images. These images are particularly useful for multi-stage builds.

podman pull nvcr.io/nvidia/cuda:11.3.0-cudnn8-runtime-centos8

The "latest" tag for CUDA, CUDAGL, and OPENGL images has been deprecated on NGC and Docker Hub.

from: https://github.com/sclorg/s2i-base-container

s2i image versions currently provided are:

core - rhel7 base + s2i settings
base - s2i-core + development libraries + npm



Container Image = set of software ready to run
Container = running instance of container image
Image Stream = set of pointers (tags) to a Docker Image
Image Stream Tag = points to a Docker Image in a registry somewhere
Image Stream Image = all the details (metadata) of the actual image itself
Image Stream Trigger = causes a specific action an a tag changes
Image Tag = distinguishing label applied to container image (ex. :latest)
Image ID = Secure Hash Algorithm (SHA) used to pull a specific image
Image Registry = stores and serves Container Images


Create Image Stream for nvidia cuda container
`oc import-image approved-cuda:11.0.3 --from=nvcr.io/nvidia/cuda:11.3.0-cudnn8-runtime-centos8 --confirm`


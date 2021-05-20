# nvidia-build-chain

from https://ngc.nvidia.com/catalog/containers/nvidia:cuda

Three flavors of images are provided:

base: Includes the CUDA runtime (cudart)
runtime: Builds on the base and includes the CUDA math libraries, and NCCL. A runtime image that also includes cuDNN is available.
devel: Builds on the runtime and includes headers, development tools for building CUDA images. These images are particularly useful for multi-stage builds.

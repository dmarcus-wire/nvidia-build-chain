# nvidia-build-chain

# Step 1:
1. ImageStream FROM "nvcr.io/nvidia/cuda:11.0.3-cudnn8-devel-ubi8" CREATE "nvidia-cuda"
1. ImageStream FROM "s2i-cuda"
1. ImageStream FROM "python-cuda"
1. BuildConfig FROM  "nvidia-cuda:11.0.3-ubi8" CREATE "s2i-cuda-11.0.3-base-ubi8"
1. BuildConfig FROM "s2i-cuda:11.0.3-base-ubi8" CREATE "s2i-cuda-11.0.3-core-ubi8" 
1. BuildConfig FROM "s2i-cuda:11.0.3-core-ubi8" CREATE "python-cuda-3.8-ubi8-cuda11.0.3"

# Step 2: 
1. ImageStream FROM s2i-minimal-notebook CREATE "jupyter-cuda"
1. BuildConfig FROM s2i-minimal-notebook CREATE jupyter-cuda-py3.8-ubi8-cuda11.0.3


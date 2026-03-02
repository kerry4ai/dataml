# DataML Docker Image

ML environment with PyTorch, R, and Julia based on NVIDIA PyTorch image.

## Base Image

`nvcr.io/nvidia/pytorch:26.02-py3`

## Features

- **NVIDIA PyTorch** - GPU-accelerated PyTorch with CUDA support
- **SSH Server** - Remote access via SSH (port 22)
- **R Environment** - Latest R with tidyverse, caret, randomForest, xgboost, ggplot2, dplyr
- **Julia Environment** - Latest stable Julia with DataFrames, CSV, Flux, GLM, Plots, StatsBase

## Exposed Ports

| Port | Service |
|------|---------|
| 22 | SSH |
| 8888 | Jupyter Lab |
| 6006 | TensorBoard |
| 8787 | RStudio Server |

## Quick Start

```bash
# Build
docker build -t dataml:latest .

# Run with GPU
docker run --gpus all -p 22:22 -p 8888:8888 -dit dataml:latest

# SSH access
ssh root@localhost  # default password: docker
```

## Environment Variables

- `ROOT_PASSWORD` - Root password for SSH (default: `docker`)
- `PYTORCH_IMAGE` - Base image override (default: `nvcr.io/nvidia/pytorch:26.02-py3`)

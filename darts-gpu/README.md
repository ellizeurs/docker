# JupyterLab Container
PyTorch and Darts with GPU Dockerfile
Contains
- PyTorch
- Darts
- Optuna
- RayTune
- PySwarm
- Other dependencies
---
###### Usage
The container is hosted on DockerHub and can be used with the command:
- Docker
``` bash
$ docker pull ellizeurs/torch-darts-gpu:cuda11.7
$ docker run -d --gpus all ellizeurs/torch-darts-gpu:cuda11.7
```
- Singularity
``` bash
$ singularity pull docker://ellizeurs/torch-darts-gpu:cuda11.7
$ singularity run --nv torch-darts-gpu_cuda11.7.sif
```
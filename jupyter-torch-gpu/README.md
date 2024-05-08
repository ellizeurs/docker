# JupyterLab Container
JupyterLab Dockerfile
Contains
- JupyterLab on port 10101
- PyTorch
- Optuna
- RayTune
- PySwarm
- Other dependencies
---
###### Usage
The container is hosted on DockerHub and can be used with the command:
- Docker
``` bash
$ docker pull ellizeurs/jupyter-lab-torch-darts-gpu:cuda11.7
$ docker run -d --gpus all -p 10101:10101 ellizeurs/jupyter-lab-torch-darts-gpu:cuda11.7
```
- Singularity
``` bash
$ singularity pull docker://ellizeurs/jupyter-lab-torch-darts-gpu:cuda11.7
$ singularity run --nv jupyter-lab-torch-darts-gpu_cuda11.7.sif
```
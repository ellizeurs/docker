# Use a imagem base com suporte a GPU do PyTorch com CUDA 11.7
FROM pytorch/pytorch:2.0.1-cuda11.7-cudnn8-runtime

# Instale dependências adicionais
RUN pip install --upgrade pip
RUN pip install darts
RUN pip install xlrd
RUN pip install openpyxl
RUN pip install lxml
RUN pip install optuna
RUN pip install ray
RUN pip install pyswarm

# Instale o Git
RUN apt-get update && apt-get install -y git

# Configurar ambiente para GPU
ENV NVIDIA_VISIBLE_DEVICES all
ENV NVIDIA_DRIVER_CAPABILITIES compute,utility

# Defina o diretório de trabalho
WORKDIR /workspace
# Use a imagem base com suporte a GPU do PyTorch com CUDA 11.7
FROM pytorch/pytorch:2.0.1-cuda11.7-cudnn8-runtime

# Instale dependências adicionais
RUN pip install --upgrade pip
RUN pip install xlrd
RUN pip install openpyxl
RUN pip install lxml
RUN pip install pyswarm

# Instale o Git
RUN apt-get update && apt-get install -y git

# Configurar ambiente para GPU
ENV NVIDIA_VISIBLE_DEVICES all
ENV NVIDIA_DRIVER_CAPABILITIES compute,utility

# Instale dependências adicionais
RUN pip install jupyterlab
RUN pip install ipywidgets

# Exponha a porta do Jupyter Lab
EXPOSE 10101

# Inicie o Jupyter Lab ao iniciar o contêiner
CMD ["jupyter", "lab", "--port=10101", "--ServerApp.iopub_msg_rate_limit=1000000000","--no-browser", "--allow-root"]
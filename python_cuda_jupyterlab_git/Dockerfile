# Use a imagem base do Python 3.12.4
FROM python:3.12.4

# Instale git
RUN apt-get update && apt-get install -y git

# Instale JupyterLab e JupyterLab-Git
RUN pip install jupyterlab jupyterlab-git==0.50.0

# Configuração para permitir que JupyterLab seja acessível de qualquer lugar (não apenas localhost)
EXPOSE 8888
# Inicie o Jupyter Lab ao iniciar o contêiner
CMD ["jupyter", "lab", "--port=8888", "--ServerApp.iopub_msg_rate_limit=1000000000","--no-browser", "--allow-root"]

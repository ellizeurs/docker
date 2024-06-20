# Use a imagem base do Python 3.12.4
FROM python:3.12.4

# Instale git
RUN apt-get update && apt-get install -y git

# Instale JupyterLab e JupyterLab-Git
RUN pip install jupyterlab jupyterlab-git==0.50.0

# Configuração para permitir que JupyterLab seja acessível de qualquer lugar (não apenas localhost)
EXPOSE 8888
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]

# Use a imagem base com suporte a GPU do PyTorch com CUDA 11.7
FROM ellizeurs/torch-darts-gpu:cuda11.7

# Instale dependências adicionais
RUN pip install jupyterlab
RUN pip install ipywidgets

# Exponha a porta do Jupyter Lab
EXPOSE 10101

# Inicie o Jupyter Lab ao iniciar o contêiner
CMD ["jupyter", "lab", "--port=10101", "--ServerApp.iopub_msg_rate_limit=1000000000","--no-browser", "--allow-root"]
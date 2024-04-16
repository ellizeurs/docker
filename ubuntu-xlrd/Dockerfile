# Use a imagem base do Ubuntu
FROM ubuntu:latest

# Atualize o sistema e instale o XRDP e o XFCE4 (ou outro ambiente de desktop de sua preferência)
RUN apt-get update
RUN apt-get install -y xrdp xfce4 
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*

# Abra a porta 3389 para o XRDP
EXPOSE 3389

# Inicialize o XRDP
CMD ["xrdp", "--nodaemon"]
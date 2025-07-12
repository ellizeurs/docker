FROM php:8.2-apache

RUN apt-get update && apt-get install -y openssl \
    && a2enmod rewrite ssl proxy proxy_http headers

# Gera certificado autoassinado no build
RUN mkdir -p /etc/ssl/private /etc/ssl/certs && \
    openssl req -x509 -nodes -days 365 \
      -newkey rsa:2048 \
      -keyout /etc/ssl/private/server.key \
      -out /etc/ssl/certs/server.crt \
      -subj "/C=BR/ST=RJ/L=RioDeJaneiro/O=EllizeuSena/OU=TI/CN=localhost"

# Copiar conf personalizada
COPY apache.conf /etc/apache2/sites-available/000-default.conf

# Copiar código fonte PHP (src) e .htaccess
COPY .htaccess /var/www/html/.htaccess

RUN chown -R www-data:www-data /var/www/html

EXPOSE 80 443

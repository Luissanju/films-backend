# Imagen base
FROM debian:latest

# Autor
LABEL org.opencontainers.image.authors="luissanjuan.alu@iespacomolla.es"

# Instalar dependencias
RUN apt-get update && apt-get install -y \
    apache2 \
    php \
    php-mysql \
    php-yaml \
    libapache2-mod-php \
    curl \
    nano

# Habilitar módulos de Apache
RUN a2enmod rewrite headers

# Copiar código fuente
COPY app /var/www/html

# Permisos para Apache
RUN chown -R www-data:www-data /var/www/html && chmod -R 755 /var/www/html

# Exponer puerto 80
EXPOSE 80

# Comando de arranque
CMD ["apache2ctl", "-D", "FOREGROUND"]

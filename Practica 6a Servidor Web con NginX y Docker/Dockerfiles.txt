FROM php:7.4-apache

# Instalar extensiones necesarias para PHP
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Copiar la configuración de Apache
COPY ./src /var/www/html/

# Habilitar el módulo de reescritura de Apache
RUN a2enmod rewrite

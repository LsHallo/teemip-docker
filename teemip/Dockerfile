FROM php:8-fpm-bookworm

WORKDIR /app

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

# Install required PHP extensions
RUN apt-get update \
    && apt-get install -y \
        unzip \
        zlib1g-dev \
        libpng-dev \
        libxml2-dev \
        libzip-dev \
        libldap-dev \
        graphviz \
    && apt-get clean \
    && docker-php-ext-install gd mysqli soap zip ldap

# Download TeemIP latest zip
ADD https://sourceforge.net/projects/teemip/files/latest/download /app/teemip.zip

# Extract and set permissions
RUN unzip teemip.zip \
    && rm teemip.zip \
    && cp -r web/* /var/www/html \
    && rm -r /app/* \
    && chown www-data:www-data -R /var/www/html


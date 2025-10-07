FROM php:8.2.29-fpm

RUN apt-get update \
    && apt-get install -y \
    # precisa para dokcer-php-ext-install
    libzip-dev \
    git

# Instalr extensões do PHP
RUN docker-php-ext-install \
    zip \
    pdo \
    pdo_mysql

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY ./ /var/www/html

# Instalar pacotes da aplicação
RUN composer install

# Porta fpm
EXPOSE 9000

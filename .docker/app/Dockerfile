FROM php:8.2.29-fpm

WORKDIR /var/www/html

# Instalar dependências PHP + Node
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    curl \
    libzip-dev \
    nodejs \
    npm \
    && docker-php-ext-install zip pdo pdo_mysql

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Copiar projeto Laravel
COPY ./ /var/www/html

# Instalar dependências PHP e Node
RUN composer install
RUN npm install

# Expor portas
EXPOSE 9000 5173

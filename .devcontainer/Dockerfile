FROM php:8.2.29-fpm

WORKDIR /var/www/html

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    curl \
    libzip-dev \
    libonig-dev \
    && docker-php-ext-install zip pdo pdo_mysql \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && curl -fsSL https://deb.nodesource.com/setup_lts.x | bash - \
    && apt-get install -y nodejs \
    && apt-get clean && rm -rf /var/lib/apt/lists/*


# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Copiar projeto Laravel
COPY ./ /var/www/html

# Instalar dependências PHP e Node
RUN composer install
RUN npm install

# Expor portas
EXPOSE 9000 5173

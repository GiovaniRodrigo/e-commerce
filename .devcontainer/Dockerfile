FROM php:8.2.29-fpm

WORKDIR /var/www/html

# Install system dependencies and Microsoft ODBC
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    curl \
    libzip-dev \
    libonig-dev \
    gnupg \
    ca-certificates \
    apt-transport-https \
    lsb-release \
    unixodbc-dev \
    && curl -fsSL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > /etc/apt/trusted.gpg.d/microsoft.gpg \
    && curl -fsSL https://packages.microsoft.com/config/ubuntu/22.04/prod.list > /etc/apt/sources.list.d/mssql-release.list \
    && apt-get update \
    && ACCEPT_EULA=Y apt-get install -y msodbcsql18 \
    && docker-php-ext-install zip pdo \
    && pecl install sqlsrv pdo_sqlsrv \
    && docker-php-ext-enable sqlsrv pdo_sqlsrv \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && curl -fsSL https://deb.nodesource.com/setup_lts.x | bash - \
    && apt-get install -y nodejs \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Copy Laravel project
COPY ./ /var/www/html

# Install dependencies
RUN composer install
RUN npm install

# Expose ports
EXPOSE 9000 5173

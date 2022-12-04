FROM php:8.1-fpm

# библиотека libpq-dev нужна, чтобы установить pdo_pgsql
RUN apt-get update && apt-get install -y \
    libpq-dev \
    git \
    zip \
    curl \
    sudo \
    unzip

RUN pecl install redis && docker-php-ext-enable redis && docker-php-ext-install pdo_mysql pdo_pgsql

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
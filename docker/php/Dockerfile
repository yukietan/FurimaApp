FROM php:8.3-fpm-alpine

COPY php.ini /usr/local/etc/php/

RUN apk update \
    && apk add --no-cache \
    mysql-client \
    libzip-dev \
    zlib-dev \
    unzip \
    curl \
    bash

RUN docker-php-ext-install pdo_mysql zip

RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer \
    && composer self-update

WORKDIR /var/www
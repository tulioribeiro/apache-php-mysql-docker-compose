ARG PHP_VERSION=""
FROM php:${PHP_VERSION:+${PHP_VERSION}-}fpm-alpine

RUN apk update; \
    apk upgrade;

RUN apk add --update --no-cache \
        freetype-dev \
        libjpeg-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd

RUN docker-php-ext-install pdo pdo_mysql

RUN docker-php-ext-enable pdo_mysql
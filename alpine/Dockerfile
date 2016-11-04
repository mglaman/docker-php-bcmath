FROM php:7.0-fpm-alpine
MAINTAINER Matt Glaman <nmd.matt@gmail.com>
# Install modules
RUN apk add --no-cache \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        libxml2-dev \
        && docker-php-ext-install mcrypt zip bcmath pdo_mysql mysqli mbstring opcache soap \
        && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
        && docker-php-ext-install gd

# Setup xdebug
RUN pecl install xdebug-beta && docker-php-ext-enable xdebug

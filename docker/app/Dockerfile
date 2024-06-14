FROM php:8.2-fpm

ENV TZ Asia/Tokyo

RUN apt-get update && \
    apt-get install -y git unzip libzip-dev libonig-dev libicu-dev libpq-dev && \
    docker-php-ext-install zip pdo_mysql intl bcmath

COPY ./docker/app/php.ini /usr/local/etc/php/php.ini

COPY --from=composer:2.2 /usr/bin/composer /usr/bin/composer

WORKDIR /app
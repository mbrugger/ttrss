FROM php:7.4-fpm-alpine

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

RUN apk add --no-cache git libgd libintl icu-libs icu-dev postgresql-libs zlib-dev libpng-dev postgresql-dev && \
  docker-php-ext-install intl gd pcntl pgsql pdo_pgsql && \
  apk del icu-dev zlib-dev libpng-dev postgresql-dev

EXPOSE 9000
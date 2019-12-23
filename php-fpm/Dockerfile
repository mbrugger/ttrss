FROM php:7.4-fpm-alpine

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

RUN apk add --no-cache php7-intl php7-dom php7-gd php7-iconv php7-pcntl php7-fileinfo \
  php7-json php7-pgsql php7-pdo php7-pdo_pgsql php7-mbstring php7-posix php7-session

EXPOSE 9000
FROM php:7.2-fpm-alpine

WORKDIR /var/www

RUN apk update && apk add curl && \
  curl -sS https://getcomposer.org/installer | php \
  && chmod +x composer.phar && mv composer.phar /usr/local/bin/composer

RUN apk update && apk add --no-cache postgresql-dev libpng-dev

RUN docker-php-ext-install pdo pdo_mysql pdo_pgsql pgsql gd


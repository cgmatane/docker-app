FROM php:7.2-fpm-alpine

RUN apk update && apk add --no-cache postgresql-dev

RUN docker-php-ext-install pdo pdo_mysql pdo_pgsql pgsql

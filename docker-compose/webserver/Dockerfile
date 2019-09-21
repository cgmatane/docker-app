# Set master image
FROM php:7.2-fpm-alpine

# Set working directory
WORKDIR /var/www/html

# Install Additional dependencies
RUN apk update && apk add --no-cache \
    build-base shadow vim curl nano \
    php7 \
    php7-fpm \
    php7-common \
    php7-pdo \
    php7-pdo_mysql \
    php7-mysqli \
    php7-mcrypt \
    php7-mbstring \
    php7-xml \
    php7-openssl \
    php7-json \
    php7-phar \
    php7-zip \
    php7-gd \
    php7-dom \
    php7-session \
    php7-zlib \
    php7-pgsql \
    php7-pdo_pgsql \
    php7-exif \
    postgresql-dev

# Add and Enable PHP-PDO Extenstions
RUN docker-php-ext-install pdo pdo_mysql pgsql pdo_pgsql exif
RUN docker-php-ext-enable pdo_mysql pdo_pgsql

# Install PHP Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


FROM php:7.2-fpm
RUN apt-get update && apt-get install -y nano wget zlib1g-dev git unzip

RUN docker-php-ext-install pdo pdo_mysql bcmath zip

RUN apt install -y libmagickwand-dev --no-install-recommends && \
    pecl install imagick && docker-php-ext-enable imagick && \
    rm -rf /var/lib/apt/lists/*

RUN pecl install xdebug-2.7.1 && docker-php-ext-enable xdebug
ADD ./php.ini /usr/local/etc/php/php.ini
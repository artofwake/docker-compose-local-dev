FROM php:7.2-fpm
RUN apt-get update && apt-get install -y nano wget zlib1g-dev git unzip

RUN docker-php-ext-install pdo pdo_mysql bcmath zip gd

RUN apt install -y libmagickwand-dev --no-install-recommends && \
    pecl install imagick && docker-php-ext-enable imagick && \
    rm -rf /var/lib/apt/lists/*

RUN pecl install xdebug-2.7.1 && docker-php-ext-enable xdebug
ADD ./php.ini /usr/local/etc/php/php.ini

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get install -y nodejs

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

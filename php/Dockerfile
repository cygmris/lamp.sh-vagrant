FROM php:5.6-fpm

ADD php.ini    /usr/local/etc/php/php.ini
ADD php-fpm.conf    /usr/local/etc/php-fpm.conf
ADD sources.list    /etc/apt/sources.list

RUN apt-get update \
    && apt-get install -y libpng-dev

RUN docker-php-ext-install gd \
    && docker-php-ext-install pdo_mysql

ADD composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer

WORKDIR /opt
RUN usermod -u 1000 www-data

VOLUME ["/opt"]

FROM php:7.2-fpm
MAINTAINER Kondin Dmitriy <kondin@etown.ru>

RUN apt-get update && apt-get install -y \
        curl \
        wget \
        git \
        vim \
        less \
        mc \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        openssl  \
        libssl-dev  \
        libcurl4-openssl-dev\
    && pecl install mongodb \
    && docker-php-ext-install -j$(nproc) mongodb \

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
ADD php.ini /usr/local/etc/php/conf.d/40-custom.ini
WORKDIR /var/www
CMD ["php-fpm"]

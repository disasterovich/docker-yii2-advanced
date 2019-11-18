FROM php:7.2-fpm

RUN apt-get update && \
    apt-get -y install \
        curl \
        libxml2-dev \
        zlib1g-dev \
        libzip-dev \
        libcurl3-dev \
        libpng-dev \
        libpq-dev \
        imagemagick

RUN docker-php-ext-install \
        zip \
        curl \
        bcmath \
        exif \
        gd \
        iconv \
        intl \
        mbstring \
        opcache \
        pdo_mysql

CMD ["php-fpm"]

EXPOSE 9000

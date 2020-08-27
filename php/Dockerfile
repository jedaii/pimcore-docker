FROM php:7.4-fpm
RUN apt-get update && apt-get install -y \
git \
curl \
libfreetype6-dev \
libcurl3-dev \
libicu-dev \
libmcrypt-dev \
libfreetype6-dev \
libjpeg-dev \
libjpeg62-turbo-dev \
libmagickwand-dev \
libpq-dev \
libpng-dev \
libxml2-dev \
libzip-dev \
zlib1g-dev \
--no-install-recommends \
&& docker-php-ext-install -j$(nproc) iconv \
mysqli \
bcmath \
-j$(nproc) gd \
intl \
pdo_mysql \
opcache \
soap \
zip \
exif

RUN apt-get update && apt-get install -y \
libmagickwand-dev --no-install-recommends \
&& pecl install imagick \
&& docker-php-ext-enable imagick

RUN curl -sS https://getcomposer.org/installer | php -- \
--filename=composer \
--install-dir=/usr/local/bin && \
composer clear-cache

WORKDIR /var/www

CMD ["php-fpm"]

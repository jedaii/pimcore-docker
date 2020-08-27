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
&& docker-php-ext-install -j$(nproc) iconv  mysqli

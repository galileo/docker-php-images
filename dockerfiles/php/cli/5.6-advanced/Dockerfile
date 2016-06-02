FROM galileo/php:5.6
LABEL version='5.6-advanced'
MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

# Install mcrypc
# Install intl
# Install xsl Extension
RUN apt-get update && apt-get install -y \
        libmcrypt-dev \
        libicu-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng12-dev \
        libxslt1-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) \
        gd \
        intl \
        mcrypt \
    && docker-php-ext-install \
        xsl \
        exif \
        mysql \
        mysqli \
        mbstring \
        pdo_mysql

RUN apt-get purge -y libxslt1-dev

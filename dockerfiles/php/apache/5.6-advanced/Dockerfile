FROM php:5.6-apache

MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

# Install mcrypc
RUN apt-get update && apt-get install -y \
        libmcrypt-dev \
    && docker-php-ext-install -j$(nproc) mcrypt

# Install intl
RUN apt-get update && apt-get install -y \
        libicu-dev \
    && docker-php-ext-install -j$(nproc) intl

# Install gd
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng12-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

# Install xsl Extension
RUN apt-get install -y libxslt1-dev \
    && docker-php-ext-install xsl \
    && apt-get purge -y libxslt1-dev

# Install additional Extensions
RUN docker-php-ext-install \
  mysql \
  mysqli \
  pdo_mysql

RUN docker-php-ext-install exif

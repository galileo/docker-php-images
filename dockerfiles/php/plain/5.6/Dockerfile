FROM php:5.6

MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

# install composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# setup composer to install globally
ENV COMPOSER_BIN_DIR="/usr/local/bin"
ENV COMPOSER_ALLOW_SUPERUSER="true"

# only heavy required packages
RUN apt-get update && apt-get install -y \
	git


FROM php:5.6

MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive \
    COMPOSER_BIN_DIR="/usr/local/bin" \
    TIMEZONE=UTC \
    COMPOSER_ALLOW_SUPERUSER="true"

# install composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# only heavy required packages
RUN apt-get update && apt-get install -y \
	git

RUN cp /usr/src/php/php.ini-production ${PHP_INI_DIR}/php.ini \
    && echo "date.timezone = $TIMEZONE" >> ${PHP_INI_DIR}/php.ini

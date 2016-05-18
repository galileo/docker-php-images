FROM php:5.6
LABEL version='5.6-php'
MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive \
    COMPOSER_BIN_DIR="/usr/local/bin" \
    COMPOSER_ALLOW_SUPERUSER="true" \
    MEMORY_LIMIT="1024M" \
    TIMEZONE=UTC

# install composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# only heavy required packages
RUN apt-get update && apt-get install -y \
	git \
	vim

RUN echo $TIMEZONE > /etc/timezone && dpkg-reconfigure --frontend noninteractive tzdata

RUN cp /usr/src/php/php.ini-production ${PHP_INI_DIR}/php.ini \
    && echo "date.timezone = $TIMEZONE" >> ${PHP_INI_DIR}/php.ini \
    && echo "memory_limit = $MEMORY_LIMIT" >> ${PHP_INI_DIR}/php.ini

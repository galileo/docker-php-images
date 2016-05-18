FROM php:5.6-apache
LABEL version='5.6-apache'
MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

# setup composer to install globally
ENV DEBIAN_FRONTEND=noninteractive \
    COMPOSER_BIN_DIR="/usr/local/bin" \
    COMPOSER_ALLOW_SUPERUSER="true" \
    TIMEZONE=UTC

# install composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# only heavy required packages
RUN apt-get update && apt-get install -y \
	git

RUN echo $TIMEZONE > /etc/timezone && dpkg-reconfigure --frontend noninteractive tzdata
RUN cp /usr/src/php/php.ini-production ${PHP_INI_DIR}/conf.d/php.ini \
    && echo "date.timezone = $TIMEZONE" >> ${PHP_INI_DIR}/conf.d/php.ini

RUN echo 'memory_limit = 1024M' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"

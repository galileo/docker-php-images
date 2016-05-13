FROM php:5.6

RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

RUN apt-get update && apt-get install -y \
	git


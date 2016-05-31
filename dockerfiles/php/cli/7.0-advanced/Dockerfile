FROM galileo/php:7.0
LABEL version='7.0-advanced'
MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

RUN apt-get update -q -y \
 && apt-get install -q -y --force-yes --no-install-recommends \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libxpm-dev \
        libpng12-dev \
        libicu-dev \
        libxslt1-dev \
        ca-certificates \
        curl \
        acl \
        sudo \
        unzip \
        && rm -rf /var/lib/apt/lists/*


RUN docker-php-ext-configure mysqli --with-mysqli=mysqlnd \
 && docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd \
 && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/ --with-xpm-dir=/usr/include/ --enable-gd-native-ttf --enable-gd-jis-conv \
 && docker-php-ext-install exif gd mbstring intl xsl zip mysqli pdo_mysql \
 && docker-php-ext-enable opcache


RUN apt-get purge -y libxslt1-dev

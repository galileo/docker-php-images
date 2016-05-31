FROM galileo/php:7.0-advanced-phpunit-4
LABEL version='7.0-advanced-phpunit-4-xdebug'
MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

RUN yes | pecl install xdebug

RUN echo 'zend_extension=xdebug.so' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"
RUN echo 'xdebug.remote_enable = 1' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"
RUN echo 'xdebug.remote_connect_back = 1' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"
RUN echo 'xdebug.remote_autostart = 1' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"


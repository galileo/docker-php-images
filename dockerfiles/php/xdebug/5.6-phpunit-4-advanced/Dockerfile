FROM galileo/php:5.6-phpunit-4-advanced

MAINTAINER Kamil Ronewicz <galileox86@gmail.com>

RUN yes | pecl install xdebug

RUN echo 'zend_extension=xdebug.so' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"
RUN echo 'xdebug.remote_enable = 1' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"
RUN echo 'xdebug.remote_connect_back = 1' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"
RUN echo 'memory_limit = 1024M' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"
RUN echo 'xdebug.remote_autostart = 1' >> "${PHP_INI_DIR}/conf.d/20-xdebug.ini"


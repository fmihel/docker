FROM php:7.4-apache
LABEL maintainer="fmihel76@gmail.com"

RUN apt-get update \ 
    && apt-get upgrade -y \
    && apt-get install autoconf automake mc -y \
    && docker-php-ext-install mysqli \
    && mkdir /opt/xdebug/ \
    && curl https://xdebug.org/files/xdebug-3.1.6.tgz -o /opt/xdebug.tgz \ 
    && tar -zxvf /opt/xdebug.tgz -C /opt/xdebug/ \ 
    && rm -rf /opt/xdebug.tgz \
    && cd /opt/xdebug/xdebug-3.1.6/ \
    && phpize \ 
    && ./configure \
    && make\
    && cp modules/xdebug.so /usr/local/lib/php/extensions/no-debug-non-zts-20190902\
    && a2enmod headers \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer
RUN apt-get -y install libmagickwand-dev \
    && pecl install imagick \
    && docker-php-ext-enable imagick
# RUN apt-get update -y && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev
# RUN set -eux; docker-php-ext-configure gd --with-freetype --with-jpeg; \
    # docker-php-ext-install exif gd
RUN apt-get update && \
    apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev && \
    docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ && \
    docker-php-ext-install gd

#FROM php:7.1-fpm
#FROM php:7.4-fpm
#FROM php:5.5-fpm
#FROM php:5.6-fpm
FROM php:8.3-fpm

ADD php.ini /usr/local/etc/php/php.ini
ADD php-fpm.conf /usr/local/etc/php-fpm.conf

EXPOSE 9000

RUN apt-get update -y && apt-get install -y \
    zlib1g-dev \
    libjpeg-dev \
    libfreetype6-dev \
#    libmagick++-dev \
#    libmagickwand-dev \ 
    libpq-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libonig-dev \
    libwebp-dev \
    libxpm-dev \
    libzip-dev \
    zip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg=/usr/include/ --enable-gd

#COPY redis.tgz /home/redis.tgz
RUN pecl channel-update pecl.php.net \
 && docker-php-ext-install gd \
 && docker-php-ext-install zip \
 && docker-php-ext-install opcache \
 && docker-php-ext-install pdo_mysql \
# && docker-php-ext-install mysql \ 
 && docker-php-ext-install mysqli \
 && apt-get install -y libicu-dev \
 && docker-php-ext-install intl \
 && docker-php-ext-install intl \
# && pecl install imagick-3.4.3 \
# && pecl install xdebug \
# && pecl install mongodb \
# && docker-php-ext-enable xdebug \
# && docker-php-ext-enable imagick \
 && docker-php-ext-enable gd

#RUN docker-php-ext-install gd \
#   && docker-php-ext-install pdo_mysql \
#   && pecl install /home/redis.tgz && echo "extension=redis.so" > /usr/local/etc/php/conf.d/redis.ini
ADD composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer
ADD deployer.phar /usr/local/bin/dep
RUN chmod 755 /usr/local/bin/dep
ADD phpunit.phar /usr/local/bin/phpunit
RUN chmod 755 /usr/local/bin/phpunit


#WORKDIR /opt
RUN usermod -u 1000 www-data

#VOLUME ["/opt"]

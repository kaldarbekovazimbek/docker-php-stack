FROM php:8.2-fpm

RUN docker-php-ext-install mysqli

#RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY --from=composer:2.8 /usr/bin/composer /usr/bin/composer

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

COPY conf.d/* $PHP_INI_DIR/conf.d
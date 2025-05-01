FROM php:8.4.6-fpm-alpine

RUN apk add --no-cache --virtual .build-deps \
  $PHPIZE_DEPS \
  freetype-dev \
  libjpeg-turbo-dev \
  libpng-dev \
  icu-dev \
  oniguruma-dev \
  && docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install -j$(nproc) \
  intl \
  pdo_mysql \
  mysqli \
  gd \
  mbstring \
  opcache \
  && apk del .build-deps

RUN wget -qO /usr/local/bin/composer \
  https://getcomposer.org/download/2.8.8/composer.phar \
  && chmod +x /usr/local/bin/composer

COPY php.ini /usr/local/etc/php/conf.d/app.ini

WORKDIR /var/www/html

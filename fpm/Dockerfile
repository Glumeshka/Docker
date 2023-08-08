FROM php:8.1-fpm

RUN apt-get update && apt-get install -y \
  curl \
  wget \
  git \
  libfreetype6-dev \
  libjpeg62-turbo-dev \
  libpng-dev \
  libonig-dev \
  libzip-dev \
  libmcrypt-dev \
  && pecl install mcrypt-1.0.5 \
  && docker-php-ext-enable mcrypt \
  && docker-php-ext-install pdo_mysql \
  && docker-php-ext-configure gd --with-jpeg --with-freetype \
  && docker-php-ext-install -j$(nproc) gd

# Устанавливаем Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
 
WORKDIR /data
 
VOLUME /data
 
CMD ["php-fpm"]
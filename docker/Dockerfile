FROM php:8.3-apache

RUN apt-get update && apt-get install -y \
    libonig-dev \
  && docker-php-ext-install pdo_mysql mysqli

COPY --from=composer /usr/bin/composer /usr/bin/composer
ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer

COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf
RUN a2enmod rewrite

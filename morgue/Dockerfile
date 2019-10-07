FROM ubuntu:bionic as fetcher

RUN apt-get update && apt-get install --yes curl unzip
RUN curl -sL https://github.com/etsy/morgue/archive/master.zip -o morgue.zip
RUN unzip morgue.zip
RUN mv morgue-master morgue


FROM composer as composer

COPY --from=fetcher morgue /morgue

WORKDIR /morgue
RUN composer install

FROM php:7.3-apache

COPY --from=composer /morgue /var/www/html/morgue

RUN docker-php-ext-install pdo_mysql
RUN a2enmod rewrite

COPY morgue.conf /etc/apache2/sites-available/morgue.conf

RUN a2dissite 000-default
RUN a2ensite morgue

COPY config.json /var/www/html/morgue/config/development.json

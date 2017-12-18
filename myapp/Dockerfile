FROM php:7.0-apache

RUN apt-get update && \
    apt-get install -y php5-mysql && \
    apt-get clean

COPY app /var/www/html/
ADD /var/log/apache22

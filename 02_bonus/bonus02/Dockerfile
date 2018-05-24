FROM php:7.2.4-apache

RUN apt-get -y update && apt-get -y upgrade && apt-get install -y ssmtp mailutils && docker-php-ext-install pdo_mysql 

COPY ./ssmtp.conf /etc/ssmtp/ssmtp.conf

RUN echo 'sendmail_path=sendmail -i -t' >> /usr/local/etc/php/conf.d/php-sendmail.ini

RUN echo 'localhost localhost.localdomain' >> /etc/hosts
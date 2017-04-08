FROM ubuntu:trusty

RUN apt-get update && \
  apt-get -y install supervisor git curl apache2 libapache2-mod-php5 php5-mysql pwgen php-apc php5-mcrypt && \ 
  echo "ServerName localhost" >> /etc/apache2/apache2.conf

ADD vhost.conf /etc/apache2/sites-enabled/000-default.conf

# Setting up PHP configuration RUN 
RUN sed -i 's/memory_limit = 128M/memory_limit = 512M/' /etc/php5/apache2/php.ini
RUN sed -i 's/display_errors = Off/display_errors = On/' /etc/php5/apache2/php.ini
RUN sed -i 's/display_startup_errors = Off/display_startup_errors = On/' /etc/php5/apache2/php.ini
RUN sed -i 's/short_open_tag = Off/short_open_tag = On/' /etc/php5/apache2/php.ini

RUN a2enmod rewrite

RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/bin/composer

RUN mkdir -p /var/www/src
RUN usermod -u 1000 www-data

WORKDIR /var/www/src

EXPOSE 80

CMD /usr/sbin/apache2ctl -D FOREGROUND
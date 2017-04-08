FROM alpine:3.4

RUN apk update && \
  apk upgrade && \
  apk add --update \
    bash \
    curl \
    php5-phar \
    php5-common \
    php5-iconv \
    php5-mcrypt \
    php5-pdo \
    php5-ctype \
    php5-openssl \
    php5-pdo_mysql \
    php5-pdo_sqlite \
    php5-sqlite3 \
    php5-mysqli \
    php5-xml \
    php5-dom \
    php5-dev \
    php5-soap \
    php5-cli \
    php5-json \
    php5-mysql \
    php5-curl \
    php5-gd \
    php5-fpm && \
  rm /var/cache/apk/*

RUN adduser www-data -D ''

ADD app.ini /etc/php5/conf.d/

RUN mkdir -p /var/www

RUN sed -i -e 's|listen = 127.0.0.1:9000|listen = 9000|g' /etc/php5/php-fpm.conf
RUN sed -i -e 's|user = nobody|user = www-data|g' /etc/php5/php-fpm.conf

WORKDIR /var/app

EXPOSE 9000
ENTRYPOINT ["php-fpm","-F"]
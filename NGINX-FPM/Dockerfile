FROM trafex/alpine-nginx-php7
MAINTAINER scfobao <7913116@qq.com>
# php-redis
ENV PHPREDIS_VERSION 3.1.2
ENV COMPOSER_VERSION 1.1.2

RUN apk update
#ͬ²½ËÖ»ú
RUN apk add tzdata && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN apk del tzdata
RUN apk add  php7-redis \   
     php7-xdebug \
     php7-pcntl \
     php7-mbstring \
     php7-json \
     php7-sockets \
     php7-pdo_mysql \
     php7-pdo \
     php7-zip \
     php7-xml \
     php7-xmlrpc \
     php7-simplexml \
     php7-posix \
     php7-xsl \
     php7-intl \
     php7-gd \
     php7-xmlwriter \
     php7-opcache


RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=${COMPOSER_VERSION} && \
    chmod +x /usr/local/bin/composer     
COPY nginx.conf /etc/nginx/nginx.conf
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY app/*.conf /etc/nginx/conf.d/
COPY timezone.ini /etc/php7/conf.d/zzz_custom.ini          
WORKDIR /
#CMD ["/bin/sh"]

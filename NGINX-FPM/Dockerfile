FROM trafex/alpine-nginx-php7
MAINTAINER scfobao <7913116@qq.com>
# php-redis
ENV PHPREDIS_VERSION 3.1.2

RUN apk update
#ͬ²½ËÖ»ú
RUN apk add tzdata && cp /usr/share/zoneinfo/Asia/Chongqing /etc/localtime
RUN apk del tzdata
RUN apk add  php7-redis \   
     php7-xdebug \
     php7-pcntl \
     php7-mbstring \
     php7-json \
     php7-posix \
     php7-opcache
COPY nginx.conf /etc/nginx/nginx.conf
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY app/*.conf /etc/nginx/conf.d/
WORKDIR /
#CMD ["/bin/sh"]

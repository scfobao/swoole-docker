# sd-swoole
#FROM php:7.1.12-alpine
FROM trafex/alpine-nginx-php7
MAINTAINER liqinghua 7913116@qq.com
ENV COMPOSER_VERSION 1.1.2
# ¹¹½¨swoole»·¾³£¬ÔÕÀ°²װÁphp,swoole,composer
RUN apk update \
    && apk upgrade \    
    && apk add --no-cache $PHPIZE_DEPS  git autoconf build-base linux-headers libaio-dev php7-dev php7-pear openssl librdkafka-dev librdkafka php7-bcmath php7-redis libzip libzip-dev php7-opcache php7-redis php7-pdo php7-posix \
    openssl-dev \
    hiredis \
    hiredis-dev \
#    && pecl install zip \
#&& pecl install ZendOpcache \
    && pecl install inotify \
    && pecl install ds \
    && pecl install igbinary \
    && cd /home && rm -rf temp && mkdir temp && cd temp \
    && wget https://github.com/swoole/swoole-src/archive/v1.9.19.tar.gz \   
    # https://github.com/phpredis/phpredis/archive/3.1.2.tar.gz \     
    # && tar -xzvf 3.1.2.tar.gz \
    && tar -xzvf v1.9.19.tar.gz \
    && cd /home/temp/swoole-src-1.9.19 \
    && phpize && ./configure --enable-async-redis --enable-openssl && make \
    && make install \       
#   && cd /home/temp/phpredis-3.1.2 \
#   && phpize \
#   && ./configure --enable-redis-igbinary \
#   && make &&  make install \
    && cd /home && rm -rf temp && mkdir temp && cd temp \
    && git clone https://github.com/arnaud-lb/php-rdkafka.git \
    && cd php-rdkafka \
    && phpize \
    && ./configure \
    && make all -j 5 \
    && make install \
    && cd /etc/php7/conf.d \
    && echo extension=rdkafka.so>rdkafka.ini \
    && echo extension=igbinary.so>igbinary.ini \
    && echo extension=inotify.so>inotify.ini \
    && echo extension=swoole.so>swoole.ini \
# && echo extension=redis.so>redis.ini \
    && echo extension=ds.so>ds.ini  
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=${COMPOSER_VERSION} && \
    chmod +x /usr/local/bin/composer
RUN apk add tzdata && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime   

#RUN apk del --no-cache $PHPIZE_DEPS libaio-dev php7-dev openssl-dev hiredis-dev autoconf build-base linux-headers librdkafka-dev
#CMD ["bin/sh"]


#sd-swoole
#FROM sd-swoole
#FROM scfobao/myswoole:1.2
FROM scfobao/sd-swoole:1.0
MAINTAINER liqinghua 7913116@qq.com
RUN mkdir /apps
COPY composer.json /apps/composer.json
#COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
# 安装SD框架
#RUN cd /apps && composer install && php vendor/tmtbe/swooledistributed/src/Install.php -y
#RUN apt update
#RUN apt install nginx -y
#RUN apt install libmosquitto-dev -y
#RUN pecl install mosquitto-0.4.0
#RUN rm -f /etc/nginx/sites-enabled/default \
#        && cd /usr/local/etc/php/conf.d/ \
#        && echo extension=mosquitto.so>mosquitto.ini 
CMD ["php","/apps/bin/start_swoole_server.php","start"]
#ENTRYPOINT ["supervisord", "--nodaemon", "--configuration", "/etc/supervisor/conf.d/supervisord.conf"]

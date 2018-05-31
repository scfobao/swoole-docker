# sd3-swoole
FROM scfobao/sd3:1.1
MAINTAINER liqinghua 7913116@qq.com

RUN apt update
RUN apt install nginx -y
RUN apt install supervisor -y
RUN mkdir /apps
COPY composer.json /apps/composer.json
COPY supervisord.conf /etc/supervisord.conf
RUN rm -f /etc/nginx/sites-enabled/default
# 安装SD框架
RUN cd /apps && composer install && php vendor/tmtbe/swooledistributed/src/Install.php -y

#CMD ["php","/apps/bin/start_swoole_server.php","start"]
CMD ["/usr/bin/supervisord"] 

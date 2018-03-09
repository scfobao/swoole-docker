# sd-swoole
#FROM sd-swoole
FROM scfobao/myswoole:1.2
MAINTAINER liqinghua 7913116@qq.com
RUN mkdir /apps
COPY composer.json /apps/composer.json
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
# 安装SD框架
#RUN cd /apps && composer install && php vendor/tmtbe/swooledistributed/src/Install.php -y
#CMD ["php","/apps/bin/start_swoole_server.php","start"]
ENTRYPOINT ["supervisord", "--nodaemon", "--configuration", "/etc/supervisor/conf.d/supervisord.conf"]

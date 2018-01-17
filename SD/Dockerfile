# sd-swoole
FROM scfobao/sd-swoole:1.0
MAINTAINER liqinghua 7913116@qq.com
RUN mkdir /apps
COPY composer.json /apps/composer.json
# 安装SD框架
RUN cd /apps && composer install && php vendor/tmtbe/swooledistributed/src/Install.php -y

CMD ["php","/apps/bin/start_swoole_server.php","start"]

FROM 4devs/php:7.1

RUN yum -y install php-fpm && yum clean all

RUN useradd nginx -s /sbin/nologin && \
    chown nginx:nginx /var/www
COPY php-fpm.conf /etc/php-fpm.conf
COPY php-fpm.d/* /etc/php-fpm.d/

EXPOSE 9000

CMD ["php-fpm", "-F"]

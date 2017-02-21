FROM 4devs/centos

ENV REMI_REPO_VERSION 'remi-php71'
ENV PHP_TIMEZONE 'Europe/Moscow'

RUN yum-config-manager --enable ${REMI_REPO_VERSION} \
    && yum -y install php php-intl php-mbstring php-cli php-xml php-gd \
    && yum clean all

RUN sed -ri 's@;date.timezone =@date.timezone = '"$PHP_TIMEZONE"'@g' /etc/php.ini

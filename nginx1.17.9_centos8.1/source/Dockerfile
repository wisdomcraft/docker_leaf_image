FROM centos
MAINTAINER lihuilu<1760908473@qq.com>

ADD nginx_php.tar /

RUN useradd --no-create-home --shell /sbin/nologin www \
    && ln -s /usr/local/php/bin/php /usr/bin/php \
    && systemctl enable php-fpm \
    && systemctl enable nginx

EXPOSE 80


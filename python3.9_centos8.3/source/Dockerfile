FROM centos:8.3.2011
MAINTAINER lihuilu<1760908473@qq.com>

ADD python.tar /

RUN useradd --no-create-home --shell /sbin/nologin www \
    && ln -s /usr/local/python3.9/bin/python3.9 /usr/local/python3.9/bin/python \
    && echo -e "\nexport PATH=/usr/local/python3.9/bin:$PATH\n" >> /etc/profile \
    && source /etc/profile \
    && echo -e "\nsource /etc/profile\n" >> /root/.bashrc \
    && echo -e "\nalias ll='ls -l'\n" >> /root/.bashrc \
    && source /root/.bashrc

EXPOSE 80

CMD /usr/local/python3.9/bin/supervisord -c /srv/supervisor/supervisord.conf


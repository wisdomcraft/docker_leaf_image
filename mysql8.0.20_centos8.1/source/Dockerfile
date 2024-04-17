FROM centos:8.1.1911
MAINTAINER lihuilu<1760908473@qq.com>

ADD mysql.tar /

RUN useradd --no-create-home --shell /sbin/nologin mysql \
    && chown -R mysql:mysql /etc/my.cnf \
    && chmod 444 /etc/my.cnf \
    && chmod 755 /usr/local/mysql/ \
    && chown -R mysql:mysql /usr/local/mysql/data \
    && chmod 755 /usr/local/mysql/data/* \
    && chmod 660 /usr/local/mysql/data/*/* \
    && ln -s /usr/local/mysql/bin/mysql /usr/bin/mysql \
    && ln -s /usr/local/mysql/bin/mysqldump /usr/bin/mysqldump \
    && echo -e "\nexport LANG='C.utf8'\n" >> /etc/profile \
    && source /etc/profile \
    && echo -e "\nsource /etc/profile\n" >> /root/.bashrc \
    && source /root/.bashrc

EXPOSE 3306 33060

CMD /usr/local/mysql/bin/mysqld --pid-file=/usr/local/mysql/data/localhost.pid --user=mysql


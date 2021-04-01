FROM registry.access.redhat.com/ubi8/ubi:8.0

RUN yum --disableplugin=subscription-manager -y module enable php:7.2 && \
    yum --disableplugin=subscription-manager -y install httpd php && \
    yum --disableplugin=subscription-manger clean all

ADD index.php /var/www/html 

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0   /var/run/httpd /var/log/httpd && \
    chmod -R g=u /var/run/httpd /var/log/httpd

USER 1234

EXPOSE 8080

RUN httpd -D FORGROUND

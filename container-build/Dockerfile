# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

LABEL io.openshift.expose-services="8080:http" \
      io.openshift.s2i.scripts-url="image:///usr/libexec/s2i"

RUN sed -i 's/Listen 80/Listen 8080/g' /etc/httpd/conf/httpd.conf

RUN chgrp -R 0   /var/run/httpd /var/log/httpd && \
    chmod -R g=u /var/run/httpd /var/log/httpd

EXPOSE 8080

USER 1001

FROM centos:6
RUN echo "sslverify=false" >> /etc/yum.conf
RUN yum -y update && \
    yum install -y \
        zip \
        wget \
        unzip \
        nc \
        httpd && \
    yum clean all && \
    rm -rf \
        /tmp/* \
        /var/tmp/* \
        /var/www/html/*
COPY httpd.conf /etc/httpd/conf/httpd.conf
RUN apachectl -t && apachectl -k graceful
EXPOSE 80
VOLUME ["/var/log/httpd"]

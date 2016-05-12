FROM centos:6
MAINTAINER Gravitee Team <http://gravitee.io>
RUN echo "sslverify=false" >> /etc/yum.conf
RUN yum -y update && \
    yum install -y \
        wget \
        unzip \
        nc \
        httpd && \
    yum clean all
COPY httpd.conf /etc/httpd/conf/httpd.conf
RUN apachectl -t && apachectl -k graceful
EXPOSE 80
VOLUME ["/var/log/httpd"]

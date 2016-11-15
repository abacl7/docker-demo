FROM centos:7.2.1511

RUN yum install -y httpd

RUN yum update -y

COPY httpd-foreground /usr/local/bin/

EXPOSE 80
CMD ["httpd-foreground"]

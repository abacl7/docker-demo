FROM centos:7.2.1511

MAINTAINER abacl7@github

ARG api_key=YOUR_KEY

RUN yum install -y httpd python git

RUN sed -ri 's/Options Indexes FollowSymLinks/Options Indexes FollowSymLinks ExecCGI/g; \
             s/#AddHandler cgi-script .cgi/AddHandler cgi-script .pl .cgi/g' /etc/httpd/conf/httpd.conf

WORKDIR /tmp

RUN git clone https://github.com/abacl7/library-search.git

RUN mv /tmp/library-search/cgi-bin/*.cgi /var/www/cgi-bin/

RUN chmod +x /var/www/cgi-bin/*.cgi

RUN mv /tmp/library-search/*.html /var/www/html/

RUN mv /tmp/library-search/resource /var/www/html/

RUN sed -ri s/YOUR_API_KEY/$api_key/g /var/www/cgi-bin/search-library.cgi

COPY httpd-foreground /usr/local/bin/

RUN chmod +x /usr/local/bin/httpd-foreground

EXPOSE 80
CMD ["httpd-foreground"]

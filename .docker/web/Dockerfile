FROM httpd:2.4

RUN mkdir -p /var/www/html/web/sites/default/files
WORKDIR /var/www/html

COPY ./.docker/web/httpd.conf /usr/local/apache2/conf/

COPY web /var/www/html/web

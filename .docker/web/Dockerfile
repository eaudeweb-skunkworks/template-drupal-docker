FROM httpd:2.4

WORKDIR /var/www/html

COPY ./.docker/web/httpd.conf /usr/local/apache2/conf/
COPY web /var/www/html/web
RUN mkdir -p /var/www/html/web/sites/default/files && chown daemon:daemon /var/www/html/web/sites/default/files

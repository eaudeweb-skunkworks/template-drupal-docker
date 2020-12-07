FROM cristiroma/nginx-php-fpm:php73

COPY load.environment.php composer.json composer.lock RoboFile.php /usr/share/nginx/html/
COPY config config
COPY web web
# Workaround until https://helpdesk.eaudeweb.ro/issues/9184 is fixed
COPY example.robo.yml robo.yml

RUN composer self-update --2 && composer install && apk add sudo

# Remove post-install useless stuff
RUN rm -rf /root/.composer web/*.txt web/example.gitignore web/modules/README.txt web/themes/README.txt web/profiles/README.txt web/sites/README.txt web/sites/example.settings.local.php web/sites/default/settings.local.php && \
    echo "* * * * * cd /usr/share/nginx/html && sudo -E -u www-data ./vendor/bin/drush core:cron --uri=http://localhost:8080" > /etc/crontabs/root

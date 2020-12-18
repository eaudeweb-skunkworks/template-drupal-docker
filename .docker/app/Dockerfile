FROM cristiroma/nginx-php-fpm:php73

COPY .docker/app/heavy-lifter.conf /etc/nginx/conf.d/snippets/heavy-lifter.conf
COPY load.environment.php composer.json composer.lock RoboFile.php /usr/share/nginx/html/
COPY config config
COPY web web
# Workaround until https://helpdesk.eaudeweb.ro/issues/9184 is fixed
COPY example.robo.yml robo.yml

# We need sudo for CRON, .env for composer errors
RUN composer self-update --2 && composer install && touch .env && apk add sudo

# Remove post-install useless stuff
RUN rm -rf /root/.composer web/*.txt web/example.gitignore web/modules/README.txt web/themes/README.txt web/profiles/README.txt web/sites/README.txt web/sites/example.settings.local.php web/sites/default/settings.local.php

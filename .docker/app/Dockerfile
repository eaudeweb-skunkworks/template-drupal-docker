FROM cristiroma/nginx-php-fpm:php73

COPY .docker/app/heavy-lifter.conf /etc/nginx/conf.d/snippets/heavy-lifter.conf
COPY example.robo.yml robo.yml
COPY load.environment.php composer.json composer.patches.json composer.lock RoboFile.php /usr/share/nginx/html/
COPY config config
COPY drush drush
COPY patches patches
COPY scripts scripts
COPY web web

# We need sudo for CRON, .env for composer errors
RUN composer self-update --2 && composer install && touch .env && apk add sudo

# Remove post-install useless stuff
RUN rm -rf /root/.composer web/*.txt web/example.gitignore web/modules/README.txt web/themes/README.txt web/profiles/README.txt web/sites/README.txt web/sites/example.settings.local.php web/sites/default/settings.local.php

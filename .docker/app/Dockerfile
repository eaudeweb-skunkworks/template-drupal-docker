FROM cristiroma/php-fpm:7.3-latest

RUN rm -rf web/.csslintrc web/.eslintignore web/.eslintrc.json web/.ht.router.php web/*.txt web/example.gitignore web/web.config web/modules/README.txt web/themes/README.txt web/profiles/README.txt web/sites/README.txt web/sites/example.settings.local.php web/sites/example.sites.php

COPY ./.docker/app/www.conf /usr/local/etc/php-fpm.d/www.conf
COPY composer.json composer.json
COPY composer.lock composer.lock
COPY config /var/www/html/config
COPY vendor /var/www/html/vendor
COPY web /var/www/html/web
RUN chown daemon:daemon /var/www/html/web/sites/default/settings.php

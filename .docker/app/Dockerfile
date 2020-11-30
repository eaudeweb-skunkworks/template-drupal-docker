FROM wyveo/nginx-php-fpm:php73

WORKDIR /usr/share/nginx/html

COPY composer.json composer.json
COPY composer.lock composer.lock

COPY web web

RUN rm -rf /root/.composer web/.csslintrc web/.eslintignore web/.eslintrc.json web/.ht.router.php web/*.txt web/example.gitignore web/web.config web/modules/README.txt web/themes/README.txt web/profiles/README.txt web/sites/README.txt web/sites/example.settings.local.php web/sites/example.sites.php


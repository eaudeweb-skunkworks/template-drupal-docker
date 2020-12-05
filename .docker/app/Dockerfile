FROM cristiroma/nginx-php-fpm:php73

COPY composer.json composer.lock /usr/share/nginx/html/
COPY web web
RUN composer self-update --2 && composer install
RUN rm -rf /root/.composer web/.csslintrc web/.eslintignore web/.eslintrc.json web/.ht.router.php web/.htaccess web/*.txt web/example.gitignore web/web.config web/modules/README.txt web/themes/README.txt web/profiles/README.txt web/sites/README.txt web/sites/example.settings.local.php web/sites/example.sites.php

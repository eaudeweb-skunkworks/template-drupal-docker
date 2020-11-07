FROM cristiroma/php-fpm:7.3-latest

ADD composer.json composer.lock ./
RUN composer install --no-dev --prefer-dist --no-interaction
RUN rm -rf web/.csslintrc web/.eslintignore web/.eslintrc.json web/.ht.router.php web/.htaccess web/*.txt web/example.gitignore web/web.config web/modules/README.txt web/themes/README.txt web/profiles/README.txt web/sites/README.txt web/sites/example.settings.local.php web/sites/example.sites.php
COPY web/modules /web/modules
COPY web/themes /web/themes
COPY web/profiles /web/profiles

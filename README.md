# Drupal Docker stack template

## TODO: In no particular order

* Container: Varnish - front-end caching integrated
* Container: CRON
* Container: Postfix mail queuing & processing instead of direct SMTP connection
* Container: Memcached
* Configuration: APCu
* Configuration: Inject git tag/commit, so we can determine which version is running
* Run tests during image building (Drupal-specific tests, web tests etc.)

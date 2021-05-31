FROM composer:2
FROM bash:5
FROM php:7.4-alpine

COPY Build/entrypoint.sh /entrypoint.sh

COPY --from=composer /usr/bin/composer /usr/bin/composer
COPY --from=bash /usr/local/bin/bash /usr/bin/bash

RUN apk update && apk upgrade \
    && apk add bash git libxml2-dev libzip-dev zip unzip curl \
    && rm -rf /var/cache/apk/*

RUN docker-php-ext-install zip

RUN echo -e "Install squizlabs/php_codesniffer" \
    && composer global require squizlabs/php_codesniffer --prefer-dist --no-progress \
    && ln -nfs /root/.composer/vendor/bin/phpcs /usr/bin/phpcs \
    && chmod a+x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]

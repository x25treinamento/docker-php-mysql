FROM php:fpm-alpine

COPY wait-for-it.sh /usr/bin/wait-for-it

RUN chmod +x /usr/bin/wait-for-it

RUN apk --update --no-cache add git autoconf musl icu-libs icu-dev

RUN docker-php-ext-install opcache pdo_mysql mysqli intl
RUN docker-php-ext-enable opcache

#xdebug extensions
# RUN pecl install xdebug
# RUN docker-php-ext-enable xdebug

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN composer global require hirak/prestissimo

WORKDIR /var/www

CMD composer install ; wait-for-it database:3306 -- bin/console doctrine:migrations:migrate ;  php-fpm 

RUN rm -rf /var/cache/apk/*

EXPOSE 9000

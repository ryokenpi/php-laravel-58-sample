FROM php:7.2-fpm-alpine

RUN apk --update add \
    && apk add build-base curl git zip unzip vim \
	&& cd /usr/bin \
	&& curl -sS https://getcomposer.org/installer | php \
	&& ln -s /usr/bin/composer.phar /usr/bin/composer \
	&& apk add libxml2-dev curl-dev $PHPIZE_DEPS \
	&& pecl install xdebug \
	&& docker-php-ext-install pdo_mysql mbstring xml session tokenizer json \
	&& docker-php-ext-enable pdo_mysql mbstring xml session tokenizer json xdebug

FROM php:8.4-fpm

RUN apt-get update \
    && apt-get install -y libpng-dev libonig-dev libxml2-dev zip unzip git curl

RUN docker-php-ext-install pdo_mysql mbstring gd

WORKDIR /var/www/html

COPY . .

RUN curl -sS https://getcomposer.org/installer | php \
    && php composer.phar install

CMD php artisan serve --host=0.0.0.0 --port=8000

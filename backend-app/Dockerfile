FROM php:8.2-cli

WORKDIR /var/www

RUN apt-get update && apt-get install -y \
    git curl zip unzip libpng-dev libonig-dev libxml2-dev libzip-dev \
    && docker-php-ext-install pdo_mysql mbstring bcmath gd zip

COPY --from=composer:2.7 /usr/bin/composer /usr/bin/composer

COPY . .

RUN composer install --no-interaction --prefer-dist \
    && cp .env.example .env \
    && php artisan key:generate \
    && chown -R www-data:www-data storage bootstrap/cache \
    && chmod -R 775 storage bootstrap/cache

CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=8000"]

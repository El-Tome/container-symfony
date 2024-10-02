# Utiliser l'image PHP avec FPM
FROM php:8.2-fpm

# Installer Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Installer des extensions PHP supplémentaires si nécessaire
RUN apt-get update && apt-get install -y \
    zip \
    unzip \
    git \
    && docker-php-ext-install pdo_mysql

# Définir le répertoire de travail
WORKDIR /var/www/html

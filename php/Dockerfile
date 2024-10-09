# Utiliser l'image PHP avec FPM
FROM php:8.2-fpm

# Installer Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Installer des extensions PHP supplémentaires si nécessaire
RUN apt-get update && apt-get install -y \
    zip \
    unzip \
    git \
    libicu-dev \
    libxml2-dev \
    libzip-dev \
    && docker-php-ext-install \
    intl \
    pdo_mysql \
    zip

# Installer Symfony CLI pour la gestion du projet Symfony (optionnel mais utile)
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony*/bin/symfony /usr/local/bin/symfony

# Installer les dépendances de Symfony et initialiser le projet
WORKDIR /var/www/html

# Copier les fichiers de l'application dans le container
COPY . /var/www/html

# Exposer le port utilisé par PHP-FPM
EXPOSE 9000

# Commande par défaut
CMD ["php-fpm"]

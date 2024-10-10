# Use the PHP image with FPM
FROM php:8.2-fpm

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install additional PHP extensions if necessary
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

# Install Symfony CLI (optional but useful)
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony*/bin/symfony /usr/local/bin/symfony

# Set working directory
WORKDIR /var/www/html

# Copy all project files into the container
COPY public/ /var/www/html

# Set proper permissions
RUN chown -R www-data:www-data /var/www/html

# Expose the port used by PHP-FPM
EXPOSE 9000

# Default command
CMD ["php-fpm"]

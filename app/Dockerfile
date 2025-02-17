# Dockerfile para proyectoX
# ProyectoX: Proyecto de prueba para Docker con Laravel

# Imagen base from Docker Hub Apache with PHP
FROM php:8.4-apache
# Workdir
WORKDIR /var/www/html
# User www-data for Apache web app
USER www-data
# Copy files
COPY ./src /var/www/html
# Install dependencies
RUN apt-get update && apt-get install -y \
    libzip-dev \
    zip \
    unzip \
    git \
    curl
# Install PHP extensions
RUN docker-php-ext-install pdo_mysql zip
# Run composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
# Install composer dependencies
RUN composer install
# Change permissions
RUN chown -R www-data:www-data /var/www/html/storage
RUN chown -R www-data:www-data /var/www/html/bootstrap/cache
# Change permissions
RUN chmod -R 775 /var/www/html/storage
RUN chmod -R 775 /var/www/html/bootstrap/cache
# Copy apache configuration file
COPY ./apache.conf /etc/apache2/sites-available/000-default.conf
# Enable Apache mod_rewrite
RUN a2enmod rewrite
# Copy .env file
COPY ./src/.env.example .env
# Generate key
RUN php artisan key:generate
# Expose port 80
EXPOSE 80
# Start Apache
CMD ["apache2-foreground"]



FROM php:7.4-fpm

# Install PDO MySQL extension for database connectivity
RUN docker-php-ext-install pdo pdo_mysql mysqli

# Set working directory
WORKDIR /var/www/html
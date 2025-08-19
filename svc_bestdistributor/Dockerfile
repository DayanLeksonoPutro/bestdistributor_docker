FROM php:7.4-apache

# Install PDO MySQL extension for database connectivity
RUN docker-php-ext-install pdo pdo_mysql mysqli

# Copy the custom Apache configuration file
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf

# Enable the new site configuration and disable the default one
RUN a2ensite 000-default.conf && a2dissite 000-default

# Set correct permissions for Apache
RUN chown -R www-data:www-data /var/www/html

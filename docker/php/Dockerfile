FROM php:8.2-fpm

# Update package manager
RUN apt-get update

# Install required extensions
RUN docker-php-ext-install pdo_mysql

# Install composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Copy the application code to the container
COPY . /var/www/html

# Install Laravel dependencies
RUN cd /var/www/html && composer install --no-dev --prefer-dist --no-scripts --no-progress --no-suggest

# Set working directory
WORKDIR /var/www/html

# Expose port 9000 for FastCGI
EXPOSE 9000

# Run PHP-FPM
CMD ["php-fpm"]

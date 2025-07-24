FROM phpdockerio/php:8.1-fpm

WORKDIR "/application"

# Install PHP extensions and dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    unzip \
    php8.1-gd \
    php8.1-intl \
    php8.1-mysql \
    php8.1-pgsql \
    php8.1-yaml \
    php8.1-xml \
    php8.1-mbstring \
    php8.1-curl \
    php8.1-zip \
    php8.1-bcmath \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install Composer (if not already installed by base image)
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

# Optional: set environment variable for database if needed (can also be set via docker-compose)
# ENV DATABASE_URL="postgres://user:pass@db:5432/dbname"

# Default command
CMD ["php-fpm"]


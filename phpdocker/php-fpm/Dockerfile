FROM phpdockerio/php:8.1-fpm

WORKDIR /application

RUN apt-get update && \
    apt-get -y --no-install-recommends install \
        git \
        curl \
        unzip \
        php8.1-gd \
        php8.1-intl \
        php8.1-mysql \
        php8.1-yaml && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*


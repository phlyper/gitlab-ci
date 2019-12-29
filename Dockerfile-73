from php:7.3-apache

# Install "curl", "libmemcached-dev"
RUN apt-get update && \
    apt-get install -y --no-install-recommends\
    git \
    curl \
    libmemcached-dev \
    libz-dev \
    libpq-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libssl-dev \
    libcrypt-dev
    
# Install the php mcrypt extension
RUN docker-php-ext-install mcrypt

# Install the php pdo_mysql extension
RUN docker-php-ext-install pdo_mysql

# Install the php gd extension
RUN docker-php-ext-configure gd
    docker-php-ext-install gd
    
# Install the php xdebug extension
RUN pecl install xdebug && docker-php-ext-configure xdebug

# Install ZIP
RUN pecl install zip && docker-php-ext-enable zip

# Install composer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /url/local/bin/composer

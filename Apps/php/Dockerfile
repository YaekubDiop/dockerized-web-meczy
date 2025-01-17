FROM php:7.4-apache

# Install system dependencies
RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libonig-dev \
    libzip-dev \
    zip \
    unzip \
    libxml2-dev

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql \
    && docker-php-ext-install gd \
    && docker-php-ext-install mbstring \
    && docker-php-ext-install xml

# Enable Apache modules
RUN a2enmod rewrite

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /var/www/html

# Set permissions
RUN chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html



# Ce Dockerfile configure un environnement PHP 7.4 avec Apache, 
# en y ajoutant plusieurs extensions PHP utiles pour des applications web 
# courantes (comme la gestion des bases de données MySQL, le traitement d'images,
# les chaînes multibytes et le XML). 
# Il active également le module Apache rewrite pour la gestion des URLs, 
# et assure que les permissions sur le répertoire de travail sont correctement définies 
# pour permettre au serveur Apache de fonctionner correctement.
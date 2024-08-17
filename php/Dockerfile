FROM php:7.1-apache-buster
#ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt upgrade -y \
    && apt install -y ca-certificates libc-client-dev libbz2-dev  \
       libcurl4-gnutls-dev libicu-dev libkrb5-dev libldap2-dev libldb-dev \
       libpng-dev libxml2-dev libxslt-dev zlib1g-dev  \
    && rm -r /var/lib/apt/lists/* \
    && docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
    && docker-php-ext-install bz2 calendar curl fileinfo gd gettext intl imap json ldap mbstring mysqli pdo pdo_mysql xml xsl zip \
    && pecl install xdebug-2.9.8 \
    && docker-php-ext-enable xdebug \
    && a2enmod rewrite
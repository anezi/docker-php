# PHP CLI Docker Container
# Base Dockerfile: anezi/php-cli
FROM ubuntu:latest
MAINTAINER Hassan Amouhzi <hassan@anezi.net>

RUN echo "deb http://ppa.launchpad.net/ondrej/php/ubuntu `. /etc/lsb-release && echo $DISTRIB_CODENAME` main" > \
    /etc/apt/sources.list.d/ondrej-ubuntu-php-wily.list \
    && echo "deb-src http://ppa.launchpad.net/ondrej/php/ubuntu `. /etc/lsb-release && echo $DISTRIB_CODENAME` main" >> \
    /etc/apt/sources.list.d/ondrej-ubuntu-php-wily.list \
    && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 14AA40EC0831756756D7F66C4F4EA0AAE5267A6C \
    && echo "deb http://ppa.launchpad.net/maxmind/ppa/ubuntu `. /etc/lsb-release && echo $DISTRIB_CODENAME` main" > \
    /etc/apt/sources.list.d/maxmind.list \
    && echo "deb-src http://ppa.launchpad.net/maxmind/ppa/ubuntu `. /etc/lsb-release && echo $DISTRIB_CODENAME` main" >> \
    /etc/apt/sources.list.d/maxmind.list \
    && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys F44B38CE3DB1BF64B61DBD28DE1997DCDE742AFA

RUN apt-get update && apt-get install -y \
    curl \
    php7.0-dev \
    php7.0-cli \
    php7.0-curl \
    php7.0-intl \
    php7.0-mysql \
    libmaxminddb-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install MaxMind-DB-Reader-php
RUN cd /tmp \
    && curl -sSL https://github.com/maxmind/MaxMind-DB-Reader-php/archive/v1.1.0.tar.gz -o MaxMind-DB-Reader-php.tar.gz \
    && tar zxvf MaxMind-DB-Reader-php.tar.gz \
    && cd MaxMind-DB-Reader-php-1.1.0/ext \
    && phpize \
    && ./configure \
    && make \
    && make install \
    && cd /tmp \
    && rm -rf MaxMind-DB-Reader-php \
    && echo "extension=maxminddb.so" > /etc/php/7.0/mods-available/maxminddb.ini \
    && ln -s /etc/php/mods-available/maxminddb.ini /etc/php/7.0/cli/conf.d/20-maxminddb.ini

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=1.0.0-alpha11

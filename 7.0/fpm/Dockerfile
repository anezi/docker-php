# PHP FPM Docker Container
# Base Dockerfile:  anezi/php-fpm
FROM anezi/php-cli
MAINTAINER Hassan Amouhzi <hassan@anezi.net>

RUN apt-get update && apt-get install -y \
  git \
  php7.0-fpm \
  php-apcu \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

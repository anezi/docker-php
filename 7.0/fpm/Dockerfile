# PHP FPM Docker Container
# Base Dockerfile:  anezi/php-fpm
FROM anezi/php-cli:7.0
MAINTAINER Hassan Amouhzi <hassan@anezi.net>

RUN apt-get update && apt-get install -y \
  php7.0-fpm \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

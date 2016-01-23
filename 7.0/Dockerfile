# PHP 7.0 Docker Container
# Base Dockerfile: anezi/php7.0
FROM ubuntu:latest
MAINTAINER Hassan Amouhzi <hassan@anezi.net>

RUN echo "deb http://ppa.launchpad.net/ondrej/php-7.0/ubuntu `. /etc/lsb-release && echo $DISTRIB_CODENAME` main" > \
  /etc/apt/sources.list.d/ondrej-ubuntu-php-7_0-wily.list && \
  echo "deb-src http://ppa.launchpad.net/ondrej/php-7.0/ubuntu `. /etc/lsb-release && echo $DISTRIB_CODENAME` main" >> \
  /etc/apt/sources.list.d/ondrej-ubuntu-php-7_0-wily.list && \
  apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 14AA40EC0831756756D7F66C4F4EA0AAE5267A6C

RUN apt-get update && apt-get install -y \
  git \
  php7.0-fpm \
  php-apcu \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

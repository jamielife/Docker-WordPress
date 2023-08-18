# WordPress Dockerfile: Create container from official WordPress image, basic customizations.
# docker build -t wordpress_local:wp_custom_1.0 .

FROM wordpress:latest

# APT Update/Upgrade, then install packages we need
RUN apt update && \
    apt upgrade -y && \
    apt autoremove && \
    apt install -y \
    vim \
    mariadb-client

# Replace php.ini
COPY php.ini /usr/local/etc/php

# Remove old php.ini files (wihtout creating new image) 
RUN rm /usr/local/etc/php/php.ini-development && \
    rm /usr/local/etc/php/php.ini-production
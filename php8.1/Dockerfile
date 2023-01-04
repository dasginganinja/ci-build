# syntax=docker/dockerfile:1

# Basic Apache / PHP 8.1 Appserver for lando
FROM devwithlando/php:8.1-apache-4

RUN apt-get update && apt-get install -y build-essential emacs-nox vim nano automake && curl -sL https://deb.nodesource.com/setup_14.x | bash - \
    && apt-get install -y nodejs && rm -r /var/lib/apt/lists/*
# without this, the global install was failing
RUN npm config set user root
# this is to hide warnings about running as root
RUN echo "unsafe-perm = true" >> ~/.npmrc
# Install gulp and emulsify-gulp globally to hopefully take advantage of previous build.
RUN npm install -g gulp@^4.0 gulpjs/gulp-cli

# syntax=docker/dockerfile:1

# Basic Apache / PHP 8.2 Appserver for lando
#FROM --platform=linux/amd64 devwithlando/php:8.4-apache-5
FROM devwithlando/php:8.4-apache-5

RUN apt-get update && apt-get install -y apt-utils build-essential emacs-nox vim nano automake && curl -sL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs && rm -r /var/lib/apt/lists/*
COPY --from=composer:2 /usr/bin/composer /usr/local/bin/composer
# without this, the global install was failing
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
#RUN npm config set user root
# this is to hide warnings about running as root
RUN echo "unsafe-perm = true" >> ~/.npmrc
# Install gulp and emulsify-gulp globally to hopefully take advantage of previous build.
RUN npm install --arch=x64 --target_arch=x64 --target_platform=linux -g gulp@^4.0 gulpjs/gulp-cli

# Basic Apache / PHP 7.0 Appserver for lando
FROM devwithlando/php:7.0-apache-2

RUN apt-get update && apt-get install -y emacs && cat /etc/apt/preferences && curl -sL https://deb.nodesource.com/setup_10.x | bash - \
    && apt-get install -y nodejs build-essential vim nano emacs && rm -r /var/lib/apt/lists/*
# without this, the global install was failing
RUN npm config set user root
# this is to hide warnings about running as root
RUN echo "unsafe-perm = true" >> ~/.npmrc
# Install gulp and emulsify-gulp globally to hopefully take advantage of previous build.
RUN npm install -g gulp@^3.9.1 emulsify-gulp@^4.0.0 gulp-imagemin@5.0.3 gulpjs/gulp-cli
RUN npm install -g gifsicle jpegtran-bin optipng-bin

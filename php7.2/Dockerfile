# Basic Apache / PHP 7.2 Appserver for lando
FROM node:10 as nodejs
FROM devwithlando/php:7.2-apache-2

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - \
    && apt-get install -y nodejs build-essential
RUN npm install gulpjs/gulp-cli -g
RUN echo "unsafe-perm = true" >> ~/.npmrc

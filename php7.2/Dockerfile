# Basic Apache / PHP 7.2 Appserver for lando

FROM devwithlando/php:7.2-apache-2

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    build-essential \
  && rm -rf /var/lib/apt/lists/*
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get update && apt-get install -y --no-install-recommends \
    node-js \
  && rm -rf /var/lib/apt/lists/*
RUN npm install gulpjs/gulp-cli -g
RUN echo "unsafe-perm = true" >> ~/.npmrc

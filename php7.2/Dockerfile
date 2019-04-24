# Basic Apache / PHP 7.2 Appserver for lando
FROM node:10 as nodejs
FROM devwithlando/php:7.2-apache-2

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    build-essential \
  && rm -rf /var/lib/apt/lists/*
COPY --from=nodejs /usr/local/bin/node /usr/local/bin/node
COPY --from=nodejs /usr/local/bin/npm /usr/local/bin/npm
RUN npm install gulpjs/gulp-cli -g
RUN echo "unsafe-perm = true" >> ~/.npmrc

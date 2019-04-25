# Basic Apache / PHP 7.2 Appserver for lando
FROM devwithlando/php:7.2-apache-2

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - \
    && apt-get install -y nodejs build-essential && rm -r /var/lib/apt/lists/*
RUN npm install -g gulpjs/gulp-cli emulsify-gulp@^4.0.0
RUN echo "unsafe-perm = true" >> ~/.npmrc

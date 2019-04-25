# Basic Apache / PHP 7.2 Appserver for lando
FROM devwithlando/php:7.2-apache-2

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - \
    && apt-get install -y nodejs build-essential && rm -r /var/lib/apt/lists/*
#gulpjs/gulp-cli was in this list previously
RUN npm install -g gulp@>=4
RUN npm install -g gulp-imagemin@5.0.3
RUN npm install -g emulsify-gulp@^4.0.0
RUN echo "unsafe-perm = true" >> ~/.npmrc

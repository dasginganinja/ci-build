# Basic Apache / PHP 7.4 Appserver for lando
FROM dasginganinja/ci-build:7.4-apache-2

# Install mysql-server
RUN apt-get update && apt-get install -y mariadb-server && /etc/init.d/mysql start && mysql -e "CREATE DATABASE IF NOT EXISTS drupal; CREATE USER IF NOT EXISTS 'drupal'@'%' IDENTIFIED BY 'drupal'; GRANT ALL PRIVILEGES ON drupal.* TO 'drupal'@'%'; FLUSH PRIVILEGES; " && wget -O drush.phar https://github.com/drush-ops/drush-launcher/releases/latest/download/drush.phar && chmod +x drush.phar && mv drush.phar /usr/local/bin/drush && rm -r /var/lib/apt/lists/*
RUN cp /usr/local/etc/php/php.ini-production /usr/local/etc/php/php.ini && sed -i 's/memory_limit\s*=.*/memory_limit=256M/g' /usr/local/etc/php/php.ini

# Add mysql defaults
ADD .my.cnf /root/
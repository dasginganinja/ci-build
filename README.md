# ci-build
Dockerfile used for CI builds

Base image from devwithlando/php

Tags provided:
* dasginganinja/ci-build:latest
* dasginganinja/ci-build:php8.0-apache-2
* dasginganinja/ci-build:php7.4-apache-2
* dasginganinja/ci-build:php7.3-apache-2
* dasginganinja/ci-build:php7.2-apache-2
* dasginganinja/ci-build:php7.1-apache-2
* dasginganinja/ci-build:php7.0-apache-2

The latest version will always refer to the latest PHP variant.

# Building images locally

To build an image, change into the appropriate folder, i.e. `php7.3` and then run `docker build - < Dockerfile`.

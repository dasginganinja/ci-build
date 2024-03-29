# ci-build
Dockerfile used for CI builds

Base image from devwithlando/php

Tags provided:
* dasginganinja/ci-build:latest
* dasginganinja/ci-build:8.2-apache-4
* dasginganinja/ci-build:8.1-apache-2
* dasginganinja/ci-build:8.0-apache-2
* dasginganinja/ci-build:7.4-apache-2
* dasginganinja/ci-build:7.3-apache-2
* dasginganinja/ci-build:7.2-apache-2
* dasginganinja/ci-build:7.1-apache-2
* dasginganinja/ci-build:7.0-apache-2

The latest version will always refer to the latest PHP variant.

# Building images locally

To build an image, change into the appropriate folder, i.e. `php7.3` and then run `docker image build - < Dockerfile`.

# Building an image for local tagging, testing, and release

1. Change into the directory you want to run things in, i.e. php8.1
    1. `cd php8.2`
2. Build the image. 
    1. Choose the appropriate tag from the list above and use that as the tag in your command
    2. `docker image build -t dasginganinja/ci-build:8.2-apache-4 .`
3. Run the image locally for testing
    1. `docker run -it dasginganinja/ci-build:8.2-apache-4 bash`
4. Push the updated image (ONCE YOU ARE SURE) to Docker Hub
    1. `docker image push dasginganinja/ci-build:8.2-apache-4`

Note: You may need to `docker login` and enter your Docker Hub credentials. :)


# Issues when building

If you run into issues when building, set `buildkit` to `false` in the Docker config. You can edit this from within the Docker Settings panel. Restart afterwards and you can build as you normally would.

# Target Platform :)
In your `~/.zshrc` add the following entry

```export DOCKER_DEFAULT_PLATFORM=linux/amd64```
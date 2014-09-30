# docker-php-nginx (ubuntu based)

## Usage
You can either just pull the image from the docker index using:

    docker pull jmcarbo/docker-php-nginx


Run a container with the new image using:

    docker run -d jmcarbo/docker-php-nginx

If you just

Mount your web app under `/srv/http` using docker's `-v` switch to make the container serve it up. Use `-p 80` to expose the container's port.

A real world example could look like this:

    docker run -d -p 80 -v /vagrant/app:/srv/http -name app jmcarbo/docker-php-nginx


### `nginx.conf`
* One server serving at localhost from /srv/http using php
* Added `daemon off` to enable control by runit
* All comments removed

### `php-fpm.conf`
* Added `daemonize off` to enable control by runit
* Remove unnecessary settings & comments
* Besides: all settings still default

### `php.ini`
* Commented out open_basedir restriction
* Enabled mysql extension

# Drupal 8 Docker Environment

## Install Composer
Install composer on your Mac. See: getcomposer.org.

```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php --install-dir=bin --filename=composer
php -r "unlink('composer-setup.php');"
```


## Install Docker for Mac

 1. Set Up Docker for Mac. Instructions [here] (https://github.com/Atomox/ExampleCode/blob/master/docker.readme.md)


## Checkout Druapl 8 Repo

 1. Checkout alexa-d8 repo inside of an `alexa-d8` folder. (~/Sites/alexa-d8/)
 2. Switch to that folder, then alexa-d8 again, so: `cd alexa-d8/alexa-d8`.
 3. `composer install`.


## Checkout LEMP repo (this one)
 1. Your LEMP repo should live in it's own folder, at the same level as the Drupal 8 repo above. (~/Sites/DockerLEMP/)
 2. Switch to the root of this repository.
  a. From here, your repo should live at: `../alexa-d8`, so: `../alexa-d8/alexa-d8/web` should be the docroot of your Drupal site.
 3. Back in this directory: `docker-compose build` to prepare to bring up your environment.
 4. `docker-compose up -d` will bring up your environment.
 5. `docker-compose ps` to confirm nothing failed. There should be 4 containers, including: `SOLR`, `NGINX`, `MYSQL`, and `PHPFPM`.


## Logging
rysyslog is installed on phpfpm. Start with `service rsyslog start` inside the phpfpm container.

For all logs: `docker-compose logs -f [optinal_container_name]` (tails the logs)
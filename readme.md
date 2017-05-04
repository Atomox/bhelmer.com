# Docker Environment

## Install Docker for Mac

 1. Set Up Docker for Mac. Instructions [here] (https://github.com/Atomox/ExampleCode/blob/master/docker.readme.md)

## Checkout LEMP repo (this one)
 1. Your LEMP repo should live in it's own folder, at the same level as the Drupal 8 repo above. (~/Sites/DockerLEMP/)
 2. Switch to the root of this repository.
  a. From here, your repo should live at: `../alexa-d8`, so: `../alexa-d8/alexa-d8/web` should be the docroot of your Drupal site.
 3. Back in this directory: `docker-compose build` to prepare to bring up your environment.
 4. `docker-compose up -d` will bring up your environment.
 5. `docker-compose ps` to confirm nothing failed. There should be 4 containers, including: `SOLR`, `NGINX`, `MYSQL`, and `PHPFPM`.

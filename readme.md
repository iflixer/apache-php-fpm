

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"




https://stackoverflow.com/questions/59862387/how-to-deploy-php-fpm-on-docker-container-and-apache-nginx-on-localhost-ubuntu


docker build - < Dockerfile-fpm7.4

docker run \
  --user 33:33 \
  --network host \
  --restart always \
  --detach \
  --name sitename-php74-fpm \
  --volume=/path/to/web:/path/to/web \
  --volume=/var/log/php74-sitename:/var/log/php74-sitename \
  sitename-php74-fpm
# Docker-composer for Magento 2
Nginx + PHP-FPM 7.2 + MySQL 5.7

## Quick start
Copy/extract magento2 to `magento` dir  \
`docker-compose up -d`\
Open `http://127.0.0.1:8081` (default opening phpinfo())


### Other
docker-compose up -d
docker-compose up --build -d
docker-compose up build --no-cache
docker-compose exec fpm php -v
docker-compose ps
docker-compose logs -f nginx
docker-compose logs -f mysql
docker-compose down
docker-compose restart
docker-compose exec fpm composer install
docker-compose exec fpm composer dump-autoload -o

docker exec -it nginx /bin/bash
namei -om /var/www/magento/

docker-compose exec fpm php bin/magento setup:di:compile
docker-compose exec fpm php bin/magento module:enable --all
docker-compose exec fpm php bin/magento cache:clean config
docker-compose exec fpm php bin/magento setup:static-content:deploy -f


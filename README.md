docker-compose exec php bash

COMPOSER_MEMORY_LIMIT=-1 composer create-project pimcore/demo-basic pimcore-project

cd pimcore-project

./vendor/bin/pimcore-install --admin-username admin --admin-password admin \
  --mysql-host-socket=db  --mysql-username pimcore  --mysql-password pimcore \
  --mysql-database pimcore  --no-interaction

http://127.0.0.1:8080/admin

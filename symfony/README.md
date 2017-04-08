Here is a docker-compose file with nginx-php5.6-mysql-phpmyadmin enviroment for symfony app

 - localhost:{APP_PORT} - nginx
 - localhost:{PHPMYADMIN_PORT} - phpmyadmin


Structure of project dir should be next:

$PROJECT_DIR/data - for persistent data (db, logs)  
$PROJECT_DIR/src - for app sources


Before bootstrap you have to create .env file with next params:

```
APP_NAME={APP_NAME}
PROJECT_DIR={PROJECT_DIR}

PORT={APP_PORT}
PHPMYADMIN_PORT={PHPMYADMIN_PORT}

DATABASE_ROOT_PASS={DATABASE_ROOT_PASS}
DATABASE_USER={DATABASE_USER}
DATABASE_USER_PASS={DATABASE_USER_PASS}
DATABASE_NAME={DATABASE_NAME}
```

To boostrap you have to run next command

```
docker-compose up -d
```
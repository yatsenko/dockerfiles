Here is a docker-compose file with apache-php5.6-mysql-phpmyadmin enviroment
 
 - localhost:{APP_PORT} - apache+php
 - localhost:{PHPMYADMIN_PORT} - phpmyadmin
 - localhost:{MAILCATCHER_PORT} - mailcatcher

Structure of project dir should be next:

$PROJECT_DIR/data - for persistent data (db, logs)  
$PROJECT_DIR/src - for app sources

Before bootstrap you have to create .env file with next params:

```
APP_NAME={APP_NAME}
PROJECT_DIR={PROJECT_DIR}

APP_PORT={APP_PORT}
PHPMYADMIN_PORT={PHPMYADMIN_PORT}
MAILCATCHER_PORT={MAILCATCHER_PORT}

DB_NAME={DATABASE_NAME}
DB_USER={DATABASE_USER}
DB_ROOT_PASS={DATABASE_ROOT_PASS}
DB_PASS={DATABASE_USER_PASS}
```

To boostrap you have to run next command

```
docker-compose up -d
```
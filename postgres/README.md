Here is a docker-compose file to run postgres

 - localhost:{PORT} - postgres

Before bootstrap you have to create .env file with next params:

```
PORT=5432
DEBUG=false

DATA_DIR={DATA_DIR}

DB_USER={DATABASE_USER}
DB_PASS={DATABASE_USER_PASS}
DB_NAME={DATABASE_NAME}
```

To boostrap you have to run next command

```
docker-compose up -d
```
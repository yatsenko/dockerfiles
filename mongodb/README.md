Here is a docker-compose file to run mongodb

 - localhost:27017 - postgres

Before bootstrap you have to create .env file with next params:

```
DATA_DIR={DATA_DIR}
```

To boostrap you have to run next command

```
docker-compose up -d
```

Run mongodb via cli

```
docker run -d --restart=always -p 27017:27017 -v /var/lib/mongo/data:/data/db --name mongodb mongo
```
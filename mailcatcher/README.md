Run mailcatcher via cli

```
docker run -d --restart=always -p 1080:1080 -p 1025:1025 --name mailcatcher schickling/mailcatcher
```
Here is a docker-compose file to run jenkins

To boostrap you have to run next command

```
docker-compose up -d
```

#### Create new volume container, inheriting from jenkins container
```
docker create -v /var/jenkins_home --restart=always --name jenkins-data jenkinsci/jenkins
```

#### Starting jenkins container, using previously created volume container.
```
docker run -d --restart=always -p 8080:8080 --volumes-from jenkins-data jenkinsci/jenkins --name jenkins --hostname jenkins
```
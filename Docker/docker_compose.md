docker run tanzeel/simple-webapp
docker run mongodb
docker run redis:alpine
docker run ansible

Inside docker-compose.yml
```
services:
     web:
        image: "tanzeel/simple-webapp"
     database:
        image: "mongodb"
     messaging:
        image: "redis:alpine"
     orchestration:
        image: "ansible"

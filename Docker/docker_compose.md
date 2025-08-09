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
```
```
to up and running the docker container"
docker-compose up
```

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/16921c07-8ee1-4216-a677-a0c54300cbba" />

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

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/6b9611cd-d3dc-4cc0-8aca-7cb4864026aa" />


```
docker run -d --name=redis redis
docker run -d --name=db postgres
docker run -d --name=vote -p 5000:80 voting-app
docker run -d --name=result -p 5001:80 result-app
docker run -d --name=worker worker
```
now we need to link the containers using --links
```
docker run -d --name=vote -p 5000:80 --link redis:redis voting-app
docker run -d --name=result -p 5001:80 --link db:db result-app
docker run -d --name=worker --link db:db --link redis:redis worker  #might get deprecated in future for links this way
# Note: db:db =db
```
Creating a docker-compose.yml 
```
redis:
 image: redis
db:
 image: postgres:9.4
vote:
 image: voting-app
 ports:
  - 5000:80
 links:
  -redis
result:
 image: result-app
 ports:
  -5001:80
 links:
  -db
worker:
 image: worker
 links:
  - redis
  - db


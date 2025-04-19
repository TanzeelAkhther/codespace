Run - tag

pull and run latest image (default)
```
docker run redis
```

pull and run the image version you want
```
docker run redis:4.0    #image:tag
```

Run - stdin
```
docker run -i kodekloud/simple-prompt-docker
docker run -it kodekloud/simple-prompt-docker
```

Run - Port Mapping
```
docker run kodekloud/webapp
*Running on https://0.0.0.0:5000/

docker run -p 80:5000 kodekloud/webapp 

#If users want the access the application through port 80 on my Docker Host through -p parameter in the run command
#80 = port of docker host
#5000 = port of docker container
```
Run - Volume mapping

```
docker run -v /opt/datadir:/var/lib/mysql mysql
#specifying the directorcy on the docker host followed by a colon and the directory inside the docker container.
```

Inspect Container
```
docker inspect <container_name>
```

Container Logs
```
docker logs <container_name>
```


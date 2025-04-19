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

check the version along side pulling the image
```
docker run ubuntu cat /etc/*release*
```

There are two ways of access the web, or particular application on the web UI.
One is using the internalIP and two is using by mapping a port to my Docker Host and accessing it using the external IP.

Access the application and store data as well 
```
docker run -p 8080:8080 -v /root/my-jenkins-data:/var/jenkins_home -u root jenkines

#my-jenkins-data- new directory created inside root docker host
#/var/jenkins_home - where container data is located
#-u root :- for user
```

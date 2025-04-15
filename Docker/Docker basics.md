**Docker Commands**

Docker run command is used to run a container from an image
```
docker run nginx
```
Docker ps command list all the containers and some basic informations about them such as container ID, name, images, status, ports, etc
```
docker ps
```
Each container automatically gets a random ID and name created for it by Docker

To see all running containers or not, it will display running as well as previously stopped or exited containers
```
docker ps -a
```
To stop a running container use docker stop command with container ID or container name but it will be present and consume space
```
docker stop silly_samet
```
To remove the container permanently use rm command, output prints the name back
```
docker rm silly_samet
docker rm <container_id or name> # we can remove multiple container by provide the name or id dividing them by a space
```
List images present or available on our Host
```
docker images
```
to remove image that in no longer required use rmi commnad with image name
```
docker rmi nginx
```

Pull - Download an Image (It will also run the container)
```
docker run nginx
```

only pull the image in your host
```
docker pull nginx
```

You can append a command for a container to run accordingly
```
docker run ubuntu sleep 5  #container stops or sleeps after 5 sec
```

Exec - Execute a command
```
docker exec <container_name> cat/etc/hosts    #to list out the contents in hosts file
```

Run - attach and detach
```
docker run -d kodekloud/simple-webapp   #detach the container and run in background

docker attach <container_name or ID>  #to attach the container
```

Run the container and provide a name
```
docker run -d --name webapp nginx:1.14-alpine
```

Remove image with a different tag
```
docker rmi nginx:alpine
```

Remove multiple images at once
```
docker postgres redis mysql nginx:1.14-alpine kodekloud/simple-webapp-mysql kodekloud/simple-webapp
```







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

To see all running containers or not, it will display running as welll as previously stopped or exited containers
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
```
List images present or available on our Host
```
docker images
```
to remove image that in no longer required use rmi commnad with image name
```
docker rmi nginx
```

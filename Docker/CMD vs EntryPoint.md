CMD - which stands for Command that defines the program that will run within the container.

Containers are meant to run a specific task or process such as to host an instance of a web server, or application server..
Once the task is complete, the container exits.

Bash is not really a process like a web server or database server. It is a shell that listens for insput from a terminal if it cannot find the terminal, it exits.

By default, docker does not attach a terminal to a container when it is run

Temporary
```
docker run ubuntu [COMMAND]
ex: docker run ubuntu sleep 5
```
Two types to specify a command for this docker file

FROM Ubuntu
CMD sleep 5

```
CMD command para1           Ex- CMD sleep 5 
CMD ["command","para1"]     Ex- CMD ["sleep","5"]

docker run ubuntu-sleeper sleep 10
```
FOr this docker file we use Entrypoint

FROM Ubuntu
ENTRYPOINT ["sleep"]
Command at startup: sleep 10
```
docker run ubuntu-sleeper 10
```

How to provide a default value use something like this dockerfile in case we do not provide any value during run command

FROM Ubuntu
ENTRYPOINT ["sleep"]

CMD ["5"]
```
docker run ubuntu-sleeper 10
```

Modify the entry point during runtime,say from sleep to an imaginary
```
docker run --entrypoint sleep2.0 ubuntu-sleeper 10

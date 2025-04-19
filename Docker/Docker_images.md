**Dockerfile**
```
Instruction Argument

FROM Ubuntu
RUN apt-get update
RUN apt-get install python

RUN pip install flask
RUN pip install flask-mysql

COPY . /opt/source-code

ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run
```

Build Image
```
docker build .
docker build Dockerfile -t mmusha/my-custom-app

# At the end of the command, we used the "." (dot) symbol which indicates for the current directory,
```

**Layered Architecture**
1. Base Ubuntu Layer
2. Changes in apt packages
3. Changes in pip packages
4. Source code
5. Update Entrypoint with "flask" command

All the layers are cached in case of failure of a particular step, if re-run it will use cache and run from the latest step, so we don't need to build entire image each time.

Before pushing the image to docker you need to login to docker using
```
docker login  #provide your credentials
docker push mmushad/my-simple-web-app
```

**Run an instance of the new image webapp-color:lite and publish port 8080 on the container to 8383 on the host.**
```
docker run -p 8383:8080 webapp-color:lite
```

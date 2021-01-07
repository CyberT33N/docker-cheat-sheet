# Docker Cheat Sheet
Docker Cheat Sheet for the most needed stuff..


<br>
<br>

# Guides
- Docker Containers 101 (https://www.youtube.com/watch?v=eGz9DS-aIeY)
- How to get started - official (https://www.youtube.com/watch?v=iqqDU2crIEQ&feature=youtu.be)




<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# Hub aka Image Registry for Docker Container
- https://hub.docker.com/search?q=&type=image











<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Dockerfile
- This file is used to build your image.

<br>


```bash
# You can use a image from hub or your own one. We start with this image and will build on top of it.
FROM node:12.16.1

# Create a directory and use it as working directory.
WORKDIR /code

# Create environment variable. Those variables will be accessable by any process.
ENV PORT 80

# copy package.json to code folder
COPY package.json /code/package.json

# Run terminal commands
RUN npm install

# Copy everything from local directory (.) to code folder
COPY . /code

# default commands to run, when starting Container
CMD [ "node", "src/server.js" ]
```

<br><br>









<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# .dockerignore
- Same logic like .gitignore
- .dockerignore is to prevent files from being added to the initial build context that is sent to the docker daemon when you do docker build, it doesn't create a global rule for excluding files from being created in all images generated by a Dockerfile.








<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# Install

## Ubuntu
```bash
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
sudo apt update
sudo apt install docker-ce
```













<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# login

## login to official docker
```bash
docker login
```

<br><br>

## login to remote
```bash
docker login urlhere
```














<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# Build (https://docs.docker.com/engine/reference/commandline/build/)
- Build image from Dockerfile
```bash
docker build
```

## tag (https://www.freecodecamp.org/news/an-introduction-to-docker-tags-9b5395636c2a/#:~:text=So%2C%20what%20exactly%20are%20Docker,of%20referring%20to%20your%20image.)
- Docker tags convey useful information about a specific image version/variant
- name:tag
- -t or --tag
```bash
# . <-- means catch docker file from the current directory
docker build -t . namehere

# If you later want to push to remote repo you may use
docker build -t . usernameORDomain/imagename
```


## file
- Tells where the Dockerfile is located. For default it chooses the current path.
- -f or --file
```bash
docker build -f
```
















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# Pull (https://docs.docker.com/engine/reference/commandline/pull/)
```bash
docker pull ubuntu
docker pull debian:jessie
docker pull ubuntu:14.04
docker pull myregistry.local:5000/testing/test-image
```


















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# Tag (https://docs.docker.com/engine/reference/commandline/tag/)
```bash
docker tag imagename tagname
```












<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# Push (https://docs.docker.com/engine/reference/commandline/push/)
- Push image to repo
- When you use docker login to connect to remote repo the command bellow will work aswell
```bash
# push to docker website
docker push username/imagename
```





























<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Start / Stop
- You can see name/id at docker ps -a
```bash
docker start <container-name/ID>
docker stop <container-name/ID>
```
















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Remove

<br><br>

- Remove Docker
```bash
docker rm <container-name/ID>
```
<br><br>

- Remove Image
```bash
docker rmi <container-name/ID/name:tag>
```














<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Run (https://docs-stage.docker.com/engine/reference/commandline/run/)

## Create Docker Container with Ubuntu
```bash
docker run -d -t --name Socket.io-Chat-APP ubuntu
```

<br><br>
## Args
```bash
## Amount of CPU you want to use for this container. In this case two and a half CPU
--cpus 2.5

## Name of the Container - Only [a-zA-Z0-9][a-zA-Z0-9_.-] are allowed.
--name samplename

## Run container in background and print container ID
--detach , -d

## Memory limit. In this case 512 MB
--memory , -m 512m

## Enable unlimited Memory Swap
--memory-swap -1
## Use 2GB Memory Swap
--memory-swap 2048

## Allocate a pseudo-TTY (teletype aka terminal)
--tty , -t

## Username or UID (format: <name|uid>[:<group|gid>])
--user , -u

## Publish a container’s port(s) to the host. In this case first 80 port is from host and second 80 port is from docker container
--publish , -p 80:80
```

















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Stats

## Show hardware resources of container
```bash
docker stats
```
























<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# ps
Show running Container
```bash
# -a or -all means show all containers (default shows just running)
docker ps -a
```

















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Commit

## Create a image of existing container
```bash
docker commit container_id svendowideit/testimage:version3
```


















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Images

## Show existing images
```bash
docker images
```












<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Logs (https://docs.docker.com/engine/reference/commandline/logs/)
- Show logs of your container
```bash
docker logs container_name_here
```

## follow
- follow logs (monitor logs)
- --follow or -f
```bash
docker log -f container_name_here
```















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Exec

## Enter bash of Container
```bash
docker exec -it samplename bash
```

## fix command not found error at clean debian container
```
apt-get update && apt-get -y install sudo
```


<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>



# Exit
Exit container
```bash
exit
```


<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# Compose (Manage multiple container settings)
- What is Docker Compose | How to create docker compose file | How to use Compose (https://www.youtube.com/watch?v=HUpIoF_conA)



<br><br>
## Install
```bash
## Install docker-compose
sudo apt install docker-compose

## Check if install was successfully
docker-compose -v
# docker-compose version
# docker-compose --version
```



<br><br>
## Compose File


#### Third party images
- You must create a file called **docker-compose.yml** anywhere on your server.
```yml
version: '3.7'
services:
 web:
  image: nginx
 database:
  image: redis
```

#### Build from Dockerfile
- If your Image is called docker-test then by using container_name your new image name will be docker-test_web and container name will be web
```yml
version: '2'

services:
  web:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: web
    ports:
      - "8080:80"
```


<br><br>
## Check if **docker-compose.yml** is valid
```bash
docker-compose config
```


<br><br>
## Start
```bash
sudo docker-compose up -d
```

## Shutdown
```bash
sudo docker-compose down
```


<br><br>
## Hub

#### MongoDB
```yml
services:
  mongodb_container:
    image: mongo:latest
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: testpw
    ports:
      - 27017:27017
    volumes:
      - mongodb_data_container:/data/db

volumes:
  mongodb_data_container:
```



<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# Change

## Add new args to existing Container
```bash
# Step 1 - Create image of your container you want to update
docker commit container_id image_name

# Step 2 - Stop old Container
docker stop container_name

# Re-create Container with new args
docker run -p 8080:8080 -td image_name
```





<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# Save (https://docs.docker.com/engine/reference/commandline/save/)

## Save specific image
```bash
sudo docker export image_name/image_id > socket.io-chat-app.tar
```

## Save all images to one tar file:
```bash
docker save $(docker images -q) -o socket.io-chat-app-full.tar
```


<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# FAQ

## How to fix docker: Got permission denied issue

```bash
sudo chmod 666 /var/run/docker.sock
```


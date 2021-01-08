# Docker Cheat Sheet
Docker Cheat Sheet for the most needed stuff..


<br>
<br>

# Guides
- Docker Containers 101 (https://www.youtube.com/watch?v=eGz9DS-aIeY)
- How to get started - official (https://www.youtube.com/watch?v=iqqDU2crIEQ&feature=youtu.be)
- https://docs.docker.com/get-started (Create sample container and modify it)


<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Nice 2 know
- alpine linux is the smallest OS and a lot of images support it! node and so on..


<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# Hub aka Image Registry for Docker Container
- Images are templates for docker container
- Containers are your running images
- https://hub.docker.com/search?q=&type=image











<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Dockerfile
- This file is used to build your image. It will load your config of your Dockerfile and create your image based on this.

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

# version
```bash
docker version
```










<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


# Build (https://docs.docker.com/engine/reference/commandline/build/)
- The docker build command builds Docker images from a Dockerfile and a “context


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
docker build -f location here
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


## Stop all running container
```bash
sudo docker stop $(sudo docker ps -a -q)
```
















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Remove

<br><br>

- Remove container
```bash
sudo docker rm <container-name/ID>
```

- Remove all container
```bash
sudo docker rm --force $(sudo docker ps -a -q)
```


<br><br>


- Remove image
```bash
sudo docker rmi <container-name/ID/name:tag>
```

- Remove all images
```bash
sudo docker rmi --force $(sudo docker ps -a -q)
```













<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Run (https://docs-stage.docker.com/engine/reference/commandline/run/)
- The docker run command first creates a writeable container layer over the specified image, and then starts it using the specified command.

<br><br>

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


# Bind mount a volume. We will use the named volume and mount it to /etc/todos, which will capture all files created at the path.
--volume , -v todo-db:/etc/todos
# -v $(pwd):/app - bind mount the current directory from the host in the container into the /app directory


# Working directory inside the container
--workdir , -w	
```



<br><br>

## Create Docker Container with Ubuntu and allocate pseudo-TTY
```bash
docker run -d --name test -it ubuntu
```


## Run terminal command
```bash
# on alpine use sh cause bash does not exist
docker run -d --name test -it ubuntu bash -c "your command here"
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

# Container

## Show existing images (https://docs.docker.com/engine/reference/commandline/image/)
- Manage containers


















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Image

## Show existing images (https://docs.docker.com/engine/reference/commandline/image/)
- Manage images





<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Images

## Show existing images (https://docs.docker.com/engine/reference/commandline/images/)
```bash
docker images
```



















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Volumes (https://docs.docker.com/storage/volumes/)
- volumes are completely managed by Docker and do not depend on the directory structure and OS of the host machine.

<br>

- Volumes are easier to back up or migrate than bind mounts.
- You can manage volumes using Docker CLI commands or the Docker API.
- Volumes work on both Linux and Windows containers.
- Volumes can be more safely shared among multiple containers.
- Volume drivers let you store volumes on remote hosts or cloud providers, to encrypt the contents of volumes, or to add other functionality.
- New volumes can have their content pre-populated by a container.
- Volumes on Docker Desktop have much higher performance than bind mounts from Mac and Windows hosts.

<br><br>

## Guides https://docs.docker.com/get-started/05_persisting_data/

<br><br>

## create named volume
```bash
docker volume create todo-db
```

<br><br>

## get details about named volume
- The Mountpoint is the actual location on the disk where the data is stored. Note that on most machines, you will need to have root access to access this directory from the host.
```bash
docker volume inspect todo-db
[
    {
        "CreatedAt": "2019-09-26T02:18:36Z",
        "Driver": "local",
        "Labels": {},
        "Mountpoint": "/var/lib/docker/volumes/todo-db/_data",
        "Name": "todo-db",
        "Options": {},
        "Scope": "local"
    }
]
```


















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# bind mounts (https://docs.docker.com/storage/bind-mounts/)
- bind mounts are dependent on the directory structure and OS of the host machine

<br>

- Bind mounts have been around since the early days of Docker. Bind mounts have limited functionality compared to volumes. When you use a bind mount, a file or directory on the host machine is mounted into a container. The file or directory is referenced by its absolute path on the host machine. By contrast, when you use a volume, a new directory is created within Docker’s storage directory on the host machine, and Docker manages that directory’s contents.

- With bind mounts, we control the exact mountpoint on the host. We can use this to persist data, but is often used to provide additional data into containers. When working on an application, we can use a bind mount to mount our source code into the container to let it see code changes, respond, and let us see the changes right away.









<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Logs (https://docs.docker.com/engine/reference/commandline/logs/)
- Show logs of your container
- Only show log of main process
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

# Exec (https://docs-stage.docker.com/engine/reference/commandline/exec/)

## Enter terminal of Container
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

## Build multiple Container
```yml
version: '2'

services:
  web:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: web
    ports:
      - "8080:8080"

  db:
    image: mongo:3.6.1
    container_name: db
    volumes:
      - mongodb:/data/db
      - mongodb_config:/data/configdb
    ports:
      - 27017:27017
    command: mongod

volumes:
  mongodb:
  mongodb_config:
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


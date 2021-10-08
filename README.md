# Docker Cheat Sheet
Docker Cheat Sheet for the most needed stuff..




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



## Docker Compose (https://docs.docker.com/compose/install/)

#### Ubuntu
```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
docker-compose --version
```










<br><br><br><br>



## How to install packages inside of your Container
```bash
apt-get update; apt-get install curl
```









<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>




# GUI

<br><br>

## Windows
- https://hub.docker.com/editions/community/docker-ce-desktop-windows/

<br><br>

## Linux
- https://dockstation.io/
- https://github.com/docker/kitematic/releases




























<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>


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






# Check available versions here: https://www.ubuntuupdates.org/package/google_chrome/stable/main/base/google-chrome-stable
ARG CHROME_VERSION="77.0.3865.120-1"
RUN wget --no-verbose -O /tmp/chrome.deb https://dl.google.com/linux/chrome/deb/pool/main/g/google-chrome-stable/google-chrome-stable_${CHROME_VERSION}_amd64.deb \
  && apt-get install -y /tmp/chrome.deb \
  && rm /tmp/chrome.deb













<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Dockerfile
- This file is used to build your image. It will load your config of your Dockerfile and create your image based on this.

<br>


```Dockerfile
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

## Define variable
```Dockerfile
ARG myvalue=3
RUN echo $myvalue > /test
```




<br><br>

## Copy folder/file from host to docker container
```Dockerfile
ADD ./hostfolder /dockerfolder/
ADD ./sample.txt /dockerfolder/
```







<br><br>

## Install

<br><br>

#### NVM & Node
```Dockerfile
# Install node
ENV NODE_VERSION 14
ENV NVM_DIR /usr/local/nvm
RUN mkdir -p $NVM_DIR && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash && \
    . $NVM_DIR/nvm.sh && \
    nvm alias default $NODE_VERSION && \
    nvm use default && \
    ln -s $NVM_DIR/versions/node/$(nvm run node --version | tail -1)/bin /node_bin
ENV NODE_PATH $NVM_DIR/lib/node_modules
ENV PATH /node_bin:$PATH

RUN node --version && exit
```

<br><br>

#### Java
```Dockerfile
RUN apt-get install -y openjdk-8-jdk && \
    apt-get install -y ant && \
    apt-get clean;
```


<br><br><br><br>



#### Chrome
```Dockerfile
# Install Chrome (WARNING: ALWAYS INSTALLS THE LATEST VERSION => builds not reproducable)
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - && \
    echo "deb http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google.list && \
    apt-get update && \
    apt-get install -y google-chrome-stable && \
    rm -rf /var/lib/apt/lists/*


# ------------------------------------------------------


# Check available versions here: https://www.ubuntuupdates.org/package/google_chrome/stable/main/base/google-chrome-stable
ARG CHROME_VERSION="77.0.3865.120-1"
RUN wget --no-verbose -O /tmp/chrome.deb https://dl.google.com/linux/chrome/deb/pool/main/g/google-chrome-stable/google-chrome-stable_${CHROME_VERSION}_amd64.deb \
  && apt-get install -y /tmp/chrome.deb \
  && rm /tmp/chrome.deb
```

<br><br>


#### Chromium Dependencies without install Chromium
```Dockerfile
RUN apt-get update \
    && apt-get install -y \
        apt-utils \
        ca-certificates \
        fonts-liberation \
        libappindicator3-1 \
        libasound2 \
        libatk-bridge2.0-0 \
        libatk1.0-0 \
        libc6 \
        libcairo2 \
        libcups2 \
        libdbus-1-3 \
        libexpat1 \
        libfontconfig1 \
        libgbm1 \
        libgcc1 \
        libglib2.0-0 \
        libgtk-3-0 \
        libnspr4 \
        libnss3 \
        libpango-1.0-0 \
        libpangocairo-1.0-0 \
        libstdc++6 \
        libx11-6 \
        libx11-xcb1 \
        libxcb1 \
        libxcomposite1 \
        libxcursor1 \
        libxdamage1 \
        libxext6 \
        libxfixes3 \
        libxi6 \
        libxrandr2 \
        libxrender1 \
        libxss1 \
        libxtst6 \
        lsb-release \
        wget \
        xdg-utils \
        libgtk2.0-0 \
        libgtkextra-dev \
        libgconf2-dev \
        libxtst-dev \
        xvfb \
        curl \
        libsm6 \
    && rm -rf /var/lib/apt/lists/*
```



<br><br>

















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Layer Caching (https://docs.docker.com/get-started/09_image_best/#layer-caching)

<br>

Dockerfile:
```bash
# before caching
FROM node:12-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]

# after caching
FROM node:12-alpine
WORKDIR /app
COPY package.json yarn.lock ./
RUN yarn install --production
COPY . .
CMD ["node", "src/index.js"]
```


<br>

.dockerignore:
```bash
node_modules
```















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# .dockerignore (https://docs.docker.com/engine/reference/builder/#dockerignore-file)
- Same logic like .gitignore
- .dockerignore is to prevent files from being added to the initial build context that is sent to the docker daemon when you do docker build, it doesn't create a global rule for excluding files from being created in all images generated by a Dockerfile.

<br><br>

## Dockerizing a Node.js web app (Best way)
- https://nodejs.org/en/docs/guides/nodejs-docker-webapp/
- http://bitjudo.com/blog/2014/03/13/building-efficient-dockerfiles-node-dot-js/
- https://blog.npmjs.org/post/171556855892/introducing-npm-ci-for-faster-more-reliable


<br>

package.json:
```bash
{
  "name": "docker_web_app",
  "version": "1.0.0",
  "description": "Node.js on Docker",
  "author": "First Last <first.last@example.com>",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {
    "express": "^4.16.1"
  }
}
```

<br>

server.js:
```bash
'use strict';

const express = require('express');

// Constants
const PORT = 8080;
const HOST = '0.0.0.0';

// App
const app = express();
app.get('/', (req, res) => {
  res.send('Hello World');
});

app.listen(PORT, HOST);
console.log(`Running on http://${HOST}:${PORT}`);
```

<br>

Dockerfile:
```bash
FROM node:12

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .

# Your app binds to port 8080 so you'll use the EXPOSE instruction to have it mapped by the docker daemon:
EXPOSE 8080

# Define the command to run your app using CMD which defines your runtime.
# Here we will use node server.js to start your server:
CMD [ "node", "server.js" ]
```

<br>

.dockerignore:
```bash
node_modules
npm-debug.log
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
```bash
# . <-- means catch docker file from the current directory
docker build .
```





## tag (https://www.freecodecamp.org/news/an-introduction-to-docker-tags-9b5395636c2a/#:~:text=So%2C%20what%20exactly%20are%20Docker,of%20referring%20to%20your%20image.)
- Docker tags convey useful information about a specific image version/variant
- name:tag
- -t or --tag
```bash
# . <-- means catch docker file from the current directory
docker build . -t namehere

# If you later want to push to remote repo you may use
docker build . -t usernameORDomain/imagename
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


# Scan (https://docs.docker.com/engine/scan/)
- When you have built an image, it is good practice to scan it for security vulnerabilities using the docker scan command. Docker has partnered with Snyk to provide the vulnerability scanning service.
```bash
sudo docker scan getting-started
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
# Amount of CPU you want to use for this container. In this case two and a half CPU
--cpus 2.5

# Name of the Container - Only [a-zA-Z0-9][a-zA-Z0-9_.-] are allowed.
--name samplename

# Run container in background and print container ID
--detach , -d

# Set environment variables
--env , -e

# Memory limit. In this case 512 MB
--memory , -m 512m

# Enable unlimited Memory Swap
--memory-swap -1

# Use 2GB Memory Swap
--memory-swap 2048

# Allocate a pseudo-TTY (teletype aka terminal)
--tty , -t

# Username or UID (format: <name|uid>[:<group|gid>])
--user , -u

# Publish a container’s port(s) to the host. In this case first 80 port is from host and second 80 port is from docker container
--publish , -p 80:80




# Bind mount a volume. We will use the named volume and mount it to /etc/todos, which will capture all files created at the path.
--volume , -v todo-db:/etc/todos

# bind mount the current directory from the host in the container into the /app directory
-v $(pwd):/app

# If volume "todo-mysql-data" was never created before it will be created automatically
-v todo-mysql-data:/var/lib/mysql 




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
```bash
sudo docker container -ls
```


















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Image

## Show existing images (https://docs.docker.com/engine/reference/commandline/image/)
```bash
sudo docker image -ls
```


<br><br>


## Show history of image
- Using the docker image history command, you can see the command that was used to create each layer within an image.
```bash
docker image history getting-started
```


<br><br>


#### Get Dockerfile from Image
```
docker history --no-trunc imageIDhere | tac | tr -s ' ' | cut -d " " -f 5- | sed 's,^/bin/sh -c #(nop) ,,g' | sed 's,^/bin/sh -c,RUN,g' | sed 's, && ,\n  & ,g' | sed 's,\s*[0-9]*[\.]*[0-9]*\s*[kMG]*B\s*$,,g' | head -n -1
```



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

- Using bind mounts is very common for local development setups. The advantage is that the dev machine doesn’t need to have all of the build tools and environments installed. With a single docker run command, the dev environment is pulled and ready to go. We’ll talk about Docker Compose in a future step, as this will help simplify our commands (we’re already getting a lot of flags).


<br><br>


## Create Dev Mode Container
- https://docs.docker.com/get-started/06_bind_mounts/#starting-a-dev-mode-container





























<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Networking (https://docs-stage.docker.com/engine/reference/commandline/network/)
- Manage networks. You can use subcommands to create, inspect, list, remove, prune, connect, and disconnect networks.

<br><br>

## Golden Rules
- **If two containers are on the same network, they can talk to each other. If they aren’t, they can’t.**
- **There are two ways to put a container on a network: 1) Assign it at start or 2) connect an existing container**


<br><br>

## Create network
```bash
sudo docker network create todo-app
```


<br><br>

## Show all network
```bash
sudo docker network ls
```


<br><br>

## Connect two container to same MySQL DB
- https://docs.docker.com/get-started/07_multi_container/
- https://github.com/nicolaka/netshoot
```bash
# run first container with mysql and assign network "todo-app" and create a netowkr-alias called "mysql"
# create a volume called "todo-mysql-data" and set the path to "/var/lib/mysql"
# create environment variables for password
docker run -d \
     --network todo-app --network-alias mysql \
     -v todo-mysql-data:/var/lib/mysql \
     -e MYSQL_ROOT_PASSWORD=secret \
     -e MYSQL_DATABASE=todos \
     mysql:5.7


# run netshoot container with network "todo-app"
docker run -it --network todo-app nicolaka/netshoot


# Inside the container, we’re going to use the dig command, which is a useful DNS tool. We’re going to look up the IP address for the hostname mysql.
dig mysql


# run second container with node.
# setting port outside with 3000 and inside too.
# set workingdir to "app"
# create volume for the current directory from the host in the container into the /app directory
# connect to network "todo-app"
# set environment variables for MySQL Host, User, PW & DB
# run in terminal from container "yarn install && yarn run dev"
docker run -dp 3000:3000 \
   -w /app -v "$(pwd):/app" \
   --network todo-app \
   -e MYSQL_HOST=mysql \
   -e MYSQL_USER=root \
   -e MYSQL_PASSWORD=secret \
   -e MYSQL_DB=todos \
   node:12-alpine \
   sh -c "yarn install && yarn run dev"
```






















<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Logs (https://docs.docker.com/engine/reference/commandline/logs/)
- Show logs of your container
- Only show log of main process
```bash
sudo docker logs container_name_here
```

## follow
- follow logs (monitor logs)
- --follow or -f
```bash
sudo docker logs -f container_name_here
```











<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

# Exec (https://docs-stage.docker.com/engine/reference/commandline/exec/)

## Enter terminal of Container
```bash
# example #1
docker exec -it samplename bash

# example #2
docker exec -it <mysql-container-id> mysql -p
```

<br><br>


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
- You must create a file called **docker-compose.yml** in the root of your project.
- https://docs.docker.com/compose/
- What is Docker Compose | How to create docker compose file | How to use Compose (https://www.youtube.com/watch?v=HUpIoF_conA)


<br><br>

## Install
```bash
# ubuntu
sudo apt install docker-compose

# fedora
sudo dnf install docker-compose
```




<br><br>
## Networking in Compose
- By default Compose sets up a single network for your app. Each container for a service joins the default network and is both reachable by other containers on that network, and discoverable by them at a hostname identical to the container name.
- Your app’s network is given a name based on the “project name”, which is based on the name of the directory it lives in. You can override the project name with either the --project-name flag or the COMPOSE_PROJECT_NAME environment variable.
- For example, suppose your app is in a directory called myapp, and your docker-compose.yml looks like this:
```bash
version: "3.9"
services:
  web:
    build: .
    ports:
      - "8000:8000"
  db:
    image: postgres
    ports:
      - "8001:5432"
```

<br><br>

When you run docker-compose up, the following happens:

- A network called myapp_default is created.
- A container is created using web’s configuration. It joins the network myapp_default under the name web.
- A container is created using db’s configuration. It joins the network myapp_default under the name db.

<br><br>


- Each container can now look up the hostname web or db and get back the appropriate container’s IP address. For example, web’s application code could connect to the URL postgres://db:5432 and start using the Postgres database.

- It is important to note the distinction between HOST_PORT and CONTAINER_PORT. In the above example, for db, the HOST_PORT is 8001 and the container port is 5432 (postgres default). Networked service-to-service communication uses the CONTAINER_PORT. When HOST_PORT is defined, the service is accessible outside the swarm as well.

- Within the web container, your connection string to db would look like postgres://db:5432, and from the host machine, the connection string would look like postgres://{DOCKER_IP}:8001.







<br><br>


## Environment variables in Compose

#### priority used by Compose
- 1. Compose file
- 2. Shell environment variables
- 3. Environment file
- 4. Dockerfile
- 5. Variable is not defined


#### Substitute environment variables in Compose files
- By default, the docker-compose command will look for a file named .env in the directory you run the command. By passing the file as an argument, you can store it anywhere and name it appropriately, for example:
```bash
docker-compose --env-file ./config/.env.dev up 
```


#### The “.env” file
- You can set default values for any environment variables referenced in the Compose file, or used to configure Compose, in an environment file named .env:
```bash
$ cat .env
TAG=v1.5

$ cat docker-compose.yml
version: '3'
services:
  web:
    image: "webapp:${TAG}"
```



#### Set environment variables in containers
- You can set environment variables in a service’s containers with the ‘environment’ key, just like with docker run -e VARIABLE=VALUE ...:
```bash
web:
  environment:
    - DEBUG=1
```


#### Pass environment variables to containers
- You can pass environment variables from your shell straight through to a service’s containers with the ‘environment’ key by not giving them a value, just like with docker run -e VARIABLE ...:
```bash
# The value of the DEBUG variable in the container is taken from the value for the same variable in the shell in which Compose is run.
web:
  environment:
    - DEBUG
```


#### The “env_file” configuration option
- You can pass multiple environment variables from an external file through to a service’s containers with the ‘env_file’ option, just like with docker run --env-file=FILE ...:
```bash
web:
  env_file:
    - web-variables.env
```

#### Set environment variables with ‘docker-compose run’
- Just like with docker run -e, you can set environment variables on a one-off container with docker-compose run -e:
```bash
docker-compose run -e DEBUG=1 web python console.py

# You can also pass a variable through from the shell by not giving it a value:
docker-compose run -e DEBUG web python console.py
```








<br><br>


## Get docker-compose versiondocker-compose
```bash
docker-compose -v
# docker-compose version
# docker-compose --version
```






<br><br>


## Compose File
- https://docs.docker.com/compose/compose-file/ (In the compose file, we’ll start off by defining the schema version. In most cases, it’s best to use the latest supported version.)

<br><br>





## Example
```yml
version: "3.7" // https://docs.docker.com/compose/compose-file/

services:
  app: // container we run
    image: node:12-alpine // image we create container from
    command: sh -c "yarn install && yarn run dev" // terminal command which will be executed. on alpine there is no bash so we use sh
    ports: // define outside and inside port
      - 3000:3000
    working_dir: /app // define working directory inside of container
    volumes: // created volume. In this case current direct will be mapped to the app folder inside of container
      - ./:/app
    environment: // create environment variables
      MYSQL_HOST: mysql
      MYSQL_USER: root
      MYSQL_PASSWORD: secret
      MYSQL_DB: todos
      
  mysql:
    image: mysql:5.7
    volumes:
      - todo-mysql-data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: todos

volumes: // define the volume mapping for all containers
  todo-mysql-data: // set volume called "todo-mysql-data". By simply providing only the volume name, the default options are used. There are many more options available though (https://docs.docker.com/compose/compose-file/#volume-configuration-reference)
```


<br><br>


## Build from Dockerfile
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

# By default, named volumes in your compose file are NOT removed when running docker-compose down. If you want to remove the volumes, you will need to add the --volumes flag.
sudo docker-compose down --volumes
```






<br><br>

## Check logs
```bash
sudo docker-compose logs

# use the follow paramater to monitor the logs of your containers
sudo docker-compose logs -f

# check logs of specific container
sudo docker-compose logs -f containername
```





<br><br>

## list all running containers
```bash
sudo docker-compose ps
```








<br><br>

## Control startup and shutdown order in Compose (https://docs.docker.com/compose/startup-order/)
- You can control the order of service startup and shutdown with the depends_on option. Compose always starts and stops containers in dependency order, where dependencies are determined by depends_on, links, volumes_from, and network_mode: "service:...".
- https://github.com/vishnubob/wait-for-it
```bash
version: "2"
services:
  web:
    build: .
    ports:
      - "80:8000"
    depends_on:
      - "db"
    command: ["./wait-for-it.sh", "db:5432", "--", "python", "app.py"]
  db:
    image: postgres
```






























<br><br>
 _____________________________________________________
 _____________________________________________________

<br><br>

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

# Known Error fixes
- Errors were encountered while processing: docker-ce
  E: Sub-process /usr/bin/dpkg returned an error code (1)
  - You can turn of your VPN. If this is not working try:
  ```javascript
  sudo systemctl restart systemd-networkd.service # (disconnected network)
  sudo apt remove docker-ce # If you hadn't done so before
  sudo apt install docker-ce # Should start docker.service
  sudo systemctl status docker.service  # Verify docker.service is running
  ```























<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>

Hub List

<br><br>

# MongoDB (https://hub.docker.com/_/mongo)

<br><br>

## Hub
```javascript
sudo docker pull mongo
sudo docker run -d -p 1337:27017 --name mongomain -d mongo:latest
# You can now access Mongo DB as example with Compass by using this string: mongodb://localhost:2717
```

<br><br>

## docker-compose
```yml
version: '3.7'
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





























<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>

# FAQ

## How to fix docker: Got permission denied issue
```bash
sudo chmod 666 /var/run/docker.sock
```


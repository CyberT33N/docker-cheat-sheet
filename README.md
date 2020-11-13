# Docker Cheat Sheet
Docker Cheat Sheet for the most needed stuff..


<br>
<br>

# Guides
Docker Containers 101 (https://www.youtube.com/watch?v=eGz9DS-aIeY)



<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>


# Hub (pre-defined container)
- https://hub.docker.com/search?q=&type=image




<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>


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

<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# Pull (https://docs.docker.com/engine/reference/commandline/pull/)
```bash
docker pull ubuntu
docker pull debian:jessie
docker pull ubuntu:14.04
docker pull myregistry.local:5000/testing/test-image
```


<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# Start / Stop
```bash
docker start <container-name/ID>
docker stop <container-name/ID>
```

<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

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


<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# Stats

## Show hardware resources of container
```bash
docker stats
```

<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>


# ps
Show running Container
```bash
docker ps
```


<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# Commit

## Create a image of existing container
```bash
docker commit container_id svendowideit/testimage:version3
```


<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

# Images

## Show existing images
```bash
docker images
```


<br>
<br>


 _____________________________________________________
 _____________________________________________________


<br>
<br>

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
- You must create a file called **docker-compose.yml** anywhere on your server.

```yml
version: '3.7'
services:
 web:
  image: nginx
 database:
  image: redis
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

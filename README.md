# Docker Cheat Sheet
Docker Cheat Sheet for the most needed stuff..

<br><br>_________________________________________________________
_________________________________________________________<br><br>


# Pull
- Download OS from Docker rep
```bash
docker pull ubuntu
```

<br><br>_________________________________________________________
_________________________________________________________<br><br>

# Run

## Create Docker Container with Ubuntu
```bash
docker run -d -t --name Socket.io-Chat-APP ubuntu
```

<br><br>## Args
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
```

<br><br>_________________________________________________________
_________________________________________________________<br><br>


# Ps
Show running Container
```bash
docker ps
```

<br><br>_________________________________________________________
_________________________________________________________<br><br>

# Exec


## Enter bash of Container
```bash
docker exec -it samplename bash
```

## fix command not found error at clean debian container
```
apt-get update && apt-get -y install sudo
```

<br><br>
_________________________________________________________
_________________________________________________________

<br><br>
# Exit
Exit container
```bash
exit
```

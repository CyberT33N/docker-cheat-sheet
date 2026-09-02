# Networking

- [docker network command reference](https://docs.docker.com/engine/reference/commandline/network/)
- Manage networks. You can use subcommands to create, inspect, list, remove, prune, connect, and disconnect networks.

## Golden Rules

- **If two containers are on the same network, they can talk to each other. If they aren't, they can't.**
- **There are two ways to put a container on a network: 1) Assign it at start or 2) connect an existing container**

## CLI

- Create network: [docker network create](../cli/network/create/overview.md)
- Show all networks: [docker network ls](../cli/network/ls/overview.md)

## Connect two container to same MySQL DB

- [Multi-container apps](https://docs.docker.com/get-started/07_multi_container/)
- [netshoot](https://github.com/nicolaka/netshoot)

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


# Inside the container, we're going to use the dig command, which is a useful DNS tool. We're going to look up the IP address for the hostname mysql.
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

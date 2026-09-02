# Environment variables in Compose

## Priority used by Compose

- 1. Compose file
- 2. Shell environment variables
- 3. Environment file
- 4. Dockerfile
- 5. Variable is not defined

## Substitute environment variables in Compose files

- By default, the docker-compose command will look for a file named .env in the directory you run the command. By passing the file as an argument, you can store it anywhere and name it appropriately, for example:

```bash
docker-compose --env-file ./config/.env.dev up 
```

## The ".env" file

- You can set default values for any environment variables referenced in the Compose file, or used to configure Compose, in an environment file named .env:

```text
$ cat .env
TAG=v1.5

$ cat docker-compose.yml
version: '3'
services:
  web:
    image: "webapp:${TAG}"
```

## Set environment variables in containers

- You can set environment variables in a service's containers with the 'environment' key, just like with docker run -e VARIABLE=VALUE ...:

```yaml
web:
  environment:
    - DEBUG=1
```

## Pass environment variables to containers

- You can pass environment variables from your shell straight through to a service's containers with the 'environment' key by not giving them a value, just like with docker run -e VARIABLE ...:

```yaml
# The value of the DEBUG variable in the container is taken from the value for the same variable in the shell in which Compose is run.
web:
  environment:
    - DEBUG
```

## The "env_file" configuration option

- You can pass multiple environment variables from an external file through to a service's containers with the 'env_file' option, just like with docker run --env-file=FILE ...:

```yaml
web:
  env_file:
    - web-variables.env
```

## Set environment variables with 'docker-compose run'

- Just like with docker run -e, you can set environment variables on a one-off container with docker-compose run -e:

```bash
docker-compose run -e DEBUG=1 web python console.py

# You can also pass a variable through from the shell by not giving it a value:
docker-compose run -e DEBUG web python console.py
```

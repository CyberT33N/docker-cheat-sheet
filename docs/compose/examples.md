# Compose Examples

## Example

```yaml
version: "3.7" # https://docs.docker.com/compose/compose-file/

services:
  app: # container we run
    image: node:12-alpine # image we create container from
    command: sh -c "yarn install && yarn run dev" # terminal command which will be executed. on alpine there is no bash so we use sh
    ports: # define outside and inside port
      - 3000:3000
    working_dir: /app # define working directory inside of container
    volumes: # created volume. In this case current direct will be mapped to the app folder inside of container
      - ./:/app
    environment: # create environment variables
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

volumes: # define the volume mapping for all containers
  todo-mysql-data: # set volume called "todo-mysql-data". By simply providing only the volume name, the default options are used. There are many more options available though (https://docs.docker.com/compose/compose-file/#volume-configuration-reference)
```

## Build from Dockerfile

- If your Image is called docker-test then by using container_name your new image name will be docker-test_web and container name will be web

```yaml
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

## Build multiple Container

```yaml
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

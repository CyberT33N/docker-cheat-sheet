# MongoDB

- [MongoDB on Docker Hub](https://hub.docker.com/_/mongo)

## Hub

```bash
sudo docker pull mongo
sudo docker run -d -p 1337:27017 --name mongomain -d mongo:latest

# You can now access Mongo DB as example with Compass by using this string:
# - mongodb://localhost:1337/?readPreference=primary&appname=MongoDB%20Compass&directConnection=true&ssl=false
```

## docker-compose

```yaml
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

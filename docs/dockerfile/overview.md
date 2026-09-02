# Dockerfile

- This file is used to build your image. It will load your config of your Dockerfile and create your image based on this.

```dockerfile
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

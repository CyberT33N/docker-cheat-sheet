# Layer Caching

- [Docker documentation: Layer caching](https://docs.docker.com/get-started/09_image_best/#layer-caching)

Dockerfile:

```dockerfile
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

.dockerignore:

```text
node_modules
```

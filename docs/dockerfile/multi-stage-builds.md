# Multi-Stage Dockerfile

- Includes Nginx and Node 16

```dockerfile
FROM nginx:1.17.8-alpine
FROM node:16.2.0-alpine3.13

ARG HTML_SERVE_DIR=${HTML_SERVE_DIR}

RUN echo "ARG HTML_SERVE_DIR is ${HTML_SERVE_DIR}"

# Copy the built sencha app into the docker image
COPY ${HTML_SERVE_DIR} /usr/share/nginx/html

# Install dependencies
CMD echo "Current file path: " && pwd && npm ci && npm start
```

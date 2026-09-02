# Build Arguments

## Define variable

```dockerfile
ARG myvalue=3
RUN echo $myvalue > /test
```

## Pin a package version via ARG

Check available versions here: [ubuntuupdates.org — google-chrome-stable](https://www.ubuntuupdates.org/package/google_chrome/stable/main/base/google-chrome-stable)

```dockerfile
ARG CHROME_VERSION="77.0.3865.120-1"
RUN wget --no-verbose -O /tmp/chrome.deb https://dl.google.com/linux/chrome/deb/pool/main/g/google-chrome-stable/google-chrome-stable_${CHROME_VERSION}_amd64.deb \
  && apt-get install -y /tmp/chrome.deb \
  && rm /tmp/chrome.deb
```

## Pass environment variable to Dockerfile for --build-arg

```yaml
docker:backend:
  extends: .docker
  stage: stage1
  variables:
    DOCKER_FILE: Dockerfile.nodejs
    NODE_APP_DIR: "test/apple"
```

Dockerfile.nodejs:

```dockerfile
FROM node:16.2.0-alpine3.13

# Sets node env to production, so that npm ci doesn't install the devDependencies
ENV NODE_ENV=production
ARG NODE_APP_DIR=${NODE_APP_DIR}

# Copy the node app and kernel modules etc into the docker image
ADD . /test
WORKDIR /test

# Install the node-app's dependencies
RUN bash ./npm-all.sh ci

# Change the workdirectory to where the node-app is located now
WORKDIR $NODE_APP_DIR

CMD echo "Current file path: " && pwd && npm start
```

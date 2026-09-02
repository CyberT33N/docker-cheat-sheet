# Install Recipes

## NVM & Node

```dockerfile
# Install node
ENV NODE_VERSION 14
ENV NVM_DIR /usr/local/nvm
RUN mkdir -p $NVM_DIR && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash && \
    . $NVM_DIR/nvm.sh && \
    nvm alias default $NODE_VERSION && \
    nvm use default && \
    ln -s $NVM_DIR/versions/node/$(nvm run node --version | tail -1)/bin /node_bin
ENV NODE_PATH $NVM_DIR/lib/node_modules
ENV PATH /node_bin:$PATH

RUN node --version && exit
```

## Java

```dockerfile
RUN apt-get install -y openjdk-8-jdk && \
    apt-get install -y ant && \
    apt-get clean;
```

## Chrome

```dockerfile
# Install Chrome (WARNING: ALWAYS INSTALLS THE LATEST VERSION => builds not reproducable)
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - && \
    echo "deb http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google.list && \
    apt-get update && \
    apt-get install -y google-chrome-stable && \
    rm -rf /var/lib/apt/lists/*


# ------------------------------------------------------


# Check available versions here: https://www.ubuntuupdates.org/package/google_chrome/stable/main/base/google-chrome-stable
ARG CHROME_VERSION="77.0.3865.120-1"
RUN wget --no-verbose -O /tmp/chrome.deb https://dl.google.com/linux/chrome/deb/pool/main/g/google-chrome-stable/google-chrome-stable_${CHROME_VERSION}_amd64.deb \
  && apt-get install -y /tmp/chrome.deb \
  && rm /tmp/chrome.deb
```

## Chromium Dependencies without install Chromium

```dockerfile
RUN apt-get update \
    && apt-get install -y \
        apt-utils \
        ca-certificates \
        fonts-liberation \
        libappindicator3-1 \
        libasound2 \
        libatk-bridge2.0-0 \
        libatk1.0-0 \
        libc6 \
        libcairo2 \
        libcups2 \
        libdbus-1-3 \
        libexpat1 \
        libfontconfig1 \
        libgbm1 \
        libgcc1 \
        libglib2.0-0 \
        libgtk-3-0 \
        libnspr4 \
        libnss3 \
        libpango-1.0-0 \
        libpangocairo-1.0-0 \
        libstdc++6 \
        libx11-6 \
        libx11-xcb1 \
        libxcb1 \
        libxcomposite1 \
        libxcursor1 \
        libxdamage1 \
        libxext6 \
        libxfixes3 \
        libxi6 \
        libxrandr2 \
        libxrender1 \
        libxss1 \
        libxtst6 \
        lsb-release \
        wget \
        xdg-utils \
        libgtk2.0-0 \
        libgtkextra-dev \
        libgconf2-dev \
        libxtst-dev \
        xvfb \
        curl \
        libsm6 \
    && rm -rf /var/lib/apt/lists/*
```

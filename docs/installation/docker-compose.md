# Docker Compose Installation

- [Docker Compose installation](https://docs.docker.com/compose/install/)

## Ubuntu

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
docker-compose --version
```

Install via package manager:

```bash
# ubuntu
sudo apt install docker-compose

# fedora
sudo dnf install docker-compose
```

## Windows

- Download Docker Desktop, it contains docker-compose: [Docker Desktop for Windows](https://docs.docker.com/desktop/setup/install/windows-install/)

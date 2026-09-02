# FAQ

## How to fix docker: Got permission denied issue

```bash
sudo chmod 666 /var/run/docker.sock
```

## Manage Docker as a non-root user

- [Docker documentation: Linux post-installation steps](https://docs.docker.com/engine/install/linux-postinstall/)

```bash
# Create the docker group.
sudo groupadd docker

# Add your user to the docker group.
sudo usermod -aG docker $USER

# Log out and log back in so that your group membership is re-evaluated.
# If testing on a virtual machine, it may be necessary to restart the virtual machine for changes to take effect.

# On a desktop Linux environment such as X Windows, log out of your session completely and then log back in.

# On Linux, you can also run the following command to activate the changes to groups:
newgrp docker 

# Verify that you can run docker commands without sudo.
docker run hello-world

sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R

sudo usermod -aG docker $USER && newgrp docker
```

# Revert publish ports

- If you want to use a service from your host machine. You can use extra_hosts to achieve this.

```yaml
debian:
    image: debian
    container_name: debian
    ports:
        - "8080:8080"
    extra_hosts:
        - "host.docker.internal:host-gateway"
```

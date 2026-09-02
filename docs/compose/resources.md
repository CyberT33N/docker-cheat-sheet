# Resources

- [Compose file reference: resources](https://docs.docker.com/compose/compose-file/compose-file-v3/#resources)
- In this general example, the redis service is constrained to use no more than 50M of memory and 0.50 (50% of a single core) of available processing time (CPU), and has 20M of memory and 0.25 CPU time reserved (as always available to it).

```yaml
version: "3.9"
services:
  redis:
    image: redis:alpine
    deploy:
      resources:
        limits:
          cpus: '0.50'
          memory: 50M
        reservations:
          cpus: '0.25'
          memory: 20M
```

# Control startup and shutdown order in Compose

- [Docker Compose startup order](https://docs.docker.com/compose/startup-order/)
- You can control the order of service startup and shutdown with the depends_on option. Compose always starts and stops containers in dependency order, where dependencies are determined by depends_on, links, volumes_from, and network_mode: "service:...".
- [wait-for-it](https://github.com/vishnubob/wait-for-it)

```yaml
version: "2"
services:
  web:
    build: .
    ports:
      - "80:8000"
    depends_on:
      - "db"
    command: ["./wait-for-it.sh", "db:5432", "--", "python", "app.py"]
  db:
    image: postgres
```

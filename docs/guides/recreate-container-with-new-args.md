# Add new args to existing Container

```bash
# Step 1 - Create image of your container you want to update
docker commit container_id image_name

# Step 2 - Stop old Container
docker stop container_name

# Re-create Container with new args
docker run -p 8080:8080 -td image_name
```

## Related CLI areas

- [docker commit](../../cli/commit/overview.md) — Create a new image from a container's changes
- [docker stop](../../cli/stop/overview.md) — Stop one or more running containers
- [docker run](../../cli/run/overview.md) — Create and run a new container from an image

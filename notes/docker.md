# Docker

## Volumes

A volume is persistent storage managed by Docker. 

Containers are temporary and can be recreated, but volumes are used to keep data outside the container lifecycle.

```yaml
volumes: 
	- uptime-kuma-data:/app/data
```

This means:

```text
Docker volume: uptime-kuma-data
Container path: /app/data
```

The application writes data to `/app/data`, but Docker stores that data in the named volume.
Useful commands:

```bash
docker volume ls
docker volume inspect <volume-name>
```

Remove containers but keep volumes: 
```bash
docker compose down
```

Remove containers and volumes:
```bash
docker compose down -v
```

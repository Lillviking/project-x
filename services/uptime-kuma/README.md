# Uptime Kuma

Uptime Kuma is used to monitor services in my homelab.

## Local URL

http://localhost:3001

## Docker Compose

Start service:
```bash
docker compose up -d
```

Stop service:
```bash
docker compose down
```

Show running containers:
```bash
docker compose ps
```

Show logs:
```bash
docker logs uptime-kuma --tail 50
```

Concepts 
- `image`: the container used to create the service
- `ports`: maps port 3001 on the host to port 3001 in the container
- `volumes`: stores persistent application data outside the container
- `restart`: unless-stopped: restarts the container unless I manually stop it

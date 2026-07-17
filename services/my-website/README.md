# Homelab Dashboard

A small static homelab dashboard served with Nginx in Docker.

## URL

http://localhost:8080

## Start

```bash
docker compose up -d
```

## Stop
```bash
docker compose down
```

## Files
The websites files are stored in
```bash
html/
```
They are mounted into the container at:
```bash
/usr/share/nginx/html
```

## Docker concepts
This service uses Nginx to serve static HTML files.
The port mapping is:
```bash
ports: 
	- "8080:80"
```
This means port `8080`on the host maps to port `80` inside the container.

The HTML directory is mounted as a bind mount:
```bash
volumes: 
	- ./html:/usr/share/nginx/html:ro
```


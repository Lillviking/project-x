# Homelab Dashboard 

A small static website served with Nginx in Docker.

## URL

`http://localhost:8080`

## Start 

```bash
docker compose up -d
```

## Stop

```bash
docker compose down
```

## Files 

The website files are stored in: 
`html/`

They are mounted into the container at:
`/usr/share/nginx/html`

## Docker concepts
This service uses the official Nginx image:
`image: nginx:alpine`

The port mapping is:

```yaml
ports:
  - "8080:80"
```

This means that port `8080`on the host maps to port `80` inside the container.
The HTML directory is mounted as a bind mount:

```yaml
volumes:
  - ./html:/usr/share/nginx/html:ro
```

The `:ro` part means read-only.

# Homelab

Det här är mitt hemmalabb för att lära mig Linux, self-hosting, Docker, containers och serverdrift.

Projektet fungerar som en träningsmiljö inför att senare kunna self-hosta tjänster på riktigt på en egen server hemma. Fokus är att bygga förståelse stegvis genom små praktiska labbar.

## Mål

* Lära mig jobba i Linuxmiljö
* Förstå Docker och Docker Compose
* Köra egna self-hosted tjänster
* Lära mig nätverk, portar, volumes, reverse proxy och HTTPS
* Förstå grundläggande serverdrift
* På sikt förstå observability med Grafana, Prometheus och loggar
* Kunna drifta enklare egna projekt, till exempel Cortex Corner

## Lärandeområden

### Linux

Öva på terminalen, filsystemet, paket, processer, rättigheter och grundläggande serveradministration.

### Docker och Docker Compose

Förstå hur images, containers, ports, volumes, bind mounts och networks fungerar.

### Self-hosting

Köra egna tjänster lokalt först och senare flytta dem till en riktig hemmalabbserver.

### Nätverk

Lära mig hur localhost, LAN, IP-adresser, portar, DNS, reverse proxy och HTTPS hänger ihop.

### Observability

Bygga förståelse för monitoring, metrics, loggar och dashboards med verktyg som Uptime Kuma, Grafana och Prometheus.

## Nuvarande tjänster

| Tjänst      | Beskrivning                                        | URL                   |
| ----------- | -------------------------------------------------- | --------------------- |
| Uptime Kuma | Övervakning av tjänster och ping/HTTP-monitorering | http://localhost:3001 |
| My Website  | Enkel statisk hemsida som körs med Nginx i Docker  | http://localhost:8080 |

## Planerade tjänster

* Homelab-dashboard eller startsida
* Grafana
* Prometheus
* Loki
* En enklare self-hosted version av Cortex Corner
* Notiser via till exempel ntfy, Gotify, Telegram eller SMS-lösning

## Projektstruktur

```text
homelab/
├── README.md
├── notes/
│   ├── linux.md
│   ├── docker.md
│   └── git.md
├── services/
│   ├── uptime-kuma/
│   └── my-website/
└── scripts/
```

## Arbetsflöde

Varje tjänst ligger i en egen mapp under `services/`.

Varje tjänst bör ha:

* `docker-compose.yml`
* `README.md`
* eventuell konfiguration eller appkod

Exempel:

```text
services/
└── my-website/
    ├── README.md
    ├── docker-compose.yml
    └── html/
        └── index.html
```

## Vanliga kommandon

Starta en tjänst:

```bash
docker compose up -d
```

Stoppa en tjänst:

```bash
docker compose down
```

Visa körande containers:

```bash
docker ps
```

Visa Compose-status:

```bash
docker compose ps
```

Visa loggar:

```bash
docker compose logs
```

Visa Git-status:

```bash
git status
```

## Git och commits

Projektet använder Conventional Commits.

Exempel:

```bash
git commit -m "docs: update homelab README"
git commit -m "feat(website): add homelab dashboard"
git commit -m "docs(docker): document bind mounts"
```

## Nästa steg

* Uppdatera `my-website` till en enkel homelab-dashboard
* Lägga till länkar till nuvarande tjänster
* Dokumentera skillnaden mellan named volumes och bind mounts
* Börja utforska container-nätverk
* På sikt flytta tjänster till en riktig hemmalabbserver

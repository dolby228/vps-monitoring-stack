# VPS Monitoring Stack

Monitoring stack based on Prometheus + Grafana, built in Docker Compose.

## Architecture 

node_exporter collects metrics of server -> Prometheus pulls and stores them -> Grafana displays data.

## Components

- **node_exporter** - the main goal is collecting metrics of server, for example: CPU busy percentage, RAM usage or disk space usage.
- **Prometheus** - collecting and keeping data, it works commonly as pull-model.
- **Grafana** - shows all kind of dashboards, site with presets grafana.com/grafana/dashboards/

## Security

Ports linked to 127.0.0.1, that way helps to avoid frauds or bots; access to Grafana occurs through SSH-tunnel; secrets in .env.

## Setup

### Step 1

Copy .env.example to .env with your data

### Step 2

Find your project directory and write this text in command line: `docker compose up -d`

### Step 3

To create or import preset of dashboard, e.x.: id = 1860

### Step 4

To forward SSH-tunnel: `ssh -L 3000:localhost:3000 user@vps.`

## Warning

Prometheus retention limited to 512MB to fit the small VPS disk.

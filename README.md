# docker-wireguard
Docker container for running a Wireguard server with a web UI behind a Traefik reverse-proxy combined with an Authentik service for authentication

This setup assumes that you're already running:
  - A [Traefik](https://github.com/znibb/docker-traefik) reverse-proxy
  - An [Authentik](https://github.com/znibb/docker-authentik) Identity Provider

## 1. Usage
The server exposes: 
  * VPN endpoint on port DOMAIN.COM:51820
  * Web UI at wg.DOMAIN.COM

## 2. Router setup
1. Make sure your router forwards UDP traffic on port 51820 to your server

## 3. Docker setup
1. Initialize config by running init.sh: `./init.sh`
2. Input personal information info `.env`
3. Make sure that Docker network `traefik` exists, `docker network ls`
4. Runu `docker compose up` and check logs

## 4. Installation - linux desktop
1. Download the config file from web UI
2. Use `nmcli connection import type wireguard file NAME.conf` to import the config to Network Manager

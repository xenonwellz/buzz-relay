# buzz-relay

Dokploy deploy bundle for a self-hosted [Buzz](https://github.com/block/buzz) relay at `buzz.obedovabor.me`.

## Stack

- `relay` — `ghcr.io/block/buzz`
- `postgres` — Postgres 17
- `redis` — Redis 7
- `minio` + `minio-init` — S3-compatible media storage

TLS / routing is handled by Dokploy (Traefik). Do not publish host ports.

## Configure in Dokploy

Project: `buzz-relay` → Compose: `buzz`

Set Environment from `.env.example` (generate secrets once). Domain: `buzz.obedovabor.me` → service `relay` port `3000`.

`RELAY_URL` is community identity — do not change after members join.

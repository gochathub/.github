<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="profile/gochathub-wordmark-dark.png">
    <img src="profile/gochathub-wordmark.png" alt="goChatHub" height="128">
  </picture>

  **[Self-hosted chat. Your server, your data, your users.](https://gochathub.com)**
</div>

# goChatHub

goChatHub is a self-hosted chat platform. The backend — `gochathub-server` — ships as a single Go binary on top of PostgreSQL: contract-first REST/OpenAPI, WebSocket fan-out with receipts, typing and presence, push notifications through your own ntfy server, and S3-compatible attachments. No PostgREST, no Redis, no Kafka, no RabbitMQ, no microservices. Your data stays on your server.

- **OpenAPI** — the `api/openapi.yaml` contract is normative; routes and schema are checked against it on every test run
- **WebSockets** — delivery mechanism only; clients reconnect and resynchronize over REST
- **Push** — UnifiedPush (self-hosted ntfy) and Web Push (RFC 8291 encrypted); identifiers only, never message content
- **Attachments** — presigned uploads against S3/MinIO; the server proxies authorization, never file bytes
- **Security** — Argon2id password hashing, hashed token storage, per-visitor rate limiting, SSRF rejection, audit logging

## Projects

| Repository | What it is |
| --- | --- |
| [`gochathub-server`](https://github.com/gochathub/gochathub-server) | Chat backend — single Go binary (API + WebSocket + admin CLI), PostgreSQL |
| [`gochathub-webui`](https://github.com/gochathub/gochathub-webui) | Web client — Vue 3 + Pinia + Tailwind 4 fork of Avian-Template |
| [`gochathub-android-client`](https://github.com/gochathub/gochathub-android-client) | Android client — CometChat UI Kit, UnifiedPush notifications |
| [`gochatinstaller`](https://github.com/gochathub/gochatinstaller) | One command boots the full stack as Docker Compose (Caddy, server, webui, Postgres, MinIO) |

[gochathub.com](https://gochathub.com) — project website.
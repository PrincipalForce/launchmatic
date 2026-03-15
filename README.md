<p align="center">
  <img src="https://app.launchmatic.io/logo.svg" alt="Launchmatic" width="60" />
</p>

<h1 align="center">Launchmatic</h1>

<p align="center">
  <strong>Deploy any app in seconds.</strong><br />
  The fastest way to go from code to live URL.
</p>

<p align="center">
  <a href="https://app.launchmatic.io">Dashboard</a> &middot;
  <a href="https://www.npmjs.com/package/@launchmatic/cli">CLI</a> &middot;
  <a href="#quickstart">Quickstart</a>
</p>

---

## What is Launchmatic?

Launchmatic deploys your apps to Kubernetes with zero configuration. Point it at your code and get a live URL — databases, SSL, custom domains, and autoscaling included.

- **Any framework** — Next.js, React, Express, FastAPI, Django, Go, Rust, Ruby, and more
- **Lightspeed** — describe what you want in plain English, get a deployed app in under a minute
- **Auto-detect** — runtime, build commands, ports, and Dockerfiles are detected automatically
- **Databases** — PostgreSQL and MongoDB provisioned alongside your app
- **Custom domains & SSL** — automatic TLS certificates via Let's Encrypt
- **Autoscaling** — horizontal pod autoscaling out of the box
- **CLI + Dashboard** — deploy from your terminal or the web UI

## Quickstart

### Install the CLI

```bash
npm install -g @launchmatic/cli
```

### Login

```bash
lm login
```

### Initialize & Deploy

```bash
cd your-project
lm init
lm deploy
```

That's it. Your app is live.

### Lightspeed (AI Generation)

```bash
lm c "build a todo app with Next.js and Prisma"
```

Generates the code, creates a repo, builds, and deploys — all in one command.

## Architecture

Launchmatic is built on Kubernetes and runs on any cloud (GCP, AWS, Azure).

| Component | Description |
|-----------|-------------|
| **Web** | Next.js dashboard |
| **API** | Fastify backend |
| **Builder** | Docker image builder (Kaniko) |
| **Deployer** | Kubernetes deployment manager |
| **Proxy** | Ingress & routing layer |
| **CLI** | Terminal interface (`lm`) |

## Links

- [Dashboard](https://app.launchmatic.io)
- [CLI on npm](https://www.npmjs.com/package/@launchmatic/cli)
- [Report an Issue](https://github.com/PrincipalForce/launchmatic/issues)

## License

Copyright 2024-2026 PrincipalForce. All rights reserved.

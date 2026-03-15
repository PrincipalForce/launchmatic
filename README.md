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
  <a href="#quickstart">Quickstart</a> &middot;
  <a href="#lightspeed">Lightspeed</a>
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

This opens your browser to authenticate with GitHub. Your GitHub account is used for both login and repository creation.

### Initialize & Deploy

```bash
cd your-project
lm init
lm deploy
```

`lm init` detects your runtime, framework, build commands, and port automatically. If your project doesn't have a GitHub repo yet, one is created for you (private by default). `lm deploy` builds a Docker image, pushes it to the registry, and deploys to Kubernetes — you get a live URL in about 60 seconds.

## Lightspeed

Lightspeed is Launchmatic's AI-powered app generator. Describe what you want and get a fully deployed application — code generation, GitHub repo, Docker build, and Kubernetes deployment all happen automatically.

### From the CLI

```bash
lm c "build a todo app with Next.js and Prisma"
```

### From the Dashboard

Click **Lightspeed** in the dashboard, type your prompt, and watch it build.

### What happens under the hood

1. **Plan** — AI analyzes your prompt and picks the right framework, database, and architecture
2. **Generate** — complete, working source code is generated for every file (not scaffolding — real code with pinned dependency versions, proper configs, and working imports)
3. **Create repo** — a private GitHub repository is created and all files are committed
4. **Build** — a Docker image is built from the generated code using the appropriate Dockerfile template
5. **Deploy** — the image is deployed to Kubernetes with health checks, SSL, and a public URL

### What you can build

| Prompt | What you get |
|--------|-------------|
| "build a todo app with Next.js and Prisma" | Full-stack Next.js app with PostgreSQL, Prisma ORM, CRUD API routes, and Tailwind UI |
| "create a React dashboard" | React + Vite SPA with routing, served via nginx with proper SPA config |
| "build a REST API with Express and MongoDB" | Express.js API with Mongoose models, Zod validation, and CRUD endpoints |
| "make a landing page for my startup" | Next.js landing page with Hero, Features, and Footer sections |
| "build a Python API with FastAPI" | FastAPI + SQLAlchemy with Pydantic schemas, PostgreSQL, and auto-docs |
| "make a space shooter game" | Single-file HTML5 Canvas game with mobile touch controls and retro styling |

### Auto-Fix

If a build fails, Lightspeed can automatically diagnose the error and push a fix. Failed deployments show a post-mortem report with what went wrong, how to fix it, and a click-to-copy report for debugging.

### Supported Frameworks

Lightspeed has built-in skill templates for:

- **Next.js** (with or without Prisma/PostgreSQL)
- **React + Vite** (SPA with nginx)
- **Express + MongoDB** (REST API)
- **FastAPI + SQLAlchemy** (Python API)
- **Django**, **SvelteKit**, **Astro**, **Go**, **Hono**, **Elysia + Bun**
- **HTML5 Canvas games** (single-file browser games)

Each skill includes complete, tested code patterns — not bullet-point outlines. The AI follows exact working patterns rather than guessing, which means apps deploy successfully on the first try.

## Deploy Your Own Code

Lightspeed is optional. You can deploy any existing project:

```bash
cd my-existing-app
lm init        # detect runtime, create service
lm deploy      # build & deploy
```

Launchmatic auto-detects:

| Runtime | Detection |
|---------|-----------|
| Node.js | `package.json` (Next.js, React, Express, etc.) |
| Python | `requirements.txt`, `pyproject.toml`, `Pipfile` |
| Go | `go.mod` |
| Rust | `Cargo.toml` |
| Ruby | `Gemfile` (Rails, Sinatra, etc.) |
| Bun | `bun.lockb` or `bunfig.toml` |
| Deno | `deno.json` |
| Static | `index.html` (served via nginx) |
| Docker | Uses your `Dockerfile` directly |

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

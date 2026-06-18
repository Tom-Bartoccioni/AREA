# AREA — Action / REAction Automation Platform

> Epitech project — B-DEV-510 (B5, *Application Development*)
> Team project.

A software suite similar to **IFTTT / Zapier**: users connect *Actions* (triggers) from one service to *REActions* from another, and the platform runs these automations automatically. Built as a three-part system around a central application server exposing a REST API.

## Architecture

- **Application server** — holds all the business logic, exposes a REST API, responds to `/about.json` describing available services
- **Web client** — browser UI, forwards requests to the server (no business logic)
- **Mobile client** — Android UI, forwards requests to the server (configurable server address)

The whole suite is orchestrated with **Docker Compose** (`server`, `client_web`, `client_mobile`).

## Core concepts

- **Services** the user subscribes to (e.g. Google, Twitter, Timer, RSS…) via OAuth2 when needed
- **Action** — a condition watched on a service (e.g. *a new email is received*)
- **REAction** — a task executed on a service (e.g. *post a message*)
- **AREA** — an Action wired to a REAction, fired automatically by a **trigger**

## Tech stack

- **Languages:** Node.js / Java / .NET (server), web + mobile clients
- **Auth:** username/password and OAuth2 (third-party services)
- **Orchestration:** Docker Compose
- **API:** REST (documented in the server README)

## Build & run

```sh
docker-compose build && docker-compose up
# server  → http://localhost:8080  (/about.json)
# web app → http://localhost:8081
```

## What I learned

- Designing a client/server architecture with a clear REST API boundary
- Integrating third-party services through OAuth2
- Containerising a multi-service application with Docker Compose
- Working as a team and acting as software architects

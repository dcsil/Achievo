## ADR 011: Backend Deployment Platform — Render

**Date:** 2025-12-01 \
**Status:** Accepted

## Context
We need to deploy a Python Flask backend as a long-running API service that:
- Runs continuously (not serverless execution).
- Supports automatic deployment from GitHub.
- Provides a public HTTPS endpoint by default.
- Allows environment variable and secret management.
- Works with minimal infrastructure overhead.
- Offers a free or low-cost option during early development.

The backend is currently running locally and must be moved to a hosted environment so the frontend can communicate with it via a stable public URL.

## Decision
We will deploy the Flask backend using **Render (Web Service)**.

## Consequences
- **Positive**
  - GitHub-based auto deploy on push.
  - Supports persistent Flask services via gunicorn.
  - Built-in HTTPS and publicly accessible URLs.
  - Simple configuration for environment variables and secrets.
  - No need for manual server setup (no VM, nginx, or process management).
  - Free tier available for development and testing.

- **Negative**
  - Free tier services sleep when inactive, causing cold-start delays.
  - Resource limits on low-cost plans.
  - Platform-specific configuration creates mild vendor lock-in.

- **Neutral**
  - Deployment and runtime logs live in the Render dashboard rather than GitHub.
  - Scaling requires plan upgrades rather than instant elastic scaling.

## Alternatives Considered
- **Option A: AWS EC2 / Azure VM**
  - Traditional virtual machines with full OS control.
  - Rejected due to infrastructure overhead, maintenance complexity, and slower iteration.

- **Option B: Vercel / Netlify**
  - Serverless deployment model.
  - Rejected because Flask does not run as a persistent server; cold starts and execution time limits reduce reliability.

- **Option C: Fly.io**
  - VM-like container hosting with global distribution.
  - Rejected due to Docker requirement and higher setup effort.

## References
- https://render.com/docs/web-services
- https://docs.gunicorn.org/
- https://flask.palletsprojects.com/en/latest/deploying/

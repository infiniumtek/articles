---
title: "How to Deploy an AI App to Production: A Practical Guide"
description: "You built an app with Cursor, Replit, or Lovable — now what? This guide covers hosting, security, CI/CD, and monitoring so you can deploy your AI app to production with confidence."
pubDate: 2025-03-05T00:00:00.000Z
author: "Thomas Franz"
category: "AI & Automation"
tags: ["deploy-ai-app", "production", "hosting", "ci-cd", "monitoring", "vibe-coding"]
draft: false
---

You prompted your way to a working app. The UI looks great, the features work, and your demo gets "wow" reactions. There's just one problem — it only runs on localhost.

Deploying an AI app to production is where most vibe-coded projects stall. The gap between "it works on my machine" and "users can access it at a real URL" is filled with decisions about hosting, security, pipelines, and monitoring that AI coding tools don't handle for you.

This guide breaks down what it actually takes to ship.

---

## Choosing the Right Hosting Platform

Not every app needs the same infrastructure. Your choice depends on what you built, how much traffic you expect, and how much control you want.

### Platform-as-a-Service (PaaS)

**Best for:** MVPs, prototypes, solo founders who want to ship fast.

- **Vercel** — Ideal for Next.js and frontend-heavy apps. Push to GitHub, get a deploy. Free tier is generous.
- **Railway** — Handles full-stack apps with databases, background workers, and cron jobs. Simple pricing, good DX.
- **Render** — Similar to Railway with a broader set of managed services. Good for apps that need a Postgres database out of the box.

PaaS platforms handle TLS certificates, load balancing, and scaling for you. The tradeoff is less control and potentially higher costs at scale.

### Virtual Private Servers (VPS)

**Best for:** Apps that need specific runtimes, GPU access, or custom networking.

- **Hetzner** — Best price-to-performance in Europe. ARM servers are remarkably cheap.
- **DigitalOcean** — Developer-friendly with solid documentation. Droplets start at $4/month.
- **AWS Lightsail** — AWS simplicity without the AWS complexity. Good if you'll eventually grow into full AWS.

A VPS gives you root access and full control. You're responsible for OS updates, firewall rules, and process management — but you also pay a fraction of what managed platforms charge.

### Cloud Providers (IaaS)

**Best for:** Apps with complex architecture, compliance requirements, or enterprise customers.

- **AWS** (ECS, Lambda, EC2) — The everything store. Steep learning curve, unmatched breadth.
- **Google Cloud** (Cloud Run) — Great for containerized apps. Cloud Run is serverless containers done right.
- **Azure** — Strong choice if your customers are already in the Microsoft ecosystem.

Most AI apps don't need full cloud infrastructure on day one. Start simple, migrate when you outgrow it.

---

## Security Basics You Can't Skip

Shipping an insecure app is worse than not shipping at all. These are the non-negotiable items before going live.

### Environment Variables and Secrets

Your API keys, database credentials, and third-party tokens should **never** appear in your source code. Every hosting platform has a way to inject environment variables at runtime — use it.

- Store secrets in your platform's secrets manager (Railway, Vercel, etc.) or use a vault service
- Never commit `.env` files to Git — add `.env` to `.gitignore` immediately
- Rotate API keys regularly, especially if they were ever exposed

### HTTPS Everywhere

Your app must serve over HTTPS. Period. Most PaaS platforms handle TLS automatically. If you're on a VPS, use **Let's Encrypt** with Certbot — it's free and takes five minutes.

### Input Validation

If your app accepts user input (and it probably does), validate and sanitize everything server-side. Client-side validation is a UX feature, not a security feature. Watch for:

- **SQL injection** — Use parameterized queries or an ORM. Never concatenate user input into SQL strings.
- **XSS** — Escape output rendered in HTML. Frameworks like React and Next.js do this by default, but `dangerouslySetInnerHTML` bypasses it.
- **Authentication** — Don't roll your own. Use Auth.js, Clerk, Supabase Auth, or Firebase Auth.

### Rate Limiting

AI apps often call expensive APIs (OpenAI, Anthropic, etc.). Without rate limiting, a single bad actor can drain your API budget in minutes. Add rate limiting at the API layer — libraries like `express-rate-limit` or Cloudflare's WAF make this straightforward.

---

## Setting Up CI/CD

CI/CD (Continuous Integration / Continuous Deployment) means every push to your main branch automatically tests and deploys your app. No more SSH-ing into a server and running `git pull`.

### The Minimum Viable Pipeline

1. **Push code** to GitHub (or GitLab, Bitbucket)
2. **Run tests** automatically — even basic smoke tests catch regressions
3. **Build** the app in a clean environment
4. **Deploy** to your hosting platform

### Tools That Work Well

- **GitHub Actions** — Free for public repos, generous limits for private ones. YAML-based workflows that live in your repo.
- **Vercel / Railway / Render** — All have built-in Git integration. Push to main = deploy. Zero config.
- **Docker** — Containerize your app so it runs identically everywhere. Write a `Dockerfile`, and your deploy target doesn't matter anymore.

### A Practical GitHub Actions Example

```yaml
name: Deploy
on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
      - run: npm ci
      - run: npm test
      - run: npm run build
      # Deploy step depends on your platform
```

The key principle: **if it's not automated, it won't happen consistently.** Set up CI/CD on day one, not after your first production incident.

---

## Monitoring: Know When Things Break

Your app will break in production. The question is whether you find out from your monitoring dashboard or from an angry user on Twitter.

### What to Monitor

- **Uptime** — Is your app responding? Services like UptimeRobot (free) or BetterStack ping your URL and alert you when it's down.
- **Errors** — Capture and aggregate runtime errors. Sentry is the standard — it catches unhandled exceptions, groups them, and shows you the stack trace with source maps.
- **Performance** — Track response times and identify slow endpoints. Vercel Analytics, Datadog, or even simple logging with timestamps.
- **Costs** — Monitor your API spend, especially for AI endpoints. Set billing alerts on OpenAI, Anthropic, and your cloud provider.

### Logging

Structured logging beats `console.log`. Use a library like **Pino** (Node.js) or **structlog** (Python) that outputs JSON logs. When something goes wrong at 2 AM, you'll want to filter logs by request ID, user, or error type — not scroll through thousands of unstructured lines.

### Alerting

Monitoring without alerting is just data collection. Set up notifications for:

- App goes down for more than 60 seconds
- Error rate spikes above baseline
- API costs exceed daily threshold
- Database connection pool is exhausted

---

## The Deployment Checklist

Before you flip the switch to production, walk through this:

- [ ] App builds and runs in a clean environment (not just your laptop)
- [ ] Environment variables are configured on the hosting platform
- [ ] Custom domain is pointed with DNS records (A or CNAME)
- [ ] HTTPS is active and HTTP redirects to HTTPS
- [ ] `.env` and secrets are excluded from the repo
- [ ] CI/CD pipeline runs tests and deploys on push to main
- [ ] Error monitoring is active (Sentry or equivalent)
- [ ] Uptime monitoring is configured
- [ ] Rate limiting is in place for public API endpoints
- [ ] Database has automated backups enabled

---

## You Don't Have to Do This Alone

Deploying an AI app to production involves real infrastructure decisions — and getting them wrong can cost you time, money, and users. If you'd rather hand off the deployment and focus on building your product, that's exactly what we do.

**[Infiniumtek's deployment service](/vibes/)** takes your repo and delivers a live, production-ready app — hosting, domain, SSL, CI/CD, and monitoring included. Flat fee, no surprises.

**[Book a free 15-minute call](/vibes/)** and we'll tell you exactly what your app needs to go live.

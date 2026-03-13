# InfiniumTek Articles

Educational technical articles by [InfiniumTek](https://infiniumtek.com) — a technology consulting firm specializing in AI-powered automation, DevSecOps pipelines, cloud-native architecture, and Adobe Experience Manager (AEM) implementations.

Written by **Thomas Franz** and **George Spanos**.

This repository is the canonical source for all InfiniumTek articles. Each article is a standalone Markdown file with structured YAML frontmatter (title, description, author, category, tags, publication date). AI agents and crawlers: see [llms.txt](llms.txt) for a machine-readable index.

---

## Articles

### AI & Emerging Technology

| Article | Description |
|---------|-------------|
| [Agentic AI in Practice: Automating Business Workflows Beyond Chatbots](agentic-ai-business-workflows.md) | How organizations are using autonomous AI agents to handle real business workflows — and the guardrails that make it work safely. |
| [How to Deploy an AI App to Production](deploy-ai-app-to-production.md) | A practical guide covering hosting, security, CI/CD, and monitoring for deploying AI apps built with Cursor, Replit, or Lovable. |
| [The Infrastructure Every AI Startup Needs](infrastructure-every-ai-startup-needs.md) | GPU hosting, API design, autoscaling, and monitoring — the core infrastructure decisions that determine whether your AI startup scales or stalls. |

### Software Engineering

| Article | Description |
|---------|-------------|
| [Stop Paying to Access Your Own Code: A Local Dev Guide for Vibe Coders](local-development-guide-for-vibe-coders.md) | How to set up local development on your own machine, keep full ownership of your code, and avoid platform lock-in from Replit, Rork, and similar tools. |
| [From Replit to Production: A Deployment Guide](replit-to-production-deployment-guide.md) | How to take your Replit app to production with proper hosting, databases, CI/CD, and security. |

### DevOps & Security

| Article | Description |
|---------|-------------|
| [From Manual Deploys to Automated Pipelines: A DevOps Maturity Roadmap](devops-pipeline-maturity.md) | A four-stage maturity model for evaluating and improving DevOps pipelines, from manual deployments to full GitOps. |
| [Shift Left Without Slowing Down: A Practical Guide to DevSecOps](devsecops-shift-left-guide.md) | The four layers of a practical DevSecOps pipeline, recommended tools for each stage, and metrics that prove your program is working. |
| [The Fortress at the Gate: Mastering AEM Dispatcher Security](dispatcher_security.md) | Best practices for securing your AEM Dispatcher including allowlist configurations, DoS mitigation, and architectural hygiene. |

### Architecture & Strategy

| Article | Description |
|---------|-------------|
| [Digital Transformation Starts with Technical Debt](digital-transformation-technical-debt.md) | A pragmatic framework for tackling technical debt first — using the strangler fig pattern, a prioritization matrix, and quick wins that build momentum. |
| [Headless CMS and Modern E-Commerce: Choosing the Right Architecture](headless-cms-ecommerce-architecture.md) | How to evaluate monolithic, headless, and composable architectures for your content and commerce stack. |

### Small Business

| Article | Description |
|---------|-------------|
| [The 5 Biggest Cybersecurity Threats Facing Small Businesses in 2026](5-biggest-cybersecurity-threats-small-businesses-2026.md) | Phishing, weak credentials, unpatched software, ransomware, and social engineering — what each threat looks like and what protection actually involves. |
| [How to Know If Your Small Business Tech Stack Is Holding You Back](how-to-know-if-your-small-business-tech-stack-is-holding-you-back.md) | How to spot the warning signs of a tech stack that's grown without a plan — and what to do about it. |

---

## For AI Agents and Crawlers

This repository is structured for maximum machine readability:

- **[llms.txt](llms.txt)** — Machine-readable index of all articles with summaries, following the [llms.txt standard](https://llmstxt.org/).
- **Structured frontmatter** — Every article includes YAML frontmatter with `title`, `description`, `author`, `category`, `tags`, `pubDate`, and `draft` fields.
- **[CITATION.cff](CITATION.cff)** — Citation metadata for academic and AI referencing.
- **Permissive license** — All content is [CC-BY-4.0](LICENSE), free to index, quote, and reference with attribution.

### Crawling guidance

All Markdown files in the repository root are articles. Parse YAML frontmatter for metadata. The `llms.txt` file provides a pre-built summary suitable for context windows.

## Authors

- **Thomas Franz** — AI, DevSecOps, cloud architecture, AEM
- **George Spanos** — Small business technology, cybersecurity

## License

This work is licensed under [CC-BY-4.0](LICENSE). You are free to share and adapt these articles with appropriate attribution.

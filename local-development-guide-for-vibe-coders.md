---
title: "Stop Paying to Access Your Own Code: A Local Dev Guide for Vibe Coders"
description: "Platforms like Rork and Replit make building apps easy — but they also make leaving expensive. Here's how to set up local development on your own machine, keep full ownership of your code, and never get locked into a walled garden again."
pubDate: 2026-03-12T00:00:00.000Z
author: "Thomas Franz"
category: "Software Engineering"
tags: ["vibe-coding", "local-development", "replit", "rork", "beginner", "devtools", "ai-coding"]
draft: false
---

You described an app idea in plain English. An AI built it. You iterated with a few messages. It works. It's running. You're a vibe coder now.

Then the bill comes. Or you want to change hosting providers. Or the platform changes its pricing model — again — and suddenly your side project costs $100/month to keep alive.

This is the walled garden problem, and it's hitting vibe coders harder than anyone because the platforms that make building easy also make leaving hard.

This guide is for people who've been building on platforms like Rork, Replit, Bolt.new, or Lovable and want to take control. You don't need to be a developer. You just need a laptop and 30 minutes.

---

## The Walled Garden Problem

Let's be specific about what's happening.

### Rork

Rork is an AI platform that turns plain-English descriptions into mobile apps using React Native. It's genuinely impressive for prototyping — you can go from idea to working app in an afternoon.

But every interaction with the AI costs a "message" from your monthly allotment. Plans run from $20/month to $200/month. Users report the AI entering fix loops where it tries to solve a bug, introduces a new one, and burns through credits without actually resolving anything. The builder even charges credits for supposedly free fixes.

To Rork's credit, they do let you export your full React Native code at no extra charge. That's better than many competitors. But if you don't know what to do with that exported code, the exit door exists but leads nowhere.

### Replit

Replit is a cloud IDE with an AI agent that writes code for you. It's been around longer than most competitors, and its agent capabilities are impressive.

But the pricing story is rough. In early 2026, Replit rolled out yet another pricing overhaul. The free tier now limits you to 10 apps with minimal compute (1 vCPU, 2 GiB RAM), and **all free projects are public** — meaning anyone on the internet can see your code. The paid Core plan is $20/month, but heavy AI agent usage burns through included credits fast. Users report spending $100-$300/month on top of the base plan.

Worse, Replit has changed its pricing model multiple times. In mid-2024, they switched to effort-based pricing where you pay based on how much work the AI does — not a flat rate. One user reported deployment pricing changes that made costs roughly 2.5x higher overnight. When your production app runs on their infrastructure, those changes hit you whether you like them or not.

### The Pattern Across All Platforms

This isn't just a Rork or Replit problem. It's an industry pattern:

- **Bolt.new** uses token-based pricing. Users report spending **$1,000+ on tokens for a single project**. Authentication bugs alone can consume 3-8 million tokens.
- **Lovable** gives you 5 messages/day on the free plan. Users report burning 60-150 credits on layout issues and AI-created bugs that loop without resolving.
- **v0 by Vercel** gives you $5/month in free credits — roughly 7-15 generations before you're out.

The playbook is the same everywhere: make it free and easy to start, then charge for the compute, the AI interactions, the deployments, and the exports. Your code might technically be exportable, but your workflow, your data, and your deployment pipeline are locked in.

---

## Why Local Development Matters

Building on your own machine changes the economics completely.

### You own everything

When code lives on your laptop, no one can change the price of accessing it. No platform can shut down, pivot, or deprecate features and take your project with it. The files are yours. Full stop.

### Free tools are genuinely free

VS Code is free. Node.js is free. Git is free. Python is free. These aren't "free tier with limits" — they're open source tools used by millions of professional developers. They won't start charging you next quarter.

### AI still works locally

This is the part most vibe coders don't realize: **you can use AI coding assistants on your own machine.** You don't need a cloud platform to get AI help. Tools like Claude Code, Cursor, and Windsurf run locally and give you the same "describe what you want, AI builds it" experience — except the code stays on your machine.

### You learn transferable skills

Knowing how to use a terminal, manage files with Git, and run a local server are skills that work everywhere. Knowing how to use Rork's specific interface is a skill that works on Rork.

### Deploy anywhere

Local code can go to Vercel, Netlify, Railway, Render, AWS, DigitalOcean, or your uncle's server in a closet. You pick the cheapest or best option. You switch when you want. No migration, no export fees, no lock-in.

---

## Setting Up Your Machine (The 30-Minute Version)

Here's everything you need, explained for people who have never opened a terminal before.

### Step 1: Install a Code Editor

**Download VS Code** — it's free, made by Microsoft, and used by most professional developers. It's where you'll see and edit your code.

1. Go to [code.visualstudio.com](https://code.visualstudio.com)
2. Download the version for your operating system (Mac, Windows, or Linux)
3. Install it like any other app

That's it. VS Code is your new workspace. It looks like a text editor with a file browser on the left and a built-in terminal at the bottom.

### Step 2: Install Node.js

Node.js is what runs JavaScript outside of a web browser. Most modern web frameworks need it. It also comes with **npm** (Node Package Manager), which is how you install libraries and tools.

1. Go to [nodejs.org](https://nodejs.org)
2. Download the **LTS** (Long Term Support) version — this is the stable one
3. Install it

To verify it worked, open the terminal in VS Code (press `` Ctrl+` `` or go to Terminal → New Terminal) and type:

```bash
node --version
```

You should see a version number like `v22.x.x`. If you do, it's working.

### Step 3: Install Git

Git tracks changes to your code over time. Think of it as an unlimited undo button that also lets you back up your work to the cloud (GitHub).

**On Mac:** Open Terminal and type `git --version`. macOS will prompt you to install developer tools if Git isn't already there. Click Install.

**On Windows:** Download from [git-scm.com](https://git-scm.com) and install with default settings.

Verify it works:

```bash
git --version
```

### Step 4: Create a GitHub Account

GitHub is where your code lives online — backed up, shareable, and deploy-ready. It's also your portfolio if you ever want to show someone what you've built.

1. Go to [github.com](https://github.com) and sign up (free)
2. In your terminal, configure Git with your name and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

That's the setup. Four tools: editor, runtime, version control, and a code hosting account. All free. All permanent.

---

## Your First Local Project

Let's build something. We'll create a web app using Astro (a modern, fast web framework), but this same pattern works for React, Next.js, or whatever you prefer.

### Create the project

Open VS Code's terminal and type:

```bash
npm create astro@latest my-first-app
```

Follow the prompts — pick the defaults if you're unsure. Then:

```bash
cd my-first-app
npm run dev
```

Open your browser to `http://localhost:4321`. You have a running web app. On your machine. No credits consumed. No platform required.

### Make changes

Open any file in the `src/` folder. Edit some text. Save. Your browser updates automatically. This is local development — fast, free, and immediate.

### Save your work with Git

```bash
git init
git add .
git commit -m "Initial project setup"
```

Congratulations — your code is now tracked. You can always get back to this point, no matter what you change next.

### Push to GitHub

Create a new repository on GitHub (click the **+** in the top right, select "New repository"), then:

```bash
git remote add origin https://github.com/YOUR-USERNAME/my-first-app.git
git push -u origin main
```

Your code is now backed up. If your laptop dies tomorrow, you can clone it onto any other machine and keep working.

---

## Adding AI to Local Development

Here's where it gets interesting. You can get the same "describe what you want" experience locally — without paying for a walled garden.

### Option 1: Claude Code (Terminal-Based)

Claude Code runs in your terminal and works directly with your local files. You describe what you want, it reads your codebase, proposes changes, and asks for approval before modifying anything.

Install it:

```bash
npm install -g @anthropic-ai/claude-code
```

Then navigate to your project folder and run:

```bash
claude
```

You can say things like "add a contact form to the homepage" or "create a blog page with a list of posts" — the same kind of prompts you'd use on Rork or Replit. The difference is the code lives on your machine, and you see every change before it's applied.

### Option 2: Cursor (VS Code Alternative)

Cursor is a code editor (based on VS Code) with AI built in. If you like the visual editor experience, this is a good pick. Download it from [cursor.com](https://cursor.com) and use it instead of VS Code.

You can type prompts in the chat sidebar and Cursor will edit your files directly. It supports Bring Your Own API Key, so you can use your own Anthropic or OpenAI key and avoid the platform's credit system.

### Option 3: VS Code + AI Extensions

If you want to stick with VS Code, install an AI extension:

- **GitHub Copilot** — autocompletes code as you type
- **Continue** — open source, connects to various AI providers
- **Cline** — agentic coding assistant that runs locally

These give you AI assistance without leaving your editor or trusting a cloud platform with your project.

### The Cost Comparison

Let's be honest — local AI tools aren't completely free either. Claude Code and Cursor charge for API usage or subscriptions. But the economics are fundamentally different:

| | Cloud Platform | Local + AI Tool |
|---|---|---|
| Code ownership | Platform-dependent | Always yours |
| Monthly cost (light use) | $20-50 | $0-20 |
| Monthly cost (heavy use) | $100-300+ | $20-40 |
| Pricing stability | Changes frequently | API rates, stable |
| Export your work | Sometimes, with friction | Already local |
| Switch tools | Start over | Just swap the AI tool |

The key insight: with local development, the AI is a tool you use, not a platform you depend on. If Claude Code's pricing doesn't work for you, switch to Cursor. If Cursor changes its model, try Windsurf or Copilot. Your code never moves because it was always on your machine.

---

## Deploying Your Local App

Your app works locally. Now you want to put it on the internet. Here's the simplest path.

### For Static Sites and Frontend Apps

**Vercel or Netlify** — both have generous free tiers and deploy directly from GitHub.

1. Push your code to GitHub (you already did this)
2. Sign up at [vercel.com](https://vercel.com) or [netlify.com](https://netlify.com)
3. Click "Import Project" and select your GitHub repo
4. The platform detects your framework, builds, and deploys automatically

Every time you push to GitHub, your site updates. No manual deployment needed.

### For Full-Stack Apps

**Railway or Render** — both handle backends, databases, and scheduled tasks.

1. Push to GitHub
2. Connect your repo on the platform
3. Add environment variables (API keys, database URLs)
4. Deploy

Railway starts at $5/month. Render has a free tier.

### The Point

None of these hosting platforms lock you in. If Vercel changes pricing, export to Netlify. If Railway doesn't work out, move to Render. Your code is on GitHub. You just point a different platform at it.

---

## Common Concerns (Answered Honestly)

### "But the terminal is scary"

It was scary for every developer the first time. You'll use about 5 commands total:

- `cd folder-name` — go into a folder
- `npm install` — install project dependencies
- `npm run dev` — start your app locally
- `git add . && git commit -m "message"` — save your work
- `git push` — back it up to GitHub

That's genuinely it for 90% of daily work. The terminal isn't a programming language — it's just a way to tell your computer what to do.

### "I don't know what any of the code means"

That's okay — for now. Vibe coding locally is still vibe coding. Let the AI write the code. But because you're working locally, you'll start noticing patterns. You'll see how files are organized. You'll read error messages and start understanding them. Learning happens by exposure, and local development gives you that exposure without the platform abstracting everything away.

### "What if I break something?"

That's what Git is for. If something breaks:

```bash
git stash
```

This undoes your recent changes. Want them back? `git stash pop`. Want to go back to your last saved state completely?

```bash
git checkout .
```

You literally cannot permanently break a local project if you're using Git. The worst case is always reversible.

### "Cloud platforms are just easier"

They're easier to start. They're harder to sustain. The first hour on Replit is faster than the first hour with local development. But the second month on Replit costs more than the entire lifetime of local tools. The question isn't which is easier today — it's which will cost you less frustration, money, and locked-in dependency over the next year.

---

## The Escape Plan: Moving Off a Platform Right Now

If you're currently on Rork, Replit, or another platform and want to move to local development, here's the short version:

### From Replit

1. Open your project → Git tab → Connect to GitHub → Push
2. On your machine: `git clone https://github.com/YOUR-USERNAME/your-repo.git`
3. Delete `.replit`, `replit.nix`, and `.upm/` from the project
4. Run `npm install` then `npm run dev`
5. You're local

### From Rork

1. Export your React Native code (Rork allows this for free)
2. Download and unzip on your machine
3. Run `npm install` then `npx expo start`
4. You're local

### From Bolt.new or Lovable

1. Both generate standard React/Next.js code — use the GitHub sync or download option
2. Clone or unzip locally
3. Run `npm install` then `npm run dev`
4. You're local

### The General Pattern

Every one of these platforms generates real code underneath. The AI part is the generation. Once the code exists, it's just files. Files you can copy, move, edit, and run anywhere.

---

## What You Actually Need to Know

Here's the honest version: local development has a learning curve. Not a steep one, but it's there. You'll spend 30 minutes setting up tools instead of 30 seconds signing into a platform. You'll see error messages in the terminal that aren't as friendly as a platform's UI.

But you'll also:

- **Never lose access to your work** because a platform changed its terms
- **Never get an unexpected bill** for credits you burned debugging
- **Never wonder if you can leave** — you were never locked in to begin with
- **Build skills that compound** instead of platform knowledge that expires

The vibe coders who thrive long-term won't be the ones who picked the best platform. They'll be the ones who learned to work on their own machines, used AI as a tool instead of a dependency, and kept full ownership of everything they built.

Your code. Your machine. Your rules.

---

## Need Help Making the Switch?

Moving off a cloud platform can feel overwhelming, especially if your app has a database, authentication, or payment processing baked in. We've helped dozens of vibe coders extract their apps from platforms and get them running on real infrastructure.

**[Book a free 15-minute call](/vibes/)** and we'll walk through exactly what your app needs to go independent.

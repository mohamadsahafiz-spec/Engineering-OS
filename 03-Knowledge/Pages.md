# Cloudflare Pages

# Technology Status

Current Usage

Not Yet Used

Adoption Priority

Future Projects

Learning Priority

## Purpose

This document serves as the Engineering-OS decision guide for Cloudflare Pages.

It focuses on engineering decisions, deployment strategy, operational boundaries, and practical experience rather than reproducing vendor documentation.

---

# Overview

Cloudflare Pages is a static hosting platform optimized for modern frontend applications.

Within Engineering-OS, Pages is responsible for hosting user interfaces while delegating backend processing to Cloudflare Workers.

---

# Primary Responsibilities

Cloudflare Pages should be responsible for:

- Static frontend hosting
- HTML
- CSS
- JavaScript
- React applications
- Asset delivery
- CDN distribution
- Frontend deployment

Pages should not contain backend business logic.

---

# When to Use

Use Pages when:

✓ Hosting static websites

✓ Deploying React applications

✓ Delivering frontend assets globally

✓ Requiring automatic HTTPS

✓ Fast frontend deployment is desired

---

# When NOT to Use

Avoid Pages when:

✗ Building REST APIs

✗ Processing backend business logic

✗ Running scheduled jobs

✗ Accessing databases directly

✗ Performing authentication logic

Those responsibilities belong in Cloudflare Workers.

---

# Best Practices

- Keep frontend and backend separated.
- Deploy only compiled frontend assets.
- Store secrets outside the frontend.
- Use Workers for API communication.
- Version deployments.
- Monitor deployment status.

---

# Common Mistakes

- Treating Pages like a Node.js server.
- Attempting backend processing inside the frontend.
- Hardcoding API endpoints.
- Exposing secrets in client-side code.
- Mixing deployment responsibilities.

---

# Lessons Learned

## Lesson 001

Pages is a frontend platform.

Workers is a backend platform.

Never confuse their responsibilities.

---

## Lesson 002

API failures should be investigated independently of frontend rendering.

Separate frontend debugging from backend debugging.

---

## Lesson 003

Deployments completing successfully do not guarantee backend functionality.

Always verify frontend rendering and API communication independently.

---

# Decision Matrix

Need to deploy a frontend?

→ Pages

Need server-side processing?

→ Workers

Need SQL storage?

→ D1

Need object storage?

→ R2

Need global key/value storage?

→ KV

---

# Related Documents

Cloudflare.md

Workers.md

D1.md

R2.md

KV.md

---

# Revision Policy

This document evolves through practical engineering experience.

Every deployment issue, routing problem, or operational lesson should improve this guide.

Avoid generic platform documentation.

Capture Engineering-OS knowledge.
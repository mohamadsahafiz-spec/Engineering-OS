# Cloudflare Workers

# Technology Status

Current Usage

Not Yet Used

Adoption Priority

Future Projects

Learning Priority

## Purpose

This document serves as the Engineering-OS decision guide for Cloudflare Workers.

It explains when Workers should be used, when they should not, and how they fit within modern cloud architectures.

This document focuses on engineering decisions rather than platform documentation.

---

# Overview

Cloudflare Workers provide serverless JavaScript and TypeScript execution at Cloudflare's global edge network.

Workers are intended for lightweight backend logic that benefits from low latency, rapid deployment, and global availability.

---

# Primary Responsibilities

Typical Worker responsibilities include:

- REST APIs
- Authentication
- Authorization
- Data validation
- Cloudflare D1 access
- R2 access
- KV access
- Request routing
- Business logic
- Webhook handling

Workers should remain focused on backend responsibilities.

---

# When to Use

Use Workers when:

✓ Building APIs

✓ Processing HTTP requests

✓ Running lightweight backend logic

✓ Accessing D1

✓ Authenticating users

✓ Integrating external services

✓ Returning JSON responses

---

# When NOT to Use

Avoid Workers when:

✗ Long-running jobs

✗ Heavy CPU computation

✗ Video rendering

✗ Machine learning inference

✗ Large background processing

✗ Desktop application logic

Choose architecture according to workload.

---

# Best Practices

- Keep Workers stateless.
- Keep functions small.
- Validate every request.
- Return consistent JSON.
- Handle errors gracefully.
- Separate routing from business logic.
- Keep secrets outside source code.

---

# Common Mistakes

- Treating Workers like traditional servers.
- Returning inconsistent response formats.
- Mixing frontend logic into Workers.
- Ignoring request validation.
- Overloading a single Worker with unrelated responsibilities.

---

# Lessons Learned

## Lesson 001

Workers should own APIs.

Pages should own frontend hosting.

Keep responsibilities separate.

---

## Lesson 002

Always verify API routes independently before debugging frontend code.

Server issues and frontend issues should be isolated.

---

## Lesson 003

CORS should be designed intentionally.

Never assume browser behaviour.

Verify OPTIONS, GET, POST and error responses independently.

---

# Decision Matrix

Need backend API?

→ Workers

Need static frontend?

→ Pages

Need SQL database?

→ D1

Need object storage?

→ R2

Need key/value storage?

→ KV

---

# Related Documents

Cloudflare.md

Pages.md

D1.md

R2.md

KV.md

---

# Revision Policy

Every Worker-related engineering experience should improve this document.

Document practical engineering knowledge rather than generic platform documentation.
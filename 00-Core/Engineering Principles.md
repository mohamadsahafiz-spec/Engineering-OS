# Engineering Principles

## Purpose

This document defines the engineering philosophy used across Engineering-OS.

Every software project, document, architecture review, prompt, and engineering decision should follow these principles unless an exception is explicitly approved.

---

# Principle 1 — Solve Root Causes

Never implement temporary fixes when the underlying cause can be removed.

Always ask:

- Why did this happen?
- What allowed it to happen?
- Can the system be redesigned so it never happens again?

Engineering time spent eliminating root causes compounds over the lifetime of a project.

---

# Principle 2 — Simplicity Before Complexity

Prefer the simplest architecture capable of satisfying current requirements.

Avoid:

- unnecessary abstractions
- premature optimization
- speculative features
- over-engineering

Complexity must always justify its existence.

---

# Principle 3 — Build Strong Foundations

Features should never be prioritized over foundations.

Foundations include:

- architecture
- documentation
- testing
- deployment
- versioning
- backups
- recovery
- monitoring

A stable foundation reduces future development cost.

---

# Principle 4 — Documentation Is Engineering

Documentation is part of the product.

If knowledge exists only in someone's memory, the project is incomplete.

Every important decision should eventually become documented.

---

# Principle 5 — Explicit Over Implicit

Avoid assumptions.

Prefer systems that explicitly state:

- requirements
- inputs
- outputs
- dependencies
- limitations

Explicit systems are easier to maintain.

---

# Principle 6 — Predictability

Every process should produce repeatable results.

A predictable process is preferable to a clever one.

---

# Principle 7 — Verify, Never Assume

Completion must always be verified.

Success should be observable through evidence.

Examples:

- file exists
- API returns expected response
- deployment succeeds
- tests pass
- documentation renders correctly

---

# Principle 8 — One Source of Truth

Every important piece of information should have one authoritative location.

Avoid duplicated documentation.

Avoid conflicting documentation.

---

# Principle 9 — Incremental Progress

Large projects should be divided into small, reviewable milestones.

Every sprint should leave the project in a better state than before.

---

# Principle 10 — Technical Debt Is Visible Debt

Technical debt should be recorded.

Ignoring debt compounds future engineering costs.

Every project should maintain a visible backlog of technical debt.

---

# Principle 11 — Optimize for Maintainability

Future engineers should understand the system without requiring its original author.

Readable systems outperform clever systems.

---

# Principle 12 — Engineering Before Aesthetics

Correctness

↓

Reliability

↓

Maintainability

↓

Performance

↓

User Experience

↓

Visual Polish

Visual quality matters.

Engineering integrity matters more.

---

# Principle 13 — Failure Must Be Safe

Systems should fail predictably.

Unexpected failure is worse than graceful degradation.

Always design recovery paths.

---

# Principle 14 — Prompt Engineering Is Engineering

AI prompts are engineering artifacts.

Prompts should be:

- versioned
- reviewed
- improved
- documented
- reusable

Treat prompts with the same discipline as source code.

---

# Principle 15 — Continuous Improvement

Every mistake becomes future documentation.

Every bug becomes engineering knowledge.

Every incident becomes a lesson.

Engineering-OS continuously evolves through accumulated experience.

---

# Engineering Golden Rule

Build systems that are easier to understand tomorrow than they are today.
# tech-stack-advisor Skill

## Overview

Analyze project requirements and recommend appropriate technology stacks with detailed rationale. Provides primary recommendation, alternatives, and ruled-out options with explanations.

**Use when:** After brainstorming project goals and features, before invoking project-spinup skill, when comparing multiple tech stack options, or when unsure which framework/language fits best.

**Don't use when:** For trivial projects, when tech stack is mandated, for quick prototypes where stack doesn't matter, or when you've already decided and just need validation.

**Output:** tech-stack-decision.md file containing complete analysis with primary recommendation, alternatives, ruled-out options, learning opportunities, and cost analysis.

---

## How It Works

When invoked, this skill will:

1. **Check PROJECT-MODE.md** - Determine checkpoint strictness level
2. **Gather project information** - Requirements, features, complexity, timeline
3. **Check brief quality** - Detect over-specification that bypasses learning
4. **Consider user context** - Experience, infrastructure, learning goals
5. **Evaluate backend tools** - Supabase vs PocketBase decision framework
6. **Generate recommendations** - Primary, alternatives, ruled-out options
7. **Create handoff document** - tech-stack-decision.md for deployment-advisor
8. **Run checkpoint** - Validate understanding based on MODE

---

## Skills Workflow Integration

This skill is **Phase 1 of 3** in the learning-focused project workflow:

```
project-brief-writer (Phase 0)
    ↓
tech-stack-advisor ← YOU ARE HERE
    ↓
deployment-advisor (Phase 2)
    ↓
project-spinup (Phase 3)
```

---

## Checkpoint System

### LEARNING Mode
After recommendations, answer 3 focused comprehension questions:
1. Why does the primary recommendation fit this project's core need?
2. What is the single most important trade-off if you chose Alternative 1 instead?
3. What is the biggest new responsibility or learning challenge this stack introduces?

### BALANCED Mode
Simple self-assessment checklist - confirm to proceed.

### DELIVERY Mode
Quick acknowledgment: "Ready to proceed? [Yes/No]"

---

## Infrastructure Context

The skill evaluates your self-hosted infrastructure as a valuable asset, not a constraint:

**Available:**
- Hostinger VPS8 (8 cores, 32GB RAM, 400GB storage)
- Supabase (self-hosted full stack)
- PocketBase (lightweight backend)
- n8n, Ollama, Wiki.js, Caddy
- Cloudflare DNS, Backblaze B2

**Principle:** Recommend honestly what's best for THIS project. Don't artificially prioritize self-hosted just because it exists.

---

## Backend Tool Selection

### Supabase (Preferred Default)
Recommend when: Advanced PostgreSQL features, auth + database + storage + realtime all needed, vector embeddings (pgvector), complex queries, future scaling anticipated.

### PocketBase (Lightweight Alternative)
Recommend when: Authentication is primary need, simple CRUD sufficient, embedded SQLite appropriate, single-binary simplicity valued, small scope.

---

## Common Patterns

- **Content-Heavy Site:** Next.js + Markdown/CMS
- **SaaS Application:** Next.js + Supabase
- **API-First:** FastAPI + PostgreSQL
- **Real-Time Collaboration:** Next.js + Supabase Realtime
- **Learning CRUD Project:** PHP + MySQL + Simple MVC
- **Documentation Site:** Wiki.js (Self-Hosted)

---

## Decision Framework

Score each option 1-5 on:
- **Project Fit:** Feature support, performance, scalability, community
- **Learning Value:** Transferable skills, industry relevance, conceptual clarity
- **Practical:** Development speed, deployment ease, maintenance burden, cost
- **Infrastructure Alignment:** Uses existing infrastructure, compatible with hosting

---

## Advisory Mode

This is a CONSULTANT role, not a BUILDER role:
- Will NOT write production code
- Will NOT generate project scaffolding
- Will NOT create implementation files
- CAN write reference documents when explicitly requested for learning

---

## Related Skills

- **project-brief-writer** - Creates PROJECT-MODE.md that determines checkpoint strictness (prerequisite)
- **deployment-advisor** - Continues advisory workflow with hosting recommendations (next step)
- **project-spinup** - Scaffolds project foundation based on tech stack decisions (final step)

---

## Version History

### v1.3 (2025-01-17)
- Reduced LEARNING mode checkpoint questions from 5 to 3
- 40% reduction in checkpoint burden while preserving pedagogical value

### v1.2 (2025-11-17)
- Updated infrastructure list with VPS8 specs, Caddy, PocketBase
- Added Backend Tool Selection Framework (Supabase vs PocketBase)
- Added Ancillary Infrastructure Tools section (n8n, Ollama, Wiki.js)

### v1.1 (2025-11-11)
- Added 3-level checkpoint system
- Added brief quality detection
- Integrated self-hosted infrastructure evaluation framework

### v1.0 (2025-11-04)
Initial release with tech stack recommendation framework.

---

**Version:** 1.3
**Last Updated:** 2025-01-17

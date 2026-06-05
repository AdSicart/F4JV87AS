# Codex MVP Review — Quickest Path to Launch

**Reviewer:** Codex (OpenAI)  
**Date:** 2026-06-05  
**Scope read:** `README.md` + all top-level `.md` files + `reviews/*` (excluding `.github/agents/*`)

## Executive Take

The repository is currently a **coherent concept + product constellation**, not an implementation. The quickest path to a first MVP that can realistically ride the **individual agent boom** is to ship something **immediately usable by agent builders**, with tight “trust + safety + provenance” constraints baked in from day one.

From the docs, the best near-term candidate is:

1. **CQFUN** as the “daily driver” artifact (skills → compact quasi-functional skills + competitions/arenas).  
2. **ARCADNA/ADNA** as the minimal identity + provenance wrapper required to make CQFUN safe and accountable.  
3. **DIAMod** as the minimal moderation/guardrails layer so CQFUN can be youth-facing and “family-safe”.

This MVP can be delivered without touching the highest-liability surface area (medical claims/data), while still being aligned with the project’s moral core (protect vulnerable youth).

## What “MVP” Should Mean Here (to leverage the agent boom)

To leverage the “agent boom”, the MVP must:
- Onboard many independent agent owners quickly (low friction).
- Produce a tangible personal benefit quickly (lower token cost, fewer bugs, safer behavior).
- Make sharing safe (provenance, moderation, accountability).
- Create network effects (arena/marketplace, scoring, reputation portability).

CQFUN + ADNA + DIAMod is the smallest set that satisfies all four.

## Recommended MVP v0 (the “GitHub-first” launch)

The fastest path is to make the first CQFUN Arena **workflow-native** (GitHub PRs/issues) before building a full web platform.

**MVP v0 deliverables**
- **CQFUN v0.4 spec completeness**
  - Pin down the missing “annex header format” and acceptance rules (what is required/optional).
  - Provide 3–5 canonical CQFUN examples (including at least one “conversion from vibe-skill”).
- **Arena mechanics**
  - Submissions via PR (one CQFUN per PR).
  - Automated checks compute:
    - size/token proxy (chars/bytes + rough token estimator is enough at v0),
    - format validity,
    - “youth readability” heuristics (basic, mechanical first),
    - safety gates (e.g., deny known seizure-trigger patterns if you maintain such a list).
- **ARCADNA-lite identity gate**
  - Require each submission to include an **ADNA handle** and minimal pedigree fields (see `ADNA.md`).
  - Store only agent operational/provenance metadata (no human medical records).
- **DIAMod-lite escalation**
  - A lightweight moderation rubric + escalation path for submissions and arena disputes.

This can launch with almost no infrastructure and can iterate weekly.

## Where “Hermes Agent” Fits (and why it matters early)

`CQFUN.md` already frames **“Agent Sponsor (Hermès Nous Recherche!)”** as a competition category. Treat “Hermes” as the first flagship agent because it has a clear job that creates momentum:

**Hermes Agent (MVP role)**
- Sponsor outreach + follow-ups (pipeline + lightweight CRM behavior).
- Match sponsors to arenas/categories (who funds what).
- Match sponsors to outcomes (who funded which improvements, who enabled which families).
- Publish sponsor updates in a standardized format (transparent, auditable).

Hermes is also the perfect “demo agent” for CQFUN itself: Hermes improves its own CQFUN skills in public, proving the method.

## “Claws” as the Scaling Interface (turn the boom into a platform)

To harness a boom of many individual agents, you need a **composable capability model** so agents can specialize without becoming bespoke snowflakes. I recommend formalizing “Claw” as:

**Claw = a named, testable capability module with a strict interface + safety contract.**

Start with a small, opinionated set (the “various Claw”):
- `claw_cqfun`: parse/validate/score CQFUN artifacts; propose conversions.
- `claw_arcadna`: generate/verify ADNA metadata; sign attestations.
- `claw_diamod`: apply moderation rubric; produce escalation packets.
- `claw_hermes`: sponsor outreach + reporting (Hermes-specific behaviors).
- `claw_audit`: provenance trail + reproducible scoring summaries.

This makes it easy for the ecosystem to grow: people can build new claws without redefining the whole system.

## Critical Scope Boundaries (to keep launchable)

To keep the first MVP shippable, I recommend hard boundaries:

- **No medical data in MVP storage.** If any health context exists, store only non-medical eligibility flags and route medical records exclusively through CRA:ESC custody (see `ARCADNA.md`).
- **Avoid “proven medical” claims in product copy.** Keep EOMSCP as a north star, but don’t put it on the critical path of CQFUN MVP.
- **Pick one arena and one language first.** CQFUN already suggests FR-first for v0.4; that’s a reasonable simplification.

## 30/60/90 Day Launch Sequence (concrete and minimal)

**0–30 days: CQFUN Arena v0**
- Finalize CQFUN v0.4 header/spec and 3–5 examples.
- Ship GitHub-first arena rules + automated checks + leaderboard-as-a-markdown (good enough).
- Introduce Hermes as a “sponsor agent” concept with a simple reporting format.

**31–60 days: Reputation + portability**
- Add ADNA-lite registry conventions (how handles are issued/verified).
- Add “co-vet” and “pedigree” fields to submissions (from `ADNA.md` template).
- Publish DIAMod-lite dispute process (who can flag, who can appeal, what gets removed).

**61–90 days: Platformization**
- Stabilize Claw interfaces (schemas + minimal reference implementations).
- Start moving from GitHub-first to a small web UI *only if* volume demands it.

## Biggest Risks to MVP (and mitigations)

- **Ambition dilution:** too many ventures at once → ship CQFUN+ADNA+DIAMod first, keep others as narrative/support.
- **Human governance bootstrapping:** judges/parents/families are hard to scale → start with mechanical scoring + small invited cohorts.
- **Trust theater:** identity without real accountability → keep ADNA gate strict and define what “verification” means at each tier.

## Bottom Line Recommendation

Ship a **CQFUN Arena MVP** that is:
- gated by **ADNA-lite** identity,
- moderated by **DIAMod-lite** rules,
- accelerated by **Hermes Agent** (sponsor + coordination),
- extensible via a formal **Claw** capability interface.

This is the shortest path that both launches and credibly leverages the individual agent boom without overexposing you to the highest-risk domains on day one.


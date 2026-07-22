# HANDOFF

Working notes for {{PROJECT_NAME}}. This file is for the owner and their AI agents, not for visitors. If this repo deploys to static hosting, exclude this file from deployment so it never appears on the live surface.

## What this is

Two or three sentences: what the project is, its main files, and what each one does.

## Why it exists

One short paragraph: the problem this project solves and any standing rules that govern its public surface.

## What is deployed and how the pieces connect

- **Live URL:** {{URL}}
- **Hosting:** {{host, project name, and how deployment triggers}}
- **Source of truth:** {{repo URL and visibility}}
- Any gotchas an agent needs to know before deploying (stale config files, rename history, ignore rules).

## How to update

1. The edit workflow, step by step.
2. How to preview locally.
3. What review gates apply before pushing (truth review, owner approval, etc.).

## Current state

What is true right now. Keep this section honest and current; delete anything stale.

## Shipped {{DATE}}

- One bullet per change: what shipped, the commit hash, what was verified, and any deliberate deviations from the original plan with the reason.

## Current candidate (pre-verification snapshot)

This section describes the candidate this file ships inside. It is always pre-verification: a candidate commit cannot truthfully contain its own SHA or its own later verification result, so this section never names a SHA and never carries PASS or FAILED. The draft pull request owns the exact candidate SHA (its head) and the external verification result.

- **Feature branch:** {{branch name}}
- **Draft PR:** {{URL or reference}}
- **Candidate SHA:** identified externally by the PR head
- **Verifier:** pending
- **Verification status:** pending
- **Owner approval:** not given
- **Preview deployment:** {{none, or nonproduction preview auto-created by the host; a preview is neither approval nor shipment}}
- **Production deployment:** not deployed

## Historical release record (completed releases only)

Completed results live here, added by a later, separately verified documentation change, never by amending the original candidate. Each record may reference:

- **Verified candidate SHA:** {{sha}}
- **PR URL:** {{url}}
- **Verifier report URL:** {{PR review or comment link}}
- **Owner approval:** {{where recorded}}
- **Merge commit:** {{sha}}
- **Production commit:** {{sha}}
- **Live-verification result:** {{result and reference}}

A historical record documents what a past PR already proved externally. It is not the original candidate's self-contained verification, and the implementing agent still cannot write PASS anywhere without the verifier's report for the exact SHA.

## Unfinished / known gaps

- Open items, each with enough context that a fresh agent could pick it up cold.
- Decisions of record that constrain future work, with dates. If a decision gets overridden, mark it overridden rather than deleting it.

## How future agents should continue work

- Read `AGENTS.md` and this file first, then check recent `git log`.
- Reconcile this file against actual repo state before acting; do not assume it is perfect.
- Keep this file an accurate snapshot: when an unfinished item ships, move it up rather than leaving stale plans here.

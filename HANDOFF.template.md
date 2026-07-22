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

## Verification state

This file is a candidate-state snapshot captured before verification. It cannot truthfully contain its own commit SHA or its own later verification result: the draft pull request owns the exact candidate SHA and the external verification result, and the state recorded here stays pending inside every candidate commit.

If the project uses a verification agent, every handoff records:

- **Feature branch:** {{branch name}}
- **Implementation commit SHA:** {{sha}}
- **Verifier identity:** {{who or what verified, or pending}}
- **Verification date:** {{date, or pending}}
- **Verification type:** {{pre-merge gate / post-merge audit}}
- **Verification status:** {{pending / PASS / FAILED}}
- **Findings:** {{list, or PASS}}
- **Verification report or evidence reference:** {{where the verifier's result lives}}
- **Post-verification changes:** {{none, or what changed and that the pass is invalidated}}
- **Owner approval:** {{given / not yet}}
- **Merged SHA:** {{sha, or not merged}}
- **Deployed SHA and live-verification result:** {{sha + result, or not yet deployed}}

The implementing agent cannot populate PASS without receiving the verifier's result for the exact SHA. Until that result exists, status stays pending.

## Unfinished / known gaps

- Open items, each with enough context that a fresh agent could pick it up cold.
- Decisions of record that constrain future work, with dates. If a decision gets overridden, mark it overridden rather than deleting it.

## How future agents should continue work

- Read `AGENTS.md` and this file first, then check recent `git log`.
- Reconcile this file against actual repo state before acting; do not assume it is perfect.
- Keep this file an accurate snapshot: when an unfinished item ships, move it up rather than leaving stale plans here.

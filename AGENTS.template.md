# AGENTS.md

Repository instructions for AI coding agents working on {{PROJECT_NAME}}.

## Project role

One or two sentences: what this repo is, what it produces, and where it deploys.

## Required first reads

Before making changes, every AI agent must read:

1. `HANDOFF.md`
2. `README.md` if present
3. This `AGENTS.md`
4. Recent git history with `git log --oneline -5`
5. Current working tree status with `git status --short --branch`

Do not rely on prior chat context. Treat repository files, recent commits, and the owner's explicit current instruction as the source of truth.

## Privacy defaults

This repo is {{private/public}} by default. Do not change its visibility without the owner's explicit approval.

Do not expose:

- credentials, tokens, secrets, or local machine paths
- private strategy notes or unpublished plans
- personal identifiers beyond what the owner has already published
- {{ANY_PROJECT_SPECIFIC_PRIVATE_CONTENT}}

## Public copy rules

All public-facing copy must pass a truth review before commit or deployment:

- claims are accurate and supported by evidence
- no inflated credentials or unverifiable numbers
- no claiming roles, degrees, or outcomes that are not real
- names and titles spelled per the owner's convention: {{SPELLING_CONVENTIONS}}

## Change workflow

Before editing: confirm task scope, check `git status`, identify which files should change, avoid touching unrelated files.

After editing:

1. Review the diff.
2. Validate locally when possible.
3. Update `HANDOFF.md` if project state, shipped surface, unfinished work, or future-agent instructions changed.
4. Commit with a clear message.
5. Push the feature branch to origin. A task instruction saying "push" authorizes pushing the feature branch; it never authorizes bypassing verification by pushing directly to main. There is no documentation, record-only, copy, or small-change exception.

## Verification workflow

If the project uses a verification agent, the loop is:

1. Implementation happens on a feature branch, never directly on main.
2. The feature branch is pushed before verification, so the verifier reviews the exact commit.
3. The verifier checks that commit against the brief, these repo rules, available evidence, and the truth review. It reports findings and the verified commit SHA; it does not implement.
4. Failed checks return to the implementing agent for remediation; the fix is committed, pushed, and verified again.
5. Any implementation change after a pass invalidates the pass and requires re-verification.
6. Only a verified commit may merge to main, and only after the owner approves.
7. After deployment, the verifier checks the live URL. A live failure re-enters the loop.

Verification-integrity rules:

- An implementation agent cannot self-issue, infer, or record verifier approval. A PASS may only be recorded from a distinct verification result that names the exact commit SHA it reviewed.
- When that result is absent, verification status remains pending, no matter how confident anyone is about the outcome.
- A pre-merge verification gate and a post-merge audit are different things. A verification that runs after the commit has already reached main is a post-merge audit, and the record must say so.
- A post-merge technical PASS does not prove the protocol sequence was followed. Sequence failures are protocol failures even when the content passes.

The pull request is the authoritative external verification record:

- `HANDOFF.md` is a candidate-state snapshot captured before verification; its verification state stays pending inside every candidate commit, and a candidate commit is never amended merely to write PASS into its own handoff.
- A draft pull request from the feature branch to main identifies the exact candidate SHA externally.
- The verifier's PASS or FAIL report is tied to that exact SHA and lives in the PR review or a PR comment.
- A result recorded by the owner on behalf of the verifier must be labeled as a relayed report, not presented as the verifier's authenticated identity.
- Owner approval follows a PASS and is separately recorded on the pull request.
- Squashing or rebasing after a PASS changes commit identity and requires verification of the resulting candidate. A merge commit is acceptable only if the verified candidate SHA is preserved as a parent and no unverified content is introduced.

## Deployment rules

- Deployment method: {{e.g. merge to main auto-deploys to production via host X}}
- Distinguish preview from production: hosts may auto-create nonproduction preview deployments from feature branches or PRs. A preview is neither protocol approval nor production shipment; record preview and production states separately.
- If the host serves raw repo files, keep `HANDOFF.md` and `AGENTS.md` excluded from deployment (previews included, e.g. via the host's ignore file).
- After any production deploy, verify the live URL: confirm what must be there, and grep for what must not.

## Handoff protocol

When handing work to another agent or session, update `HANDOFF.md` with: current state, what changed and why, files touched, validation performed, remaining issues, open questions, and the recommended next action.

Tell the receiving agent:

```text
Read HANDOFF.md first.
Reconcile it against the current repo state.
Do not assume the handoff is perfect.
Check code, commits, and deployed behavior before making changes.
```

## Definition of done

1. The requested change is complete and unrelated files were not changed.
2. The diff has been reviewed.
3. Public copy passed the truth review, if any changed.
4. `HANDOFF.md` is updated, if state changed.
5. Changes are committed, and pushed if the task requires it.
6. The final response lists files changed, validation performed, commit hash, and open questions.

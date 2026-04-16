# Repository Agent Policy

This file defines repository-wide agent behavior that is shared across coding
agents. It does not override the biological, reference, workflow, or evidence
contracts.

## Communication Boundary

- Discussion with the human user may be in Japanese.
- Questions, planning notes, review explanations, and progress updates may be in
  Japanese when they are not intended to remain as repository artifacts.
- GitHub-facing and repository-facing artifacts must be written in English.
- Do not mix Japanese discussion text into English artifacts unless quoting
  source material or documenting a deliberate multilingual example.

## GitHub-Facing And Repository-Facing Artifacts

Write the final form of these artifacts in English:

- `README` files
- files under `docs/`
- files under `.github/`
- pull request descriptions
- issue drafts
- release notes
- commit messages intended for shared history
- ADRs, design notes, and handoff documents intended to remain in the repository
- evidence registry entries and claim-status memos

## Never Translate

Keep these strings in their original form unless the task explicitly requires a
translation:

- code
- shell commands
- logs
- stack traces
- file paths
- identifiers
- API names
- config keys
- dataset accessions
- evidence IDs and claim IDs
- search strings

## Workflow

- Separate Japanese discussion from English artifact generation.
- First clarify the plan and decisions with the human user in Japanese when that
  helps review accuracy.
- Then produce or edit the repository artifact in English.
- Before finishing changes to Markdown, `.github`, registry, or claim-status
  files, scan for accidental Japanese text unless it is an intentional quote or
  example.

## Session Resume

When resuming work, first read the canonical handoff:

`/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/AI_RESUME_HANDOFF.md`

Do not search broadly for handoff files. Do not treat `/tmp` drafts as
canonical. The handoff contains the read order, pending items, and decision
landscape.

## Dual-Agent Analysis

- When coordinating Codex and Claude Code on evidence analysis, follow
  `docs/DUAL_AGENT_ANALYSIS_WORKFLOW.md`.
- Treat that document as workflow guidance, not as a biological contract,
  reference contract, workflow-state extension, or evidence admissibility rule.

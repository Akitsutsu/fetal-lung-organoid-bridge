# Dual-Agent Analysis Workflow

## Purpose
This document defines the operational pattern for Codex and Claude Code to
collaborate on evidence analysis before repository-facing claim or registry
edits.

This is workflow documentation, not a biological contract and not a workflow
state-machine extension.

## Grounding
Before starting a dual-agent analysis run:

1. Fetch and prune the remote.
2. Start from `origin/main`, not from a stale local branch.
3. Confirm the current `HEAD` is grounded on the intended `origin/main`.
4. Treat `/tmp` as scratch only.
5. Keep stable local analysis outputs beside the source data or in another
   explicitly named stable local analysis directory.
6. Keep the legacy repository read-only unless the human user explicitly asks
   for legacy-repo edits.

Do not use a local-only cache, scratch clone, or legacy worktree as the
authoritative repository context.

## Division Of Labor

This workflow splits responsibilities along two lanes rather than a single
primary/secondary axis. The lanes are independent: scientific synthesis
authority does not imply repository-write authority, and vice versa.

- **Scientific synthesis lead: Claude Code.** Owns reclassification, evidence
  admissibility assessment, source-overlap and redundancy analysis,
  biological interpretation, uncertainty organization, and proposing candidate
  repository edits. Claude Code does not need to hold repository-write
  authority to act as synthesis lead.
- **Repository execution lead: Codex.** Owns workflow-contract cross-check,
  minimal registry/memo/doc edits, diff review, validation, commit, pull
  request, accidental-Japanese scan, and provenance documentation.

For evidence-heavy analysis, Claude Code may act as the scientific synthesis
lead while remaining read-only by default. Codex remains responsible for
repository edits, validation, commits, and pull requests unless the human
user explicitly authorizes a different write path for a specific run.

Codex may:

- ground the repository on `origin/main`
- run the first analysis pass
- create stable local analysis outputs
- prepare candidate repository diffs
- run Claude Code in analysis-only or review-only mode
- reconcile Claude Code findings with Codex findings
- apply minimal repository edits when evidence and human direction justify them
- validate, commit, push, and open a pull request

Claude Code may:

- independently inspect repository contracts and current claim state
- inspect stable local analysis outputs
- inspect images or other local analysis artifacts when relevant
- run read-only analysis commands when the invoking prompt explicitly restricts
  the run to non-mutating operations
- critique tile selection, measurement strategy, claim wording, and registry fit
- recommend whether a repository edit is justified

Claude Code should not be given repository-editing authority by default in this
workflow. If it does edit, Codex must review and validate those edits before
commit.

## Claude Code Invocation
For automated Claude Code analysis, prefer tools restricted to read and analysis
commands. Permission mode is an operator choice and should not be treated as a
repository default.

Example pattern:

```bash
claude -p "$(cat /path/to/prompt.txt)" \
  --allowedTools "Read Bash(git:*) Bash(rg:*) Bash(python3:*) Bash(ls:*) Bash(find:*)" \
  --add-dir /stable/local/data/path \
  --max-budget-usd 2
```

Use non-interactive or bypass permission modes only in a controlled,
analysis-only run where the prompt explicitly forbids repository edits and the
allowed tools exclude editing commands. If image inspection is biologically
important, do not remove it merely to reduce runtime or output volume. Adjust
output format or prompt structure instead.

Avoid command forms that make automation brittle, such as frequently changing
shell substitutions in approval-sensitive contexts. Prefer stable wrapper
commands or stable prompt-file paths when repeated runs are expected.

## Analysis Standard
The analysis itself is the priority.

Dual-agent analysis should:

- preserve image inspection when morphology or spatial interpretation depends on
  image evidence
- distinguish visual sanity checks from quantitative measurements
- distinguish segmentation-derived proxies from raw-image or histology-facing
  measurements
- sample enough tiles, bins, or units to assess within-group variation when a
  claim depends on representativeness
- avoid adding an evidence row when the new output is only a review aid
- avoid memo updates when the current claim bottom line does not change

When evidence is insufficient, leave the repository unchanged and record the
blocking analysis gap in the local handoff or final response.

## Repository Edit Threshold
Create or edit repository-facing artifacts only when the dual-agent analysis
reduces a claim-relevant uncertainty or changes evidence interpretation.

Possible outcomes:

- no repository edit
- evidence registry row candidate
- current-status memo update
- both registry row and memo update

Do not modify `decision_log.md` or contract files unless the work changes an
OS-wide semantic rule, admissibility rule, workflow meaning, boundary condition,
or reference interpretation.

## Validation
Before committing repository changes from a dual-agent analysis run:

1. Validate `EVIDENCE_REGISTRY.tsv` column count and basic dependency rules when
   the registry changes.
2. Scan changed repository-facing artifacts for accidental Japanese text unless
   the text is an intentional quote or example.
3. Run `git diff --check`.
4. Confirm `.codex` or other environment-generated scratch files are not staged.
5. Summarize which parts came from Codex analysis, Claude Code analysis, and
   human direction.

Commit messages, pull request descriptions, and repository-facing artifacts must
be written in English.

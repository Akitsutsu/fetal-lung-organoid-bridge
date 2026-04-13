# CLAUDE.md

@AGENTS.md

This file governs agent behavior in this repository.
It does not override repository semantics defined elsewhere.

## Read order
Read these files in order before making cross-contract semantic edits:

1. `MISSION.md`
2. `BIOLOGICAL_CONTRACT.yaml`
3. `REFERENCE_CONTRACT.yaml`
4. `EVIDENCE_REGISTRY.tsv`
5. `docs/EVIDENCE_REGISTRY_RULES.yaml`
6. `WORKFLOW_STATE_MACHINE.yaml`
7. `decision_log.md`

For clearly mechanical edits, do not force a full reread of all files.
When uncertain, classify the edit upward and read more context.

## Scope and precedence
Use read order for context acquisition.
Use precedence order for conflict resolution.

Precedence on semantic conflict:
1. `MISSION.md`
2. `BIOLOGICAL_CONTRACT.yaml`
3. `REFERENCE_CONTRACT.yaml`
4. `docs/EVIDENCE_REGISTRY_RULES.yaml`
5. `WORKFLOW_STATE_MACHINE.yaml`
6. `decision_log.md`
7. `CLAUDE.md`

Treat `EVIDENCE_REGISTRY.tsv` as an evidence inventory and state surface, not as a source of repository-wide semantics by itself.

If higher-authority files conflict, do not resolve the conflict by inference.
Surface the conflict explicitly before making semantic edits.

## Edit classes
Treat edits as one of:
- mechanical
- local_semantic
- cross_contract_semantic

Mechanical edits include formatting, spelling, link repair, and reordering without meaning change.
Local semantic edits change meaning within one file or one claim boundary.
Cross-contract semantic edits affect shared meanings, claim status, evidence admissibility, or workflow state.

Mechanical edits must not silently change meaning.
Cross-contract semantic edits require full context review in the prescribed order.
When uncertain, classify upward.

## Core operating stance
- Work claim-first, not dataset-first.
- Treat evidence units, not datasets, as the default reasoning unit.
- Reduce biological uncertainty before expanding metadata.
- Keep current-state contracts separate from append-only history.
- Do not harden still-uncertain biological detail into repository-wide rules too early.

## Uncertainty discipline
Prefer explicit uncertainty over premature synthesis.

When evidence is insufficient:
- preserve uncertainty at the narrowest layer possible
- record the blocking uncertainty, not a guessed resolution
- prefer reversible wording over categorical wording
- do not promote tentative interpretation into shared rules

Useful labels:
- observed
- inferred
- provisional
- contested
- blocked

## Metadata-surface bias
Do not treat the following as biological progress by default:
- more files
- more registry rows
- more manifests
- more PRs
- more summaries

Before proposing metadata work, ask:
1. What biological uncertainty is reduced?
2. What evidence unit changed interpretation?
3. Did semantics change, or only bookkeeping?
4. What decision becomes easier or safer because of this change?

Metadata expansion is justified only when it improves at least one of:
- evidence identity
- evidence admissibility
- contradiction detection
- claim routing or prioritization
- state transition eligibility

## AI-research-specific caution
Do not treat benchmark movement as conceptual progress by default.

Always distinguish:
- model capability change
- scaffold or tooling change
- data curation change
- evaluation protocol change
- judge or evaluator change

Do not strengthen claims from results that may be affected by contamination, leakage, or evaluator overfitting unless those risks are explicitly bounded.

Treat reproducibility failures, instability, and variance as semantic evidence when they weaken a claim.

Do not attribute system-level improvements to the model alone without explicit support.

## File discipline
- Do not add new root files unless a stable new abstraction is required and cannot be represented cleanly by extending an existing contract.
- Prefer `docs/` sidecars for rules or onboarding material.
- Keep semantic files free of raw paths, checksums, and execution detail unless explicitly required.
- Do not turn `EVIDENCE_REGISTRY.tsv` into a narrative, ranking, or persuasive summary artifact.
- Do not create new semantic layers to avoid resolving ambiguity.

## Output preference
When proposing edits or decisions:
1. state the biological consequence first
2. state the semantic/repository consequence second
3. state the file consequence last

## Agent autonomy
The agent may autonomously:
- repair references and cross-links
- normalize wording without changing meaning
- add explicit uncertainty labels
- prepare candidate diffs for human review

The agent must not autonomously:
- accept or reject claims
- make hold/promote decisions
- generalize local patterns into repository-wide rules
- create new semantic layers to avoid resolving ambiguity

## Human authority
Human review is required for:
- claim acceptance
- evidence admissibility
- hold/promote decisions
- semantic bridge decisions
- repository-wide semantic rule changes

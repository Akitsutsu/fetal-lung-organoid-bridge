# decision_log

## Purpose
This file is the append-only log of OS-wide semantic changes and major verdicts.

Current contract files describe the current authoritative state of the OS.
`decision_log.md` records when and why that state changed.

It records:
- mission-level operating decisions
- biological contract decisions
- reference contract decisions
- evidence registry rule decisions
- workflow state decisions
- explicit bridge decisions that change operating semantics
- major verdicts with OS-wide consequence

It does not record:
- dataset-specific inspection notes
- local execution/debug history
- prompt transcripts
- routine file additions, moves, or renames without semantic effect
- editorial refactors without semantic effect

## Logging rules
- Append only.
- Do not rewrite prior entries.
- Corrections are made by new entries.
- Current contract files may be edited to reflect the current authoritative state, but any semantic change must be logged here as a new entry.
- Log only decisions that change operating semantics, admissibility rules, workflow meaning, boundary conditions, or release interpretation.
- Dataset-level review outcomes belong elsewhere unless they establish an OS-wide rule or major verdict.

## Entry template
### D-XXXX | YYYY-MM-DD | accepted | short title
- kind: rule | verdict | bridge
- scope:
- decision:
- rationale:
- affected_files:
- effective_from:
- supersedes:

## Initial entries

### D-0001 | 2026-04-12 | accepted | establish mission authority and legacy boundary
- kind: bridge
- scope: repo identity and boundary with the legacy workspace
- decision: adopt `MISSION.md` as the top-level mission contract for the new claim-first OS. The legacy workspace is informative but not authoritative unless a rule or invariant is explicitly lifted into this OS.
- rationale: keeps the new workspace distinct from the legacy audit / evidence archive while allowing selective inheritance of stable rules
- affected_files: `MISSION.md`
- effective_from: 2026-04-12
- supersedes: none

### D-0002 | 2026-04-12 | accepted | establish compact biological contract
- kind: rule
- scope: biological semantics for OS v0.1
- decision: adopt `BIOLOGICAL_CONTRACT.yaml` as the compact biological contract for program, alignment, modality policy, claim frame, and GSE acquisition priority. Do not split these semantics into separate root contracts yet.
- rationale: keeps biological semantics explicit while preserving packaging flexibility during early OS formation
- affected_files: `BIOLOGICAL_CONTRACT.yaml`
- effective_from: 2026-04-12
- supersedes: none

### D-0003 | 2026-04-12 | accepted | establish inherited reference invariants
- kind: rule
- scope: reference semantics for OS v0.1
- decision: adopt `REFERENCE_CONTRACT.yaml` for stable inherited invariants only: paired reference handling, sample_week defaulting, support-layer role in default reference maintenance, release immutability, anchor non-cohort default, and reference/evidence boundary.
- rationale: keeps inherited reference rules explicit without importing unstable legacy operating detail
- affected_files: `REFERENCE_CONTRACT.yaml`
- effective_from: 2026-04-12
- supersedes: none

### D-0004 | 2026-04-12 | accepted | establish evidence unit registry boundary
- kind: rule
- scope: evidence indexing and registry semantics
- decision: adopt `EVIDENCE_REGISTRY.tsv` as the canonical index of evidence units rather than datasets. Valid evidence units may include sample, condition, donor split, image set, and paired split. `docs/EVIDENCE_REGISTRY_RULES.yaml` is the subordinate normative sidecar that defines how the registry is filled.
- rationale: preserves fine-grained evidence accounting and future-proofs the registry against dataset-centric rigidity while keeping the TSV itself canonical and flat
- affected_files: `EVIDENCE_REGISTRY.tsv`, `docs/EVIDENCE_REGISTRY_RULES.yaml`
- effective_from: 2026-04-12
- supersedes: none

### D-0005 | 2026-04-12 | accepted | establish workflow state machine semantics
- kind: rule
- scope: operational workflow semantics for evidence units
- decision: adopt `WORKFLOW_STATE_MACHINE.yaml` as the single-active-state operational contract. `workflow_state` must not encode biological strength, ranking, or claim confidence.
- rationale: keeps workflow progression distinct from scientific interpretation
- affected_files: `WORKFLOW_STATE_MACHINE.yaml`
- effective_from: 2026-04-12
- supersedes: none

### D-0006 | 2026-04-12 | accepted | establish decision log scope
- kind: rule
- scope: decision logging policy
- decision: `decision_log.md` records OS-wide rule changes and major verdicts only. Dataset-specific inspection notes are out of scope.
- rationale: prevents the semantic log from collapsing into an execution notebook
- affected_files: `decision_log.md`
- effective_from: 2026-04-12
- supersedes: none

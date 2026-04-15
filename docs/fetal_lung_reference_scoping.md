# Fetal lung reference scoping

## Status

This document is an exploratory scoping sidecar. It is not a
biological contract, not a reference contract, not a workflow
state-machine extension, not an evidence admissibility rule, and
not a claim-status memo.

It records how fetal lung reference data is partitioned for
repository governance. The partition may be revised as new data
becomes available, as local analyses mature, or as existing data
changes admissibility status.

This sidecar makes the local-only fetal reference partition visible
as a governance category. It does not promote any local observation
to repository evidence.

## Relationship to existing contracts and claims

- `EVIDENCE_REGISTRY.tsv` is the authoritative inventory of admitted
  evidence. This sidecar does not duplicate, enumerate, or override
  registry rows.
- `BIOLOGICAL_CONTRACT.yaml` and memos under `docs/claims/` remain
  the authoritative claim-level and contract-level documents. This
  sidecar does not modify them.
- `docs/organoid_mapping_axes_scoping.md` records the organoid side
  of the fetal-organoid mapping axes. This sidecar records the fetal
  reference landscape and is intended to be read alongside it.

## Partition

Fetal lung reference data considered by this repository falls into
three governance partitions. Each partition has a different evidentiary
status.

### Registered evidence

Fetal lung reference data admitted as sample-level, derived, or
claim-linked evidence. The authoritative enumeration is
`EVIDENCE_REGISTRY.tsv`, with claim-level interpretation summarized
in the corresponding current-status memo under `docs/claims/`.

The repository currently carries fetal spatial transcriptomics as
sample-level registered units, with separate derived interpretation
rows linked to the relevant claim. This sidecar does not restate
those rows and does not change their workflow state.

### Local-only triage

Fetal lung reference data that has been analyzed locally but has not
been promoted to a registry row. This partition may include
single-cell or single-nucleus RNA-seq references, spatial candidate
datasets, and mixed developmental or disease cohorts where
fetal-window samples are present but source provenance, donor
mapping, modality alignment, independence, or claim routing remains
unresolved.

Local-only triage may produce biological observations useful for
human review. Those observations are not claim-bearing, are not
registry evidence, and are not reflected in `EVIDENCE_REGISTRY.tsv`
unless a separate promotion decision is made.

Stable local triage outputs are maintained outside the repository
artifact surface, alongside source data or in explicitly named local
analysis locations. Session handoffs or local scoping memos may point
to those outputs, but this sidecar does not index them.

Promotion from local-only triage to registered evidence requires the
normal human-review process defined in `CLAUDE.md`,
`docs/DUAL_AGENT_ANALYSIS_WORKFLOW.md`, and the existing contract /
claim governance.

### Restricted or held

Fetal lung reference data that is known to exist but is not currently
usable under the repository's access-independent admissibility
criteria or current claim frame. Reasons may include restricted
download status at source portals, unresolved fetal-alignment caveats,
unresolved source-provenance questions, or overlap with already
registered evidence that prevents independent support.

Records in this partition are not evaluated as admissible evidence
until the access, alignment, provenance, or independence issue changes.

## Why three partitions are distinguished

Distinguishing local-only triage from registered evidence prevents
two failure modes:

- Local biological observations being read as if they were
  claim-bearing evidence.
- Local biological observations being lost simply because they are
  not registry evidence.

This sidecar records that the local-only partition exists and defines
its governance status. The detailed inventory of local-triage
observations remains outside this document.

## Scope discipline

This sidecar does not:

- Enumerate specific accessions, dataset names, file paths, or
  quantitative findings.
- Register evidence rows, claim IDs, contract programs, or workflow
  transitions.
- Assert biological conclusions.
- Substitute for `EVIDENCE_REGISTRY.tsv`, claim-status memos, or
  local scoping memos.
- Serve as a session-handoff index.

Changes to this sidecar are allowed when the partition definitions
fail to capture a new kind of fetal reference data, or when a
governance decision changes what belongs in a partition. Changes must
preserve atemporal phrasing and must not introduce quantitative
findings or dataset-specific identifiers.

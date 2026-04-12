# Legacy import policy

## Purpose
This policy governs selective import from the legacy repository into this repository.

The goal is not to recreate the legacy workspace.
The goal is to carry forward only the material that reduces active biological uncertainty or stabilizes current claim interpretation.

## Authority rule
The legacy repository is informative, not authoritative, unless a rule, invariant, or interpretation is explicitly adopted here.

Import is translation into the new OS, not mirroring of legacy structure.

## What may be imported
Import only:
- stable semantic conclusions
- claim-relevant evidence interpretations
- stable inherited invariants that remain compatible with current contracts

## What must not be imported by default
Do not import by default:
- prompt history
- long handoff narratives
- execution details
- local debugging notes
- broad summary artifacts copied as a whole
- legacy file structure for its own sake

## Default unit of import
The default import unit is:
- an evidence unit
- a claim slice
- a narrowly scoped invariant

The default import unit is not:
- an entire dataset
- an entire tranche
- an entire summary document

## Required import record
Every imported element must state:
- source
- scope
- caveat
- destination

Destination must refer to a current-repo target such as:
- a current contract
- the evidence registry
- a rules sidecar
- the workflow state layer
- the decision log

## Minimality rule
Import only when it does at least one of the following:
- reduces an active biological uncertainty
- sharpens a claim boundary
- clarifies evidence admissibility
- preserves a stable inherited invariant
- prevents a known semantic error

## Conflict rule
If legacy material conflicts with current contracts, do not resolve the conflict by quiet inference.

Surface the conflict explicitly and require a decision.

## Non-goal
This policy does not aim to reconstruct the legacy repository inside the new repository.

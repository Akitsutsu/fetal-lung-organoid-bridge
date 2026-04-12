# Legacy import: P-0001 format-vs-directed same-line slice v1

## Purpose
Import the minimum legacy semantic slice needed to support current P-0001 reasoning in the new OS.

This import does not recreate a dataset, tranche, comparison world, or broad legacy summary.

## Source
Legacy source files actually used:
- `reports/repo_state/p0001_geo_candidate_reevaluation_v1.md`
- `reports/repo_state/gse184142_bounded_control_strengthening_v1.md`

## Scope
This import covers only:
- one same-line directed support interpretation
- one same-line format-only control interpretation
- one held environmental perturbation interpretation

This import does not cover:
- strict P-0001 closure
- single-experiment matched-split closure
- broad comparison-world restatement
- lifecycle or prediction artifacts

## Imported interpretation

### Support
The GSE221343 L+DCI condition (SPC2-ST-B2, 3D, directed medium) produces a biological shift characterized by strong AGER, reduced SFTPC, and low SOX2 — a directed identity that is qualitatively distinct from all same-line format-only conditions reviewed in the legacy repo. This is imported as claim-linked support for P-0001 under `evidence_role = support`.

### Control
The GSE184142 ALI air-control condition (SPC2-ST-B2, ALI, AT2-maintenance medium only) retains AT2 identity and does not shift toward the SOX2lowCFTR+ directed outcome. It resolves the legacy question "does ALI format alone drive the directed-arm shift?" in the negative. This is imported as claim-linked control for P-0001 under `evidence_role = control`, anchoring the format-only arm.

### Hold
The GSE184142 ALI smoke condition (SPC2-ST-B2, ALI, with cigarette smoke exposure) shows an identity additive to air-control ALI rather than a distinct directed shift. Because smoke is an environmental perturbation, the current OS treats this sample as not admissible as a pure format-only control. It is held under `caveat_or_hold_reason = environmental_perturbation_hold` pending an explicit decision on whether perturbed-format evidence can inform P-0001 separately from the pure format control.

## Caveats
- Not strict P-0001 closure. Legacy explicitly records the strict-closure verdict as unreachable from public data alone.
- This is a cross-study bundle (GSE221343 directed + GSE184142 format) rather than a single-experiment matched-split design.
- The smoke condition is held as environmental perturbation rather than admitted as a pure format-only control, even though legacy notes it did not itself shift toward the directed identity.

## Destination
- Evidence rows:
  - `EV-0001` — GSE221343 L+DCI (support)
  - `EV-0002` — GSE184142 ALI air-control (control)
  - `EV-0003` — GSE184142 ALI smoke (hold)
- Claim target: `P-0001`
- No contract change
- No workflow change
- No `decision_log.md` entry created by default

## Non-imported legacy material
Intentionally not carried over:
- legacy comparison-world bodies (v5 and prior)
- legacy lifecycle, prediction registry, and contrast registry artifacts
- legacy marker-fraction tables and cell counts
- legacy execution, acquisition, and conversion details
- legacy tranche scaffolding and broad summary documents

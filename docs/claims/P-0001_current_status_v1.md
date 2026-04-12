# P-0001 current status v1

## Scope
This is a current-state claim memo in the new OS.
It is not a closure note, not a prediction-registry replacement, and not a comparison-world recreation.

## Current claim frame
P-0001 states that a same-line directed intervention produces a biological shift that is not explained by culture format alone and remains biologically interpretable in fetal developmental context. The claim is registered under the `format_vs_directed_disentanglement` program. Strict success requires separating directed effect from format-only effect on the same line while preserving coherent fetal developmental interpretation.

## Current support
EV-0001 (GSE221343 L+DCI, SPC2-ST-B2_iAT2, 3D, directed, LDCI) is registered as `claim_linked` support for P-0001. The imported P-0001 slice records this sample as a directed identity that is qualitatively distinct from same-line format-only conditions in the legacy review. This row supports P-0001's directed arm. It does not by itself establish strict closure.

## Current control
EV-0002 (GSE184142 ALI air-control, SPC2-ST-B2_iAT2, ALI, format_only) is registered as `claim_linked` control for P-0001. EV-0001 and EV-0002 share a conservative cross-study same-line pairing (`PG_P0001_same_line_cross_study_v1`). Per D-0007 this pairing is an interpretive grouping key only; it does not by itself prove matched-split status, same-experiment provenance, or claim-closing weight. The format-only arm currently rests on a cross-study bundle, not a single-experiment matched split.

## Current hold / inadmissibility
EV-0003 (GSE184142 ALI smoke) is held under `environmental_perturbation_hold`; smoke is an environmental perturbation and is not admitted as a pure format-only control without explicit decision. EV-0004 (GSE193716 adult primary AT2, pre-culture) is held under `adult_primary_vs_fetal_caveat`; the hold is semantic, not technical, and preserves the rule that adult-primary evidence is not admissible as fetal-alignment support under the current claim frame without explicit caveat, boundary-stress role, or bridge decision.

## Current bottom line
Strict P-0001 closure is not achieved. The format-only alternative explanation is materially weakened: the ALI air-control (EV-0002) does not shift toward the directed identity, and the supporting same-study matched-split pair within GSE184142 (EV-0002 and EV-0005 in `PG_GSE184142_matched_split_format_v1`) shows format alone does not produce the directed-arm outcome. The repository now carries enough support, control, and hold structure to identify the next true gap rather than accumulate more incidental rows.

## Next gap
A single-experiment, same-line SPC2-ST-B2 tranche that contains both an explicit directed-arm condition and a format-only condition, so that the P-0001 split can be evaluated within one experiment rather than across studies.

## Non-goals
This memo does not close P-0001, does not change any contract or workflow rule, does not add or retire evidence rows, does not recreate legacy comparison-world or lifecycle artifacts, and does not introduce new schema or new claim targets.

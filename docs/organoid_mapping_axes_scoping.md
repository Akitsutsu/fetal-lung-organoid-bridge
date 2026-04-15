# Organoid ↔ fetal lung mapping — axis scoping

## Status
This document is an exploratory scoping sidecar. It is not a
biological contract, not a reference contract, not a workflow
state-machine extension, not an evidence admissibility rule, and
not a claim-status memo.

It describes the axes along which organoid queries are currently
evaluated for fetal lung mapping in this repository. The axes may
be revised as new evidence becomes available. Promoting any axis
to a contract program or to a claim requires the normal human
review process defined in `CLAUDE.md`, `docs/DUAL_AGENT_ANALYSIS_WORKFLOW.md`,
and the existing contract / claim governance.

## Relationship to existing contracts and claims
- `BIOLOGICAL_CONTRACT.yaml` defines two programs:
  `alveolarization_alignment` and
  `format_vs_directed_disentanglement`. This sidecar does not
  modify either program.
- `P-0001` and `P-0002` current-status memos are unchanged by this
  sidecar.
- `EVIDENCE_REGISTRY.tsv` is unchanged by this sidecar. No axis
  listed below maps to an existing evidence row.
- The `alveolar_epithelial_maturation` scope_layer in
  `BIOLOGICAL_CONTRACT.yaml` carries the AQP5 iPSC/hESC-derived
  organoid-system caveat that is the one cross-axis constraint
  already reflected in the contract.

## Axis framework

Six axes are currently used to evaluate organoid queries for fetal
lung mapping. Each axis defines a biological scope and a working
marker panel. Candidate-specific provenance, source overlap, and
independence are evaluated separately before any repository
promotion. The axes are not mutually exclusive; a single organoid
system may address multiple axes.

### Axis A — Proximal airway (basal / club / ciliated)
Scope: larger airway and tracheal epithelium, including canonical
basal (TP63, KRT5, KRT14, KRT15, NGFR), club / secretory (SCGB1A1,
SCGB3A2, MUC5B), and ciliated (FOXJ1, TUBA1A) lineages.

A candidate fully satisfies Axis A when a coherent canonical basal
cluster (TP63+KRT5+KRT14+) and separable club or ciliated clusters
are both present. Candidates with only one compartment, or with
incomplete basal co-firing, should be treated as partial.

### Axis B — Pulmonary neuroendocrine
Scope: rare PNEC-like cells with neuronal-program markers (ASCL1,
INSM1, CHGA, SYP). Satisfied when a coherent subpopulation
co-expresses those markers.

### Axis C1 — Budtip progenitor (revised)
Scope: fetal distal tip progenitors anchored in SOX9+ NKX2-1+ cells
with budtip-marker dominance (TESC, ID2, CA2, FGF20). The earlier
strict requirement of "HOPX / AQP5 / AGER absent" was removed
because fetal BTOs co-express early alveolar markers alongside the
budtip program.

A candidate satisfies Axis C1 when SOX9+ NKX2-1+ cells form a
coherent cluster with TESC / ID2 / CA2 / FGF20 dominant. SFTPC and
AQP5 may be present, but they are interpreted as contextual
commitment markers rather than exclusion criteria.

### Axis C2 — Late tip / early alveolar commitment
Scope: SOX9+ NKX2-1+ SFTPC+ cells with commitment markers (HOPX,
AQP5, AGER, PDPN) that vary with differentiation condition,
passage, timepoint, or late-tip / early-alveolar state context.
Axis C2 is the continuation of Axis C1 along the differentiation
axis; the two are not mutually exclusive.

### Axis D — Submucosal gland / secretory
Scope: fetal submucosal gland precursors and mature secretory cells
(MUC5B, LTF, LYZ, BPIFB1). Distinct from Axis A club / ciliated
framing.

Secretory-marker expression alone is not sufficient for Axis D;
SMG interpretation requires ductal or glandular context.

### Axis E — Mesenchymal
Scope: fetal lung mesenchymal subtypes (alveolar fibroblasts,
alveolar myofibroblast, pericyte, smooth muscle, lipofibroblast).
Addressable only by organoid queries with intentional mesenchyme;
epithelial-only systems are out of scope.

### Axis F — Endothelial / vascular
Scope: capillary, arterial, venous, lymphatic, and aerocyte
lineages. Typically requires co-culture or vascularized organoid
systems.

## Cross-axis caveats

### iPSC / hESC versus primary fetal organoid systems
The `alveolar_epithelial_maturation` scope_layer in
`BIOLOGICAL_CONTRACT.yaml` records that AQP5 expression below
interpretable fractions is specifically an iPSC/hESC-derived
organoid-system constraint. Primary fetal BTO systems retain AQP5
expression. This distinction applies to axes C1, C2, and any
downstream alveolar-maturation interpretation.

### Axis independence from claim closure
Satisfying any axis above is necessary but not sufficient for
evidence-row promotion. Evidence admissibility remains governed
by the biological contract, evidence registry rules, workflow
rules, claim-status memos, and human review.

### Strict definitions vs observed biology
Axes should define required and acceptable-present markers
separately. Requiring absence of commitment markers (as the
original Axis C1 strict definition did) can exclude biologically
real fetal populations. Axis definitions should be revisited when
empirical evidence shows the required-absent set is not satisfied
by admissible data.

### Axis-specific addressability
Axes differ in their current addressability by admissible organoid
queries. Axis C1, Axis C2, and sub-parts of Axis A are addressable
at the sample or cluster level within the existing admissible
landscape. Axis A full closure, requiring the Axis A canonical
basal panel (TP63 / KRT5 / KRT14 / KRT15 / NGFR) to co-fire in a
fetal or fetal-relevant organoid scRNA dataset, has not been
demonstrable from currently admissible public organoid query
records. Some of the strongest basal-directed iPSC organoid
candidates identified in local scoping share parent iPSC line
history with already-evidenced organoid lines, which disqualifies
them under the existing candidate-level independence screen. Axes
B, D, E, and F remain held, partial, or not locally addressable
for the reasons given in their individual scope entries.

A similar but distinct pattern applies to Axis D. Some of the
strongest publicly accessible SAE/SMG organoid candidates identified
in local scoping are derived from adult primary tissue without an
explicit fetal-alignment caveat. Those records may be useful as adult
mature SMG boundary context, but they do not qualify for fetal Axis D
integration under the existing adult-primary-only without
fetal-alignment screen. Axes A and D therefore share a structural gap
pattern: neither fetal-specific axis is closed by candidate records
passing the current admissibility screens. The underlying disqualifier
differs, however: parent iPSC line overlap for Axis A, and
adult-primary-only source without fetal alignment for Axis D.

## Non-goals

This sidecar does not:
- Introduce any new claim ID.
- Introduce any new evidence registry row.
- Modify `BIOLOGICAL_CONTRACT.yaml`, `REFERENCE_CONTRACT.yaml`,
  `WORKFLOW_STATE_MACHINE.yaml`, `EVIDENCE_REGISTRY.tsv`,
  `decision_log.md`, or any `docs/claims/*` memo.
- Commit to any specific organoid query, GEO accession, or
  laboratory as a persistent reference for any axis.
- Replace local scoping notes as the detailed working layer.

## Revision discipline
Changes to this sidecar are allowed when (a) empirical evidence
shows an axis definition fails to capture real biology, or (b) a
new axis becomes addressable by available organoid data. Changes
must preserve atemporal phrasing and must not introduce
dataset-specific numbers into this document.

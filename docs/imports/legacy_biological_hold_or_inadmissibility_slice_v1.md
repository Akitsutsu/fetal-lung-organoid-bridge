# Legacy import: biological hold / inadmissibility slice v1

## Purpose
Import the minimum legacy semantic slice needed to preserve a biological inadmissibility pattern in the new OS.

This import does not recreate a dataset, tranche, comparison world, or broad legacy summary.
Its purpose is to record a case where evidence is biologically informative but not currently admissible for active fetal-lung claim use without explicit caveat.

## Source
Legacy source files actually used:
- `reports/repo_state/coverage_boundary_audit_v1.md`
- `reports/tranches/gse193716_decision_prep_v1/README.md`

## Scope
This import covers only:
- biological hold / inadmissibility driven by adult-primary vs fetal comparison mismatch
- the distinction between biological interest and current claim admissibility
- the rule that inadmissibility here is semantic, not technical

This import does not cover:
- broad P-0002 alignment summary
- adult-primary biology as a whole
- technical QC failure
- lifecycle or prediction artifacts
- comparison-world reconstruction

## Imported interpretation

### Biological inadmissibility
Freshly isolated adult primary AT2 evidence projects onto fetal progenitor-like reference states under the current fetal-lung-centered reference. Whether this reflects a retained progenitor-like signature, limited adult representation in the fetal reference, or default closest-neighbor behavior cannot be resolved from projection alone. Under the current claim frame this ambiguity makes such evidence not admissible as fetal-alignment support without explicit caveat.

### Not a technical rejection
The hold is not a statement of failed processing, low quality, or unusable evidence. Legacy review recorded technically clean projections (off-target within existing-tranche range) for the adult primary rows. The constraint is semantic: the comparison frame does not adjudicate adult-primary identity on a fetal reference, not that the data is defective.

### Future reuse
Future reuse would require at least one of: explicit caveat recorded on the evidence unit; use under a `boundary_stress` role rather than as fetal-alignment support; a separately defined adult-primary program with its own reference and success conditions; or an explicit bridge decision that changes how adult-primary evidence is admitted relative to fetal-lung claims.

## Caveats
- This is not a strict claim-closing import.
- This is not a statement that adult-primary evidence is biologically unimportant.
- This is not a statement that all adult-primary evidence must always remain held.
- This is a current-OS inadmissibility interpretation under the present fetal-lung-centered claim frame.

## Destination
- Program context: `alveolarization_alignment`
- Current claim consequence: constrains admissibility around fetal-lung alignment claims without creating new support
- Default registry consequence for future row import: `workflow_state = hold`
- Default caveat token for future row import: `adult_primary_vs_fetal_caveat`
- No contract change
- No workflow change
- No `decision_log.md` entry created by default
- No new evidence rows added by this import

## Non-imported legacy material
Intentionally not carried over:
- specific adult-primary sample identifiers, marker tables, and cell counts
- legacy comparison-world bodies and shadow-benchmark scaffolding
- legacy lifecycle, prediction registry, and contrast registry artifacts
- legacy projection diagnostics and decision-prep row-level recommendations
- legacy tranche structure and broad summary documents

# P-0002 current status v1

## Scope
This is a current-state claim memo in the new OS.
It is not a closure note, not a prediction-registry replacement, and not a comparison-world recreation.

## Current claim frame
P-0002 states that organoid developmental programs can be aligned to fetal lung alveolarization-relevant developmental programs without reducing interpretation to generic nearest-state mapping alone. The claim is registered under the `alveolarization_alignment` program. Strict success requires alignment coherent across stage, trajectory, morphology, and off-target axes, and remaining stable when morphology, temporal structure, and image-linked or spatial evidence are considered.

## Current program-relevant registrations
EV-0006 and EV-0007 register the GSE221342 BU3_NGAT iAT1 ALI serial pair (ALI p0 and ALI p1) under `alveolarization_alignment` with `pairing_group_id = PG_GSE221342_serial_ALI_passage_v1`. They supply the temporal/serial axis on the organoid side. EV-0008 registers GSE264425 GSM8217894, a Xenium spatial transcriptomics section of FFPE fetal lung at GW18, under `alveolarization_alignment`. It supplies a spatial / tissue-native axis on the fetal reference side at a stage directly relevant to alveolarization. None of these rows are claim-linked. They are program-relevant registrations, not support.

## Current support
There are currently no `claim_links = P-0002` support rows.

## Current hold / inadmissibility
EV-0004 (GSE193716 adult primary AT2, pre-culture) remains held under `adult_primary_vs_fetal_caveat`. The imported inadmissibility slice records this as a semantic, not technical, hold: projections are interpretable but adult-primary identity cannot be adjudicated on the current fetal-lung-centered reference without explicit caveat, boundary-stress role, or bridge decision. Future reuse for P-0002 is permitted only under those conditions and is not currently exercised.

## Current bottom line
P-0002 is not yet claim-linked at the support level. The repository now carries at least one temporal organoid-side registration (EV-0006/EV-0007 serial pair) and one spatial fetal-reference registration (EV-0008) under `alveolarization_alignment`, plus the inadmissibility boundary case (EV-0004). The missing piece is a first legitimate claim-linked row — support or falsifier candidate — anchored in an actual alignment outcome rather than a potential one.

## Next gap
A first claim-linked row that carries an actual alignment-outcome assessment against the fetal reference — for example, a projection outcome on EV-0006 or EV-0007 evaluated against the required P-0002 axes, or an explicit spatial/morphology corroboration tied to EV-0008 — so that `P-0002` gains its first `support` or `falsifier_candidate` role.

## Non-goals
This memo does not close P-0002, does not change any contract or workflow rule, does not transition any row between workflow states, does not add or retire evidence rows, does not recreate legacy comparison-world or lifecycle artifacts, and does not introduce new schema or new claim targets.

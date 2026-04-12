# P-0002 current status v1

## Scope
This is a current-state claim memo in the new OS.
It is not a closure note, not a prediction-registry replacement, and not a comparison-world recreation.

## Current claim frame
P-0002 states that organoid developmental programs can be aligned to fetal lung alveolarization-relevant developmental programs without reducing interpretation to generic nearest-state mapping alone. The claim is registered under the `alveolarization_alignment` program. Strict success requires alignment coherent across stage, trajectory, morphology, and off-target axes, and remaining stable when morphology, temporal structure, and image-linked or spatial evidence are considered.

## Current program-relevant registrations
EV-0006 and EV-0007 register the GSE221342 BU3_NGAT iAT1 ALI serial pair (ALI p0 and ALI p1) under `alveolarization_alignment` with `pairing_group_id = PG_GSE221342_serial_ALI_passage_v1`. They supply the temporal/serial axis on the organoid side. EV-0008 registers GSE264425 GSM8217894, a Xenium spatial transcriptomics section of FFPE fetal lung at GW18, under `alveolarization_alignment`. It supplies a spatial / tissue-native axis on the fetal reference side at a stage directly relevant to alveolarization. These three rows are sample-level registered units; they are program-relevant, not themselves claim-linked. The assessed interpretation derived from the serial pair is carried by EV-0009 and is described in the next section.

## Current support
EV-0009 is the first `claim_links = P-0002` support row. It is a derived `unit_level = serial_chain` unit over GSM6858852 and GSM6858853 (BU3_NGAT iAT1 ALI p0 → p1), sharing `pairing_group_id = PG_GSE221342_serial_ALI_passage_v1` with EV-0006 and EV-0007. The support is partial-axis: along the trajectory (SOX2lowCFTR+ strengthens p0 → p1), stage coherence (late_GW17_19 sharpens), and quality (off-target decreases) axes, with culture format held constant at ALI so format effect is not conflated with directed effect. EV-0009 does not on its own close the morphology axis or the full multimodal alignment condition of P-0002, and it is not intended to.

## Current hold / inadmissibility
EV-0004 (GSE193716 adult primary AT2, pre-culture) remains held under `adult_primary_vs_fetal_caveat`. The imported inadmissibility slice records this as a semantic, not technical, hold: projections are interpretable but adult-primary identity cannot be adjudicated on the current fetal-lung-centered reference without explicit caveat, boundary-stress role, or bridge decision. Future reuse for P-0002 is permitted only under those conditions and is not currently exercised.

## Current bottom line
P-0002 now has its first claim-linked support row (EV-0009). Support remains partial-axis — trajectory, stage, and quality only — rather than full-axis. The repository now carries a temporal organoid-side assessed interpretation, a spatial fetal-reference registration (EV-0008), and an inadmissibility boundary case (EV-0004), which is enough structure to name the next gap more precisely rather than as "any first support row."

## Next gap
The first multimodal corroborating row: a `support` or `falsifier_candidate` unit that brings morphology or spatial evidence to bear on the same alignment that EV-0009 carries on trajectory/stage/quality alone — for example, an assessed interpretation tied to EV-0008's Xenium spatial context at a stage matching the EV-0009 endpoints.

## Non-goals
This memo does not close P-0002, does not change any contract or workflow rule, does not transition any row between workflow states, does not add or retire evidence rows, does not recreate legacy comparison-world or lifecycle artifacts, and does not introduce new schema or new claim targets.

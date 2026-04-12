# P-0002 current status v1

## Scope
This is a current-state claim memo in the new OS.
It is not a closure note, not a prediction-registry replacement, and not a comparison-world recreation.

## Current claim frame
P-0002 states that organoid developmental programs can be aligned to fetal lung alveolarization-relevant developmental programs without reducing interpretation to generic nearest-state mapping alone. The claim is registered under the `alveolarization_alignment` program. Strict success requires alignment coherent across stage, trajectory, morphology, and off-target axes, and remaining stable when morphology, temporal structure, and image-linked or spatial evidence are considered.

## Current program-relevant registrations
EV-0006 and EV-0007 register the GSE221342 BU3_NGAT iAT1 ALI serial pair (ALI p0 and ALI p1) under `alveolarization_alignment` with `pairing_group_id = PG_GSE221342_serial_ALI_passage_v1`. They supply the temporal/serial axis on the organoid side. EV-0008 registers GSE264425 GSM8217894, a Xenium spatial transcriptomics section of FFPE fetal lung at GW18, under `alveolarization_alignment`. It supplies a spatial / tissue-native axis on the fetal reference side at a stage directly relevant to alveolarization. These three rows are sample-level registered units; they are program-relevant, not themselves claim-linked. The assessed interpretations derived from the serial pair and from the GW18 spatial sample are carried by EV-0009 and EV-0010 respectively and are described in the next section.

## Current support
Two `claim_links = P-0002` support rows now exist. Both are partial-axis and complementary. EV-0009 is a derived `unit_level = serial_chain` unit over GSM6858852 and GSM6858853 (BU3_NGAT iAT1 ALI p0 → p1), carrying support along the trajectory (SOX2lowCFTR+ strengthens p0 → p1), stage coherence (late_GW17_19 sharpens), and quality (off-target decreases) sub-axes, with culture format held constant at ALI. EV-0010 is a derived sample-level assessed interpretation built on EV-0008 (GSM8217894 GW18 Xenium) under `source_unit_id = GSM8217894_analysis_v1`; it carries support on the spatial-architecture sub-axis in native fetal lung at a matching developmental stage — the SOX2lowCFTR+ trajectory state shows a coherent distal-epithelial niche (spatial correlation r = 0.85 with distal_epi across 2,147 valid 200 µm bins), together with expected regional structure for airway and budtip populations. EV-0010 does not adjudicate AT1-maturity (HOPX, AQP5 absent from the 339-gene panel), mesenchymal off-target (VIM, COL1A1, COL3A1 absent), cell-level niche assignment, morphology geometry, or cross-donor replication. Neither EV-0009 nor EV-0010 closes the full multimodal alignment condition of P-0002 on its own.

## Current hold / inadmissibility
EV-0004 (GSE193716 adult primary AT2, pre-culture) remains held under `adult_primary_vs_fetal_caveat`. The imported inadmissibility slice records this as a semantic, not technical, hold: projections are interpretable but adult-primary identity cannot be adjudicated on the current fetal-lung-centered reference without explicit caveat, boundary-stress role, or bridge decision. Future reuse for P-0002 is permitted only under those conditions and is not currently exercised.

## Current bottom line
P-0002 now has two complementary claim-linked support rows. EV-0009 carries trajectory/stage/quality support on the organoid side; EV-0010 carries spatial-architecture support on the fetal reference side. Together they cover two of P-0002's first-class axes. The morphology axis — named explicitly in the P-0002 success condition — is not yet addressed, and cross-donor/cross-stage replication of the spatial finding remains absent. Full multimodal closure is not claimed.

## Next gap
The first morphology-axis corroboration: a derived `support` or `falsifier_candidate` row that measures tissue-architecture or airspace-geometry features from GSM8217894's morphology.ome.tif at a useful resolution (not the sanity-overlay downsample) and ties those features to the distal-epithelial niche already identified in EV-0010 — so that P-0002's morphology first-class axis gains its first registered row.

## Non-goals
This memo does not close P-0002, does not change any contract or workflow rule, does not transition any row between workflow states, does not add or retire evidence rows, does not recreate legacy comparison-world or lifecycle artifacts, and does not introduce new schema or new claim targets.

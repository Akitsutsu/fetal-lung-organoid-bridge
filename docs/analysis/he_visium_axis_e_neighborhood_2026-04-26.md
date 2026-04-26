# He Visium Axis E Neighborhood Read, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `mesenchymal_axis_e_integration_v1.md`
  - `he_visium_spot_metrics_v1.md`
  - `he_fibroblast_axis_e_reference_v1.md`
  - `docs/analysis/axis_e_native_to_organoid_gap_2026-04-26.md`
- input:
  - `12` local He Visium H5AD libraries under
    `/mnt/c/Users/avanc/Desktop/lungs_analysis/data/spatial/visium/E-MTAB-11265/`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

This pass asks a narrower question than the earlier same-spot correlation read:

- not "do epithelial and mesenchymal signals occupy the same Visium spot?"
- but "does mesenchymal signal appear in the **immediate neighboring spot
  context** of epithelial signal?"

The answer is yes.

Across `12` He Visium libraries, immediate spot-neighborhood analysis changes
the Axis E interpretation in an important way:

1. `E1_alveolar_fibro` shifts from **same-spot negative** against
   `Late_tip` / `AT1` / `AT2` to **immediate-neighbor positive**;
2. `E2_myofibro` is already weakly positive at same-spot level and becomes
   **more strongly positive** in immediate-neighbor reads;
3. `E3_pericyte_smc_airway` shows a more selective pattern: positive around
   `AT1` / `AT2`, but near-neutral around `Late_tip`, consistent with a
   vascular / airway-boundary context rather than a universal distal niche;
4. epithelial hotspot spots carry elevated neighboring `E1` and especially
   neighboring `E2`, supporting adjacency rather than co-occupancy as the
   correct Visium interpretation layer.

This does not close positive organoid Axis E support. It does strengthen the
native fetal logic of Axis E by showing that same-spot anti-correlation is
compatible with local neighborhood enrichment.

## Neighborhood Definition

Neighborhoods were computed from each library's `obsm["spatial"]` Visium
coordinates after restricting to in-tissue spots.

- representative nearest-neighbor spacing in a distal library:
  approximately `226` pixels;
- **Ring 1**: spots within `<=260` pixels of the center spot, excluding the
  center spot itself;
- **Ring 2**: annulus `>260` and `<=460` pixels from the center spot.

Operationally, this produces:

- median Ring 1 neighbor count: `6` spots;
- median Ring 2 neighbor count: typically `9-12` spots after edge trimming by
  the in-tissue mask.

This is still spot-scale analysis, not cell-level contact inference. The gain
is that it removes the strict same-spot mixture assumption.

## Metrics Used

- `E1_alveolar_fibro` = `SLT: Alveolar fibro`
- `E1_broad_fibro` = `SLT: Alveolar fibro + SLT: Mid fibro`
- `E2_myofibro` = `SLT: Myofibro 1 + SLT: Myofibro 2 + SLT: Myofibro 3`
- `E3_pericyte_smc_airway` =
  `SLT: Pericyte + SLT: Vascular SMC 1 + SLT: Vascular SMC 2 +`
  `SLT: Late airway SMC + SLT: Early airway SMC 1 +`
  `SLT: Early airway SMC 2`
- epithelial weights:
  - `SLT: Late tip`
  - `SLT: AT1`
  - `SLT: AT2`

These are author-provided spot-level cell2location weights, used here only as
descriptive neighborhood variables.

## Main Finding 1: E1 Flips Sign From Same-Spot To Immediate Adjacency

The strongest result is the sign flip for `E1_alveolar_fibro`.

| E1 versus epithelial metric | same-spot mean Spearman `r` | Ring 1 neighbor mean Spearman `r` | Ring 2 neighbor mean Spearman `r` |
|---|---:|---:|---:|
| `Late_tip` | `-0.2296` | `0.1215` | `0.0951` |
| `AT1` | `-0.1290` | `0.0598` | `0.0980` |
| `AT2` | `-0.2384` | `0.0893` | `0.0818` |

For `AT1`, the neighborhood means are based on the `9` libraries with
non-sparse AT1 weights; `Late_tip` and `AT2` use all `12` libraries.

The interpretive consequence is straightforward:

- same-spot anti-correlation should not be read as evidence **against**
  epithelial-mesenchymal biological coupling;
- at Visium resolution, `E1` and distal epithelial states appear better read
  as **adjacent local compartments** than as same-spot co-mixtures.

## Main Finding 2: E2 Is Also Neighbor-Positive, Often More Strongly

`E2_myofibro` was already weakly positive in earlier same-spot reads. The
neighborhood pass strengthens that pattern.

| E2 versus epithelial metric | same-spot mean Spearman `r` | Ring 1 neighbor mean Spearman `r` | Ring 2 neighbor mean Spearman `r` |
|---|---:|---:|---:|
| `Late_tip` | `0.0712` | `0.1395` | `0.0908` |
| `AT1` | `0.1221` | `0.1931` | `0.1269` |
| `AT2` | `0.1500` | `0.1892` | `0.0936` |

Again, `AT1` is informative in `9` libraries, whereas `Late_tip` and `AT2`
remain informative across all `12`.

This makes E2 the most robust positive adjacency signal in this read,
especially around `AT1` and `AT2`.

## Main Finding 3: E3 Is Selective Rather Than Uniform

`E3_pericyte_smc_airway` behaves differently from both `E1` and `E2`.

| E3 versus epithelial metric | same-spot mean Spearman `r` | Ring 1 neighbor mean Spearman `r` | Ring 2 neighbor mean Spearman `r` |
|---|---:|---:|---:|
| `Late_tip` | `-0.3122` | `0.0406` | `0.0394` |
| `AT1` | `-0.0029` | `0.1869` | `0.0997` |
| `AT2` | `-0.1929` | `0.1136` | `0.0502` |

For `AT1`, the neighborhood means are again based on the `9` libraries with
non-sparse AT1 weights; `Late_tip` and `AT2` use all `12` libraries.

The key point is not simply that E3 becomes positive. It is that the
neighborhood pattern is **selective**:

- around `AT1` and `AT2`, `E3` becomes moderately positive;
- around `Late_tip`, `E3` moves from same-spot negative to near-neutral only.

That is biologically plausible for a pericyte / smooth-muscle / airway-boundary
axis. Unlike `E1`, it should not be expected to behave like a broad distal
epithelial support layer everywhere in the tissue.

## Main Finding 4: Epithelial Hotspots Carry Elevated Neighboring E1/E2/E3

To make the neighborhood pattern more intuitive, this pass also compared
top-decile epithelial-center spots against the remaining spots within each
library.

### Ring 1 enrichment summary

| Epithelial hotspot | Neighbor metric | Mean hotspot / background ratio | Median hotspot / background ratio |
|---|---|---:|---:|
| `Late_tip` | `R1_E1` | `1.1761x` | `1.1594x` |
| `Late_tip` | `R1_E2` | `1.2021x` | `1.1993x` |
| `AT1` | `R1_E1` | `1.3085x` | `1.0707x` |
| `AT1` | `R1_E2` | `1.9170x` | `1.5065x` |
| `AT1` | `R1_E3` | `1.1524x` | `1.2917x` |
| `AT2` | `R1_E1` | `1.1543x` | `1.0927x` |
| `AT2` | `R1_E2` | `1.4189x` | `1.3837x` |
| `AT2` | `R1_E3` | `1.1169x` | `1.1514x` |
| `Late_tip` | `R1_E3` | `0.9117x` | `0.9340x` |

Coverage note:

- `Late_tip` and `AT2` hotspot summaries use all `12` libraries.
- `AT1` hotspot summaries use the `4` libraries with stable top-decile AT1
  hotspot sets after excluding zero-dominated early libraries.

The cleanest neighborhood read is:

- `AT1` hotspots carry especially elevated neighboring `E2`;
- `AT2` hotspots carry elevated neighboring `E2` and modestly elevated
  neighboring `E1`;
- `Late_tip` hotspots also show local enrichment of both `E1` and `E2`;
- `E3` is different: it rises around `AT1` / `AT2`, but not around `Late_tip`.

This is consistent with the idea that mesenchymal support is locally adjacent
even when the exact same spot is dominated by epithelial signal.

## Stage And Region Notes

The positive neighborhood pattern is not perfectly uniform.

- In early whole-lung libraries (`pcw12`-`pcw14`), `AT1` weights are often too
  sparse for stable same-sample AT1 neighborhood reads, and `E1` versus
  `AT1`/`AT2` can remain weak or slightly negative.
- By `pcw16`-`pcw17`, whole-lung libraries show clearer positive Ring 1
  adjacency for `E1` versus `Late_tip` / `AT2` and for `E2` versus all three
  epithelial metrics.
- `E3` is the most region-sensitive sub-axis in this pass: whole-lung
  libraries show positive Ring 1 adjacency for `AT1` / `AT2`, but the single
  proximal `pcw19` sample is weak or negative for all three epithelial reads,
  reinforcing that E3 carries boundary-context information rather than a
  simple universal distal-support signal.
- The single `pcw19` proximal sample shows the strongest positive values, but
  should not be overread as distal-alveolar closure because it is regionally
  distinct from the distal question. This point applies to `E1` / `E2`, but
  the proximal sample does not strengthen `E3`.
- `pcw20` distal libraries remain positive but modest for `E1`, while `E2`
  stays more clearly positive around `AT1` / `AT2`.

So the right reading is not "uniform co-localization everywhere." It is
"repeatable immediate-neighbor enrichment that becomes clearer once spot
co-occupancy is no longer the only interpretation layer."

## What This Supports

This document supports five bridge-side uses.

1. He Visium same-spot anti-correlation does **not** collapse Axis E.
2. Native fetal `E1` is compatible with local adjacency to distal epithelial
   states even when same-spot correlation is negative.
3. Native fetal `E2` shows even clearer immediate-neighbor enrichment around
   `AT1` / `AT2`, making myofibro-like context a plausible local companion
   layer in late fetal spatial tissue.
4. Native fetal `E3` is not interchangeable with `E1` / `E2`; it behaves more
   like a selective perivascular / airway-boundary adjacency layer, strongest
   around `AT1` / `AT2` and not broadly around `Late_tip`.
5. The paper can more confidently say that mesenchymal tissue-context support
   is a neighborhood-scale question, not only a same-spot mixture question.

## What This Does Not Support

This document does **not** support:

- cell-level physical contact claims;
- claim closure for positive organoid-side `E1` / `E2` / `E3` support;
- independent cross-study replication, since He Visium remains within the He /
  Rawlins fetal atlas study family;
- reinterpretation of Visium neighborhoods as direct proof of alveolar niche
  sufficiency.

## Bridge Implication

The bridge can now make a sharper mesenchyme-side statement:

- native fetal lung carries positive `E1` / `E2` mesenchymal states;
- native fetal `E3` carries a different, more selective neighborhood logic
  rather than the same broad distal-support pattern as `E1`;
- same-spot Visium anti-correlation should not be mistaken for biological
  separation;
- immediate-neighbor Visium analysis recovers local mesenchymal enrichment
  around distal epithelial states, but that enrichment is sub-axis-specific;
- current organoid bridge datasets still do not close that mesenchymal layer.

That is a stronger biology-first account than either "stromal markers are
everywhere" or "Visium anti-correlation disproves niche support."

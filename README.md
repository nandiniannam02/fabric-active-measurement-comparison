# perfSONAR on FABRIC: Automated Analysis and Cross-Tool Network Measurement

This repository extends perfSONAR experiments on the FABRIC Testbed and evaluates perfSONAR alongside RIPE Atlas and Grafana Synthetic Monitoring. The notebook organization follows the original FABRIC recipe style: deployment/setup cells are kept next to executable analysis cells, and major successful outputs are retained for inspection. The upstream recipe structure used as a reference includes dedicated notebooks plus `node_tools`, `psconfig`, and `images`.

## Repository layout

- `perfsonar/` — three FABRIC/perfSONAR experiment notebooks, their automation scripts, pSConfig helpers, images, and a consolidated contribution summary.
- `cross_tool_study/` — complete perfSONAR/RIPE Atlas/Grafana normalization and analysis notebook, raw/normalized measurement files, final 24-hour integrated dataset, statistics, figures, and controlled-impairment results.
- `REPRODUCIBILITY.md` — execution requirements and which parts require a live FABRIC/Grafana environment.
- `RESULTS.md` — concise verified findings.

## perfSONAR extensions

Each of the three perfSONAR experiment notebooks retains the core deployment workflow and adds four analysis functions:

1. automatic archive/path performance analysis;
2. project-defined path/site quality scoring;
3. archive-derived degraded-path detection;
4. automated experiment summaries.

The quality scores and anomaly thresholds are project-defined analytical methods, not official perfSONAR metrics.

## Cross-tool case study

The cross-tool notebook documents how measurements were normalized into a common schema, how each intermediate/final CSV was generated, and how the final analysis was performed. Major successful table and figure outputs are stored in the notebook.

The common normal-condition study uses six IPv6 targets and a 24-hour window. A controlled `tc netem` experiment separately evaluates delay, packet-loss detection, and recovery behavior.

## Running the notebooks

The deployment notebooks require FABRIC credentials, FABlib, and live resources. The cross-tool analysis can be inspected from the included raw/normalized files; live Grafana/OpenSearch collection cells require the corresponding service access. See `REPRODUCIBILITY.md`.

## Attribution

The deployment structure builds on the public FABRIC perfSONAR recipes. This repository adds the automated archive analysis and the cross-platform measurement study.

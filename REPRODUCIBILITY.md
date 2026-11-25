# Reproducibility

## Environment

### perfSONAR/FABRIC notebooks
Run in a FABRIC Jupyter environment with FABlib configured. The notebooks provision or reconnect to FABRIC slices, install the perfSONAR stack using the included `node_tools`, configure pSConfig, and query TimescaleDB/OpenSearch archives. Resource/site availability can change, so FABRIC provisioning outputs will differ on a new run.

### Cross-tool notebook
The notebook is under `cross_tool_study/`. Run it with that directory as the working directory. Core offline dependencies are `pandas`, `numpy`, `matplotlib`, and `requests`.

The repository includes:
- raw perfSONAR JSON for the final RTT/traceroute window;
- Grafana raw and normalized CSV exports used by the study;
- RIPE Atlas normalized exports plus original measurement exports;
- the canonical `cross_tool_analysis/final_24h/all_tools_final_24h_normalized_clean.csv`;
- all verified final statistics and figures.

Live collection cells for Grafana Prometheus/Loki or perfSONAR OpenSearch require valid credentials and an active service. Tokens are intentionally not stored in this repository. Those cells use interactive credential entry or credentials stored on the deployed perfSONAR nodes.

## Recommended execution path

1. Open `cross_tool_study/cross_tool_analysis.ipynb`.
2. Review the schema/mapping cells.
3. Run normalizer and raw-to-normalized cells when the corresponding raw files are available.
4. Use the included canonical 24-hour CSV to reproduce final statistics and agreement analyses without live service access.
5. Compare generated tables with `cross_tool_study/cross_tool_analysis/final_statistics/` and figures with `cross_tool_study/cross_tool_analysis/figures/`.

## Outputs retained in notebooks

Successful outputs for major setup validation, archive summaries, normalization checks, final statistics tables, and plots are intentionally retained. Error traces, credential dumps, retry/debug cells, notebook checkpoints, and large deployment logs are excluded.

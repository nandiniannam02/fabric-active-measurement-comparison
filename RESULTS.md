# Results Summary

## perfSONAR automated analysis

- TACC→NCSA path experiment: Net1 quality score 99.90/100; Net2 100.00/100. Net2 had the slightly higher aggregate score, while Net1 had fewer detected degradation episodes (17 vs. 25).
- SEAT→TACC: quality score 71.88/100 (Moderate). Highest abnormal-observation rate: low throughput, 1.647%.
- DALL→SEAT: quality score 82.43/100 (Good). Highest abnormal-observation rate: low throughput, 4.004%.

## Cross-tool normal-condition study

- Canonical integrated dataset: 3,456 rows across perfSONAR, RIPE Atlas, and Grafana.
- RTT agreement was close for most destinations; RIPE-Dallas showed a distinct perfSONAR–RIPE Atlas offset of about 1.4 ms.
- Median traceroute hop counts agreed strongly for most destinations.
- perfSONAR exposed greater full-path variation; hop-count analysis indicates that some full-path churn is consistent with interface/load-balancing variation rather than structural route changes.

## Controlled impairment

- RIPE Atlas captured the short +50 ms delay and measured an RTT increase of about 49.7 ms.
- perfSONAR first detected the 20% packet-loss condition after about 7 min 12 s; Grafana after about 18 min 55 s.
- perfSONAR showed the fastest observed post-loss recovery (about 3 min 50 s).

See the notebooks and CSVs for complete target-level results and methodology caveats.

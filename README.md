# Congressional Stance Discovery & Transparency

A **text-first, context-aware** pipeline that discovers interpretable **stance themes** across U.S. bills and produces **transparent vote-support rationales**.

This repo is designed to be **poster/reader friendly**: it contains a curated set of *artifacts* (features, cluster cards, evidence plots, metrics, and example rationales) that can be inspected without running the full pipeline.

## Open these first (2 minutes)
- **Cluster cards (human-readable):** `artifacts/clusters/cluster_cards.md`
- **k selection evidence:** `artifacts/evidence/k_sweep_summary.png`
- **Per-cluster silhouette:** `artifacts/evidence/silhouette_per_cluster_sorted.png`
- **Example rationales:** `artifacts/rationales/new_explanations_table.csv`
- **Headline metrics:** `artifacts/metrics/metrics_for_abstract.csv`

## Repo layout
- `artifacts/` — the auditable artifact bundle (see `artifacts/README.md`)
- `figures/` — final plots used in the poster
- `poster/` — poster source/output (add your `ncrc_poster.tex` + PDF here)

## Data provenance
See `DATA_SOURCES.md` for the GovInfo Bulkdata collections used.

## License
See `LICENSE`.

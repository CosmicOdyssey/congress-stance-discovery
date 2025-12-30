# Artifact Bundle — Congressional Stance Discovery & Transparency

This folder contains a **minimal, read-only artifact bundle** for the project.

It includes:
1. **Features** (numerical bill representations)
2. **Clusters** (interpretable stance/theme groupings)
3. **k-selection evidence** (why a particular number of clusters was chosen)
4. **Metrics** (headline model performance)
5. **Rationales** (transparent explanations for predictions)

These artifacts are meant to be **inspectable without running the full pipeline**.

---

## 1) Features

### `features/bill_fused.npy`
- **What it is:** Final fused feature matrix for bills, combining **text embeddings** (SBERT on bill titles/summaries) and **context/graph features** (e.g., degrees/PageRank, sponsor/cosponsor/vote counts).
- **Shape:** `(num_bills, D_fused)` — one row per bill.
- **Example:**
  ```python
  import numpy as np
  X = np.load("artifacts/features/bill_fused.npy")
  print(X.shape)
  ```

### `features/coords_fused_pca2.csv`
- **What it is:** 2-D PCA projection of the fused bill vectors (for scatter plots).
- **Typical columns:** `bill_id`, `x`, `y` (and optionally `cluster`).

---

## 2) Clusters

### `clusters/cluster_cards_with_summaries.csv`
A table of **cluster “cards”**, one row per cluster. Typical columns include:
- `cluster`, `size`, `sil`
- `top_terms` (TF–IDF terms)
- `summary` (short description)
- exemplar bill titles/IDs

### `clusters/cluster_cards.md`
A **human-readable Markdown** rendering of selected cluster cards (ready to paste into a poster/report).

---

## 3) k-selection & silhouette evidence

### `evidence/k_sweep_summary.png`
A compact summary of the **k-sweep** (e.g., k = 25/30/35) with quality/stability indicators.

### `evidence/silhouette_per_cluster_sorted.png`
Per-cluster **local silhouette** values for the chosen k (sorted), highlighting tight vs. noisier clusters.

---

## 4) Metrics

### `metrics/metrics_for_abstract.csv`
A compact table of headline metrics (e.g., AUC/AP/F1) used directly in the poster/abstract.

---

## 5) Rationales

### `rationales/new_explanations_table.csv`
Instance-level, **human-readable rationales** for (member, bill) predictions (includes predicted support, similarity signals, and a short explanation).

### `rationales/rationales_example.csv`
A small curated set of example rationales (useful for quick inspection).

---

## Poster figures (outside this folder)
Final poster-ready plots live in `../figures/` (e.g., PR curves, confusion matrix, scatter).

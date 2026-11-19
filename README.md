# Agglomerative Hierarchical Clustering on BEED

[![Live demo](https://img.shields.io/badge/Live%20demo-rendered%20notebook-ff5a1f?style=for-the-badge)](https://eeg-agglomerative-clustering.vercel.app)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/parthpawar1117/eeg-agglomerative-clustering/blob/main/agglomerative_clustering_beed.ipynb)

STAI205 (Machine Learning & Algorithms 2) mid-term project by **Parth Pawar**, Vijaybhoomi University, April 2026.

Agglomerative hierarchical clustering implemented **from scratch with NumPy** on the Bangalore EEG Epilepsy
Dataset (BEED), verified against scikit-learn, and made interpretable with a decision-tree surrogate.

## Results

| Phase | What it does | Result |
|---|---|---|
| 0 · Data | Stratified sample of 300 EEG segments (75 per class), 16 standardised features | 8,000 × 17 source rows |
| 1 · From scratch | Ward-linkage agglomerative clustering in NumPy (k = 4), PCA visualisation | full merge history |
| 2 · Verification | Same clustering with scikit-learn's `AgglomerativeClustering(linkage="ward")` | **100%** agreement (300/300), NMI 1.0 |
| 3 · Surrogate | Decision tree trained on the cluster labels to explain them as rules | **96.67%** test accuracy |

## Run it

- **In the browser:** click *Open in Colab* above and choose *Runtime → Run all*. The notebook reads the
  dataset straight from this repo, so no upload is needed.
- **Locally:**
  ```bash
  pip install -r requirements.txt
  jupyter notebook agglomerative_clustering_beed.ipynb
  ```

## Dataset

`data/BEED_Data.csv` is the **BEED: Bangalore EEG Epilepsy Dataset** by Najmusseher and P. K. Nizar Banu,
from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/1134/beed+bangalore+eeg+epilepsy+dataset)
(DOI [10.24432/C5K33B](https://doi.org/10.24432/C5K33B)), redistributed under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). See `data/DATA_LICENSE.md`.

This is unsupervised clustering for coursework. It is not a diagnostic tool and makes no clinical claims.

# Categorizing Trends in Science — arXiv Topic Clustering

**Course:** DLBDSMLUSL01 — Machine Learning: Unsupervised Learning and Feature Engineering
**Case Study:** Task 3 — Categorizing Trends in Science

## Goal
Reduce a large, high-dimensional archive of scientific paper abstracts (arXiv) into
homogeneous, interpretable clusters representing current research trends, using
dimensionality reduction and clustering techniques, and provide visualizations that
preserve the main structure of the data.

## Data
Source: [arXiv metadata dataset on Kaggle](https://www.kaggle.com/Cornell-University/arxiv)
(also available via the SharePoint link in the case study PDF).

The full dataset is ~4GB / 2M+ papers, so this project works with a **filtered subset**
(see `notebooks/01_data_acquisition_eda.ipynb`) — e.g. a specific set of categories
and/or a recent date range — to keep the analysis tractable and reproducible on a
laptop. The filtering criteria and justification are documented in that notebook.

Raw data is NOT committed to this repo (too large, not mine to redistribute) — see
`.gitignore`. To reproduce: download `arxiv-metadata-oai-snapshot.json` from Kaggle,
place it in `data/raw/`, then run the notebooks in order.

## Pipeline / Repo Structure
```
notebooks/
  01_data_acquisition_eda.ipynb      # load, filter, explore
  02_preprocessing.ipynb             # text cleaning
  03_feature_engineering.ipynb       # TF-IDF / embeddings
  04_dimensionality_reduction.ipynb  # PCA / UMAP / t-SNE
  05_clustering.ipynb                # KMeans / HDBSCAN + evaluation
  06_cluster_interpretation.ipynb    # top terms, trends over time, visuals
src/
  preprocessing.py                   # reusable text-cleaning functions
  features.py                        # vectorization helpers
reports/
  case_study_report.docx             # final written documentation
data/
  raw/                                # gitignored — original download
  processed/                          # cleaned/intermediate data (small samples may be tracked)
```

## How to run
1. `pip install -r requirements.txt`
2. Download the dataset into `data/raw/`
3. Run notebooks 01 → 06 in order
4. Compile findings into `reports/case_study_report.docx`

## Status
- [x] Stage 1: Project setup
- [ ] Stage 2: Data acquisition & EDA
- [ ] Stage 3: Preprocessing
- [ ] Stage 4: Feature engineering
- [ ] Stage 5: Dimensionality reduction
- [ ] Stage 6: Clustering
- [ ] Stage 7: Cluster interpretation
- [ ] Stage 8: Report & polish
# Arvix-trends-scaffold

# RESEARCH_MAP

Interactive literature maps of causal machine learning and interpretability research. Each map is a single self-contained HTML page (no build step), served with GitHub Pages: hover a dot to see a paper, click a topic to isolate it, and search the full reading list by title, summary or author.

## Maps

| # | Topic | Papers | Topics | Live link |
|---|---|---:|---:|---|
| 1 | **Causal Inference** | 5,627 | 21 | https://na679723.github.io/RESEARCH_MAP/causal-inference-atlas_1.html |
| 2 | **Causal Representation Learning** | 703 | 20 | https://na679723.github.io/RESEARCH_MAP/ |
| 3 | **Causal Reinforcement Learning** | 1,061 | 20 | https://na679723.github.io/RESEARCH_MAP/causal-reinforcement-learning.html |
| 4 | **Causal Mediation Analysis** | 884 | 20 | https://na679723.github.io/RESEARCH_MAP/causal-mediation-analysis.html |
| 5 | **Counterfactual Reasoning** | 1,334 | 20 | https://na679723.github.io/RESEARCH_MAP/counterfactual-reasoning.html |
| 6 | **Causal Effect Heterogeneity** | 1,242 | 20 | https://na679723.github.io/RESEARCH_MAP/causal-effect-heterogeneity.html |
| 7 | **Causal Fairness** | 850 | 19 | https://na679723.github.io/RESEARCH_MAP/causal-fairness.html |
| 8 | **Mechanistic Interpretability** | 1,549 | 20 | https://na679723.github.io/RESEARCH_MAP/mechanistic-interpretability.html |
| 9 | **Causal Abstraction** | 592 | 20 | https://na679723.github.io/RESEARCH_MAP/causal-abstraction.html |

Also: **Fairness in ML Topic Map** — 1,751 fairness and bias papers (2014–2026) in six themes: https://na679723.github.io/RESEARCH_MAP/topic_map.html

## Searching

Maps 2–9 share the same search box above the reading list:

- All words must match: `sparse autoencoder`
- Exact phrase: `"counterfactual fairness"`
- Exclude a word: `causal -fairness`
- One field only: `author:pearl`, `title:bandit`, `venue:neurips`, `year:2024`
- Filter by year range, keep only papers with a link, and sort by best match, newest, oldest or title
- The map and topic counts follow the search, matches are highlighted, and the URL updates so a search can be shared as a link (e.g. `causal-fairness.html#q=graph&from=2023`)
- Press `/` to jump to the search box

## How the maps were made

1. **Collect.** For each topic, several parallel web-search passes looked for papers from different angles (for example theory, methods, applications and critiques), drawing on arXiv, OpenReview, journals, proceedings, the ML Anthology, author pages and curated reading lists. Web search was rate-limited, so the passes also harvested papers from the reference lists of surveys and key papers. Duplicate titles were merged.
2. **Cluster.** Each paper's title (weighted twice) and a short paraphrased summary were turned into TF-IDF vectors (unigrams and bigrams), reduced to 100 dimensions with LSA, and grouped with k-means; k was chosen by the best cosine silhouette between 8 and 20.
3. **Label.** Keywords come from class-based TF-IDF; each topic name (e.g. "Counterfactual fairness", "Sparse autoencoders") was written by reading the cluster's keywords and member titles.
4. **Visualize.** The map is a UMAP projection of the same vectors, lightly guided by the cluster labels so each topic reads as one region. Distances between regions are approximate.

The Causal Inference atlas (#1) was built separately from arXiv preprints and the most-cited OpenAlex works matching "causal inference".

## Caveats

- Collections are broad but not exhaustive, and coverage leans toward work that appears in surveys and reading lists.
- Summaries are paraphrases, some written from titles or citing papers rather than the original abstract.
- Some entries found only in reference lists have no link.
- Each map includes some neighbouring work where it borrows the topic's ideas (for example recommender debiasing in the mediation map).

Collected October 2026.

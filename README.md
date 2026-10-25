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
| + | **Fairness in ML** (2014–2026, six themes) | 1,751 | 26 | https://na679723.github.io/RESEARCH_MAP/topic_map.html |

## Using the maps

All maps use the same layout and controls.

**Zoom and pan**

- Zoom with the + / − buttons, a two-finger pinch, Ctrl/⌘ + scroll (or trackpad pinch), or a double-click; drag to pan once zoomed in
- Clicking a topic in the list zooms to it; "Zoom to results" frames the papers that match a search
- Zoom in past about 3× and paper titles appear next to the dots
- "Show on map" on any paper in the list flies the map to it and highlights it; hovering a paper in the list highlights its dot

**Search**

- All words must match: `sparse autoencoder`
- Exact phrase: `"counterfactual fairness"`
- Either word: `bandit OR imitation`
- Exclude a word: `causal -fairness`
- One field only: `author:pearl`, `title:bandit`, `venue:neurips`, `year:2024`
- Suggestions for authors, venues and topics appear as you type (arrow keys + Enter to pick)
- Filter by year range, venue, or papers with a link; the year histogram shows matches per year and a click on a bar filters to that year
- Click an author or venue in a result to search for it; misspelled words get a "Did you mean" suggestion
- The map and topic counts follow the search, matches are highlighted, and "Download results (CSV)" exports the current list
- The URL updates as you search, so a search can be shared as a link (e.g. `causal-fairness.html#q=graph&from=2023`)
- Press `/` to jump to the search box

## How the maps were made

1. **Collect.** For each topic, several parallel web-search passes looked for papers from different angles (for example theory, methods, applications and critiques), drawing on arXiv, OpenReview, journals, proceedings, the ML Anthology, author pages and curated reading lists. Web search was rate-limited, so the passes also harvested papers from the reference lists of surveys and key papers. Duplicate titles were merged.
2. **Cluster.** Each paper's title (weighted twice) and a short paraphrased summary were turned into TF-IDF vectors (unigrams and bigrams), reduced to 100 dimensions with LSA, and grouped with k-means; k was chosen by the best cosine silhouette between 8 and 20.
3. **Label.** Keywords come from class-based TF-IDF; each topic name (e.g. "Counterfactual fairness", "Sparse autoencoders") was written by reading the cluster's keywords and member titles.
4. **Visualize.** The map is a UMAP projection of the same vectors, lightly guided by the cluster labels so each topic reads as one region. Distances between regions are approximate.

Two maps were built differently and later converted to this common format, keeping their own papers, topics and map positions:

- **Causal Inference** (#1) comes from every arXiv preprint whose title or abstract contains "causal inference" plus the 2,000 most-cited OpenAlex works matching the phrase, clustered with non-negative matrix factorization into 21 topics in three families. It has no paper summaries; OpenAlex entries show their citation count.
- **Fairness in ML** comes from an earlier topic map of fairness and bias papers at machine learning, NLP and vision venues, with 26 topics in six themes. It has titles, first authors, venues and years but no links or summaries.

## Caveats

- Collections are broad but not exhaustive, and coverage leans toward work that appears in surveys and reading lists.
- Summaries are paraphrases, some written from titles or citing papers rather than the original abstract.
- Some entries found only in reference lists have no link.
- Each map includes some neighbouring work where it borrows the topic's ideas (for example recommender debiasing in the mediation map).

Collected October 2026.

# ⚽ European Soccer Team Style Analysis & Championship Correlation

> **Data-driven tactical analysis of European football clubs.**  
> We extract team-level playing styles from match data (PCA + K-Means) and show how tactical archetypes correlate with championship success.

---

## 🔥 Quick highlights (TL;DR)
- **Goal:** Discover team playing-style archetypes using unsupervised learning and measure which styles win titles.
- **Approach:** Aggregate match stats per team → Standardize → PCA for visualization → K-Means for clustering → correlate clusters with champions.
- **Key finding:** “Offensive Titans” and “Balanced Competitors” produce the most championships in our sample; pure defensive strategies are less likely to win.
- **Deliverable:** `refined_report.pdf` — polished, multi-page report with visuals and recommendations.

---

## 🧭 Demo (visuals & PDF)
You can preview the main deliverable: **`European Soccer Team Style Analysis Report pdf.pdf`** — a clean report with:
- executive summary
- PCA scatter plot (teams in 2D style space)
- bar chart: championships by cluster
- insights & recommendations

> Link: `./European Soccer Team Style Analysis Report pdf.pdf`

---

## 📈 Methodology (concise)
1. **Data loading:** Read `Match` and `Team` tables from the SQLite DB.  
2. **Feature engineering:** Aggregate per-team averages (goals for/against, shots on/off, fouls). Parse event-level XML for possession when available.  
3. **Preprocessing:** Fill/drop missing values, StandardScaler (z-score).  
4. **Dimensionality reduction:** PCA → 2 components for visualization and interpretability.  
5. **Clustering:** K-Means (K=3) to derive tactical archetypes (named after cluster behaviour).  
6. **Scoring:** Compute season points and champions per season, correlate cluster membership with title wins.  
7. **Visuals & report:** Generate PCA scatter, bar charts, and produce final PDF report.

## Key results (summarized)
1. **Clusters discovered:** Offensive Titans, Defensive Walls, Balanced Competitors
2. **Championship counts (sample):** Offensive Titans → 4 | Defensive Walls → 1 | Balanced Competitors → 3
3. **Interpretation:** While defensive solidity helps, teams that produce more goals (offensive efficiency) tend to have better championship outcomes in this dataset.

## Limitations & next steps
  **Current limitation:** Many event-level metrics are stored as XML strings inside columns (e.g., possession, shot details). These must be parsed to gain per-match numeric features.

## Data & credits
Source: European Soccer Database — Kaggle (hugomathien/soccer).
Acknowledgements: Thanks to data providers and the open sports analytics community.


**Prepared by:** David Oladipupo
**Email:** daveed3k3k@gmail.com



# Amazon ML Challenge 2026 — Business Entity Resolution

## Project Summary

Developed a scalable **entity resolution and business matching system** for the Amazon ML Challenge 2026. The objective was to identify matching business records across multiple large-scale data sources despite variations in names, addresses, formatting, and missing information.

The pipeline was designed to efficiently process **millions of business records** while balancing matching accuracy and computational efficiency.

## Approach

- **Data Preprocessing:** Cleaned and normalized business names and addresses by standardizing abbreviations, removing punctuation, and handling text variations.
- **Candidate Generation:** Applied name and address-based blocking to reduce the search space before detailed matching.
- **Feature Engineering:** Generated exact-match and fuzzy-similarity features for business names and addresses, along with country matching.
- **Machine Learning:** Trained a `HistGradientBoostingClassifier` to classify candidate pairs as **MATCH** or **NON-MATCH**.
- **Threshold Optimization:** Evaluated different prediction thresholds to balance precision and recall.
- **Validation:** Implemented checks for duplicate records, invalid IDs, candidate consistency, and final prediction integrity.

## Results

- **99.70% F1-score** on internal pair-level evaluation
- **99.71% Precision**
- **99.69% Recall**
- **99.94% ROC-AUC**
- **~95.03% diagnostic blocking recall**
- **0.482 Amazon ML Challenge 2026 leaderboard score**

## Technologies

**Python • Pandas • NumPy • Scikit-learn • RapidFuzz • SQLite • Machine Learning • NLP • Entity Resolution**

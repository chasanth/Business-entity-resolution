# Entity Matching Model

An ML-based entity matching system that determines whether two entity records refer to the same real-world entity.

The project uses entity attributes such as name, address, and country to generate similarity features and classify entity pairs as MATCH or NON-MATCH.

---

## Problem Statement

Entity matching is the task of identifying whether two records represent the same real-world entity.

For example:

Record A:
- Name: Apple Inc
- Address: One Apple Park Way
- Country: USA

Record B:
- Name: Apple Inc.
- Address: One Apple Park Way
- Country: USA

The model predicts whether these two records belong to the same entity.

---

## Approach

The complete pipeline is:

Dataset
→ Entity Pair Generation
→ Feature Engineering
→ Data Cleaning
→ Train/Validation/Test Split
→ Class Balancing
→ Model Training
→ Threshold Analysis
→ Evaluation
→ Model Saving
→ Inference

---

## Features

Five features were used for entity matching:

| Feature | Description |
|---|---|
| `name_exact` | Exact match between entity names |
| `name_similarity` | Similarity between entity names |
| `address_exact` | Exact match between addresses |
| `address_similarity` | Similarity between addresses |
| `country_match` | Whether the countries match |

---

## Dataset Preparation

The dataset contains positive and negative entity pairs.

### Positive pairs

Pairs known to represent the same entity.

### Negative pairs

Pairs generated from different entities to represent non-matches.

The final combined dataset contained:

- Positive pairs: 7,763,365
- Negative pairs: 500,000
- Total pairs: 8,263,365

After removing records with missing matched entity IDs from the positive data, the final training dataset was prepared for modeling.

---

## Data Split

The dataset was divided into:

- Training: 6,510,692 samples
- Validation: 813,836 samples
- Test: 813,837 samples

The training data was balanced before model training.

### Balanced Training Set

- Positive: 400,000
- Negative: 400,000
- Total: 800,000

The validation and test sets were retained separately for unbiased evaluation.

---

## Model

A gradient-boosting classification model was trained using the five engineered features.

The trained model is saved as:

```text
entity_matching_model.pkl

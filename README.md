# Bank Telemarketing Campaign Optimization

**Project Status:** Complete (MVP Delivered)
**Primary Tech Stack:** Python, LightGBM, XGBoost, Scikit-learn, ADASYN

## Executive Summary
Direct marketing campaigns in the banking sector often suffer from low conversion rates and high operational costs. This project leverages machine learning to solve the resource allocation problem by predicting which clients will subscribe to a term deposit.

By analyzing customer demographics, economic indicators, and past interaction history, the system identifies high-probability leads. This allows financial institutions to pivot from indiscriminate cold calling to a targeted, data-driven strategy that maximizes Return on Investment (ROI).

## Key Performance Metrics
The model was rigorously tested on unseen data to ensure generalization. The minimal variance between public and private evaluation scores indicates a robust model with no significant overfitting.

| Metric | Score | Note |
| :--- | :--- | :--- |
| **F1 Macro (Public)** | **0.755** | Optimized for minority class detection |
| **F1 Macro (Private)** | **0.745** | Demonstrates stability on unseen data |
| **Accuracy** | **~91%** | Maintained high overall precision |

## Technical Architecture

### 1. Handling Severe Class Imbalance
The dataset presented a classic "needle in a haystack" problem where only a small fraction of clients subscribed. Standard models would ignore these positive cases. I mitigated this by implementing **ADASYN (Adaptive Synthetic Sampling)**, which generates synthetic data points for the minority class to create a balanced learning environment.

### 2. Feature Optimization
To reduce noise and computational cost, I utilized **Recursive Feature Elimination (RFE)**. This technique iteratively removed the weakest features to isolate the signals that actually drive customer decisions, such as call duration and specific economic indices.

### 3. Model Ensemble
I orchestrated an ensemble approach using **LightGBM** and **XGBoost**. These gradient boosting frameworks were chosen for their speed and ability to handle complex, non-linear relationships in tabular data better than traditional regression models.

## Strategic Business Insights
Beyond prediction, the model offers interpretability that can shape future marketing campaigns.

*   **Demographic Targeting:** The analysis reveals that "retired" individuals and "blue-collar" workers show distinct engagement patterns. Tailoring scripts to address wealth preservation for the former and savings growth for the latter could improve conversion.
*   **Timing Matters:** There is a strong correlation between call duration and success. However, the model suggests that contact frequency (number of calls) has diminishing returns, implying that agent persistence should be capped to preserve brand reputation.

## Usage
This project is structured as a Jupyter Notebook for transparency and reproducibility.

1.  Clone the repository.
2.  Install dependencies: `pip install pandas numpy scikit-learn lightgbm xgboost imbalanced-learn matplotlib seaborn`
3.  Open the `.ipynb` file in Jupyter Lab or Google Colab to view the full pipeline, from EDA to Model Evaluation.

---
*Author: Eram Nishat*

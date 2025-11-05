# 🌿 Classifying Corporate ESG Performance Using Machine Learning

**Golib Sanaev — November 2025**

---

## 🧭 Overview

`esg-classification` explores the relationship between **Environmental, Social, and Governance (ESG)** indicators and firm-level financial performance using modern machine learning techniques.

The project uses the **ESG and Financial Performance Dataset** from *Kaggle* (shared by [Shriyash Jagtap](https://www.kaggle.com/shriyashjagtap)), a structured dataset simulating corporate ESG metrics and financial outcomes.  
It applies algorithms such as **Logistic Regression**, **Random Forests**, and **Gradient Boosting (XGBoost)** to classify firms according to sustainability-driven performance patterns.

This work serves both as:
- a **learning framework** for applied machine learning classification, and  
- an **analytical study** of how ESG pillars interact with firm-level financial data.

---

## 🧩 Project Structure

| Notebook | Title | Description |
|-----------|--------|-------------|
| **01 — Data Exploration and Preparation** | Data simulation and preprocessing | Generates or loads the ESG dataset, handles feature engineering, adds noise to mimic real-world data variability, and constructs the target label (`ESG_Class`). |
| **02 — Modeling and Classification** | Model training & evaluation | Trains Logistic Regression, Random Forest, and XGBoost classifiers. Evaluates accuracy, precision, recall, F1, and ROC-AUC. |
| **02b — Realistic Modeling Refinement** | Controlled noise introduction | Adds measurement noise and inter-pillar correlations to improve model realism. |
| **03 — Model Evaluation and Interpretation** | Threshold tuning, calibration, explainability | Includes cross-validation, threshold trade-offs, reliability curves, and SHAP-based explainability. |
| **04 — ESG Insights and Reporting** | Scenario analysis & interpretability | Analyzes feature-level and grouped SHAP values to understand what drives ESG classifications. |
| **05 — ESG Reporting & Visualization Dashboard** | Interactive analytics | Builds a live interactive dashboard using `ipywidgets` and `plotly`, allowing scenario-based experimentation. |

---

## 🎯 Objectives

- Examine how ESG indicators relate to firm financial outcomes.  
- Benchmark several classification algorithms on ESG features.  
- Identify which ESG dimensions (E, S, or G) most strongly influence firm classification.  
- Provide interpretable, reproducible, and interactive model evaluation results.

---

## 🧠 Key Learnings

### 🔹 Data Simulation & Noise Modeling
- Introduced realistic **measurement noise and correlation** between ESG pillars.  
- Simulated imperfections to mimic real-world ESG ratings behavior.  

### 🔹 Classification Modeling
| Model | Mean ROC-AUC (CV) | Test ROC-AUC | Remarks |
|:------|:------------------:|:-------------:|:--------|
| Logistic Regression | 0.93 | 0.93 | Interpretable and stable under moderate noise |
| Random Forest | 0.92 | 0.92 | Handles non-linearities well |
| XGBoost | **0.93+** | **0.92–0.93** | Best-performing, well-calibrated model |

### 🔹 Model Evaluation
- Used **cross-validation** for generalization.  
- Tuned **classification thresholds** (balanced at ~0.37 for F1).  
- Applied **calibration (Brier score ~0.11)** to align predicted probabilities.  

### 🔹 Model Explainability
- **Partial Dependence Plots (PDPs)** to show marginal effects.  
- **SHAP analysis** ranked Governance and Social as most influential ESG pillars.  
- **Grouped SHAP impacts** provided aggregated ESG vs. financial dimension importance.

---

## 📊 Results Summary

| Dimension | Mean |SHAP Value| |
|:-----------|----------------:|
| Governance | 2.5e-01 |
| Social | 2.4e-01 |
| Environmental | 2.4e-02 |
| Financial | 1.3e-02 |

**Key insight:** Governance and Social pillars contribute the most to High ESG classification.

---

## 🧰 Tech Stack

| Category | Libraries / Tools |
|-----------|-------------------|
| **Core** | Python 3.13, Pandas, NumPy |
| **Modeling** | scikit-learn, XGBoost |
| **Visualization** | Matplotlib, Seaborn, Plotly |
| **Interpretability** | SHAP, PartialDependenceDisplay |
| **Interactivity** | ipywidgets, Plotly Dash |
| **Environment** | Jupyter Notebook, `uv` / `venv` |

---

## 🧾 Data Source and Acknowledgment

The base ESG dataset originates from:  
📘 **[ESG and Financial Performance Dataset](https://www.kaggle.com/datasets/shriyashjagtap/esg-and-financial-performance-dataset/code/data)**  
by **[Shriyash Jagtap](https://www.kaggle.com/shriyashjagtap)** on *Kaggle*.

This dataset provided the foundation for simulated ESG data exploration and classification modeling.  
All preprocessing, noise generation, and label creation were performed for educational purposes.

We gratefully acknowledge **Shriyash Jagtap** for sharing this valuable dataset.

---

## 🚀 Reproducibility

### Setup
```bash
# Clone the repository
git clone https://github.com/gsanaev/esg-classification.git
cd esg-classification

# Sync environment (installs Python and dependencies)
uv sync
```

### Execution

```bash
# Retrieve Kaggle data
uv run python -m src.esg.kaggle
```

Then, execute notebooks in sequence:

```bash
# 1. notebooks/01-notebook.ipynb
# 2. notebooks/02-notebook.ipynb
# 3. notebooks/02b-notebook.ipynb
# 4. notebooks/03-notebook.ipynb
# 5. notebooks/04-notebook.ipynb
# 6. notebooks/05-notebook.ipynb
```

---

## 📚 Citation
> Sanaev, G. (2025). *Classifying Corporate ESG Performance Using Machine Learning*  
> GitHub Repository: [github.com/gsanaev/esg-classification](https://github.com/gsanaev/esg-classification)

---

## 📞 Contact

**GitHub:** [@gsanaev](https://github.com/gsanaev)  
**Email:** gsanaev@gmail.com  
**LinkedIn:** [golib-sanaev](https://linkedin.com/in/golib-sanaev)

⭐ **If you find this project insightful, please give it a star!**

---

## 📘 Author and License

**Author:** Golib Sanaev  
**Dataset Author:** [Shriyash Jagtap](https://www.kaggle.com/shriyashjagtap)  
**Version:** v1.0  
**License:** MIT  

# ⚾ dsai-m3-coaching-moneyball-analytics-kaggle

![Python](https://img.shields.io/badge/Python-3.9%20%7C%203.11-blue)
![Conda](https://img.shields.io/badge/Environment-Conda-green)
![AutoML](https://img.shields.io/badge/AutoML-AutoSklearn%20%7C%20Ensemble-orange)
![Status](https://img.shields.io/badge/Project-Active-success)

---

## 📌 Overview

This project applies **Moneyball-style analytics** using **Automated Machine Learning (AutoML)** techniques to predict outcomes.

Two approaches:
- Auto-Sklearn (fully automated)
- AutoML and Custom Ensemble (manual modeling)

---

## ⚡ Quick Start

```bash
git clone <your-repo-url>
cd dsai-m3-coaching-moneyball-analytics-kaggle
```

### Environment

```bash
conda env create -f environment_mlsk.yml
conda activate mlsk
```

OR

```bash
conda env create -f environment_ml2.yml
conda activate ml2
```

```bash
jupyter notebook
```

---

## 🧠 Notebooks

### Auto-Sklearn
- Automated model selection
- Fast baseline

### AutoML Ensemble
- Manual feature engineering
- Model stacking/blending

---

## 🏆 Model Comparison & Leaderboard

| Rank | Model Approach        | Description                         | Strengths                     | Weaknesses                  | Score* |
|------|---------------------|-------------------------------------|-------------------------------|-----------------------------|--------|
| 1    | Ensemble (Custom)   | Stacking/blending multiple models   | High performance, flexible    | More complex                | TBD    |
| 2    | Auto-Sklearn        | Automated pipeline + ensemble       | Fast, minimal effort          | Less control                | TBD    |

*Replace scores with actual Kaggle metric (e.g., RMSE, Accuracy)

---

## 📊 Evaluation Notes

- Ensemble models typically outperform due to:
  - Feature engineering
  - Model diversity
- Auto-Sklearn provides strong baseline quickly

---

## 📂 Structure

```
project/
├── documentation/
├── notebooks
├── data
├── environments
└── README.md
```

---

## 📚 Documentation

See `/documentation` folder for:
- Guides
- Slides
- Learning materials

---

## ⚙️ Dependencies

### ml2 (Ensemble)
- Python 3.11
- pandas, numpy, sklearn
- lightgbm, statsmodels
- matplotlib, seaborn

### mlsk (Auto-Sklearn)
- Python 3.9
- auto-sklearn
- sklearn stack
- graphviz

---

## ⚠️ Disclaimer

Models used are **not exhaustive** and represent a subset of possible approaches.

---

## 🚀 Future Improvements

- Add MLflow tracking
- Expand ensemble techniques
- Hyperparameter tuning

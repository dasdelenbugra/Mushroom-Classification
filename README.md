
[Mushroom_README.md](https://github.com/user-attachments/files/26165238/Mushroom_README.md)
# Mushroom Classification

A multi-model machine learning project that predicts whether a mushroom is **edible or poisonous** using 6 different classification algorithms. Models are compared by accuracy, precision, recall, and F1-score to find the best performer.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dasdelenbugra/Mushroom-Classification/blob/main/Final_project.ipynb)

---

## Results — Model Comparison

| Model | Accuracy | Notes |
|-------|----------|-------|
| Logistic Regression | 80% | Baseline |
| Ridge Classifier | 80% | Same as logistic |
| Decision Tree | ~85% | Mid performer |
| Naive Bayes | ~75% | Lowest |
| Neural Network (MLP) | ~85% | Did not converge (200 iter) |
| **Random Forest** | **91%** | Best performer |

### Best Model — Random Forest

```
              precision    recall  f1-score   support

   Edible(0)     0.94      0.89      0.91      1313
Poisonous(1)     0.88      0.93      0.90      1125

    accuracy                         0.91      2438
   macro avg     0.91      0.91      0.91      2438
```

### Logistic Regression (Baseline)

```
              precision    recall  f1-score   support

   Edible(0)     0.82      0.80      0.81      1313
Poisonous(1)     0.77      0.80      0.79      1125

    accuracy                         0.80      2438
```

---

## Dataset

- **8124 mushroom samples** — 23 species of gilled mushrooms from Kaggle
- **22 features** total (cap shape, surface, color, odor, gill type, ring type, habitat...)
- **4 features used for training:** `cap-shape`, `cap-color`, `ring-number`, `ring-type`
- **Labels:** Edible (e → 0), Poisonous (p → 1)
- **Train / Test split:** 70% / 30%
- All categorical features encoded with **LabelEncoder**

---

## How It Works

```
Load mushrooms.csv (8124 samples, 22 features)
       ↓
Select 4 features: cap-shape, cap-color, ring-number, ring-type
       ↓
LabelEncoder — convert categorical strings to integers
       ↓
Train/Test split (70/30)
       ↓
Train & evaluate 6 models in parallel:
  Logistic Regression → 80%
  Ridge Classifier    → 80%
  Decision Tree       → ~85%
  Naive Bayes         → ~75%
  Neural Network      → ~85%
  Random Forest       → 91% ← Winner
       ↓
Classification report comparison
```

---

## Technologies

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| Scikit-learn | All 6 ML models + LabelEncoder |
| Pandas | Data loading and manipulation |
| Matplotlib | Visualization |
| Google Colab | Runtime environment |

---

## Installation & Usage

```bash
git clone https://github.com/dasdelenbugra/Mushroom-Classification.git
cd Mushroom-Classification

pip install scikit-learn pandas matplotlib

jupyter notebook Final_project.ipynb
```

> Dataset: Download `mushrooms.csv` from [Kaggle](https://www.kaggle.com/datasets/uciml/mushroom-classification) and place in project root.

---

## Author

**Ömer Buğra Daşdelen**  
Computer Engineering Graduate | AI/ML & Android Developer  
[GitHub](https://github.com/dasdelenbugra) · [LinkedIn](https://linkedin.com/in/ömer-buğra-daşdelen-24746124b)

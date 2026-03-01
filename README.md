# Experiment 5 – Phishing URL Detection: ML Model Comparison
**KJSSE | AI&DS | SEM-VI | MLCS 2025-26 | Roll No: 16014223080**

---

## Objective
Implement and compare 1 unsupervised + 5 supervised ML models for phishing URL detection.

## Models Used
| Type | Model |
|------|-------|
| Unsupervised | K-Means Clustering (k=6) |
| Supervised | Random Forest, Gradient Boosting, Logistic Regression, Decision Tree, SVM |

## Dataset
- Source: [Kaggle Phishing Website Dataset](https://www.kaggle.com/datasets/eswarchandt/phishing-website-detector)
- Samples: 5,849 (after cleaning in Exp 4)
- Features: 30 URL-based structural features
- Labels: 0 = Phishing, 1 = Legitimate

## How to Run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
python Exp5_Phishing_ML_Comparison.py
```
> Place `phishing.csv` in the same folder before running.

## Outputs (7 Graphs)
| File | Description |
|------|-------------|
| `exp5_01_kmeans_clustering.png` | K-Means PCA scatter + Elbow curve |
| `exp5_02_cluster_analysis.png` | Cluster composition vs true labels |
| `exp5_03_accuracy_f1.png` | Accuracy & F1 comparison |
| `exp5_04_roc_curves.png` | ROC curves – all 5 models |
| `exp5_05_confusion_matrices.png` | Confusion matrices – top 3 models |
| `exp5_06_extended_analysis.png` | All metrics + attack-type detection rate |
| `exp5_07_rf_feature_learning.png` | Feature importance + learning curve |

## Results Summary
| Model | Accuracy | F1 | AUC |
|-------|----------|----|-----|
| Random Forest | **0.9462** | **0.9447** | 0.9875 |
| Gradient Boosting | 0.9444 | 0.9432 | **0.9884** |
| SVM | 0.9393 | 0.9383 | 0.9820 |
| Decision Tree | 0.9171 | 0.9135 | 0.9219 |
| Logistic Regression | 0.9128 | 0.9110 | 0.9741 |
| K-Means | N/A | N/A | Silhouette: 0.1088 |

## Novel Contribution
Attack-type subgroup analysis maps phishing URLs into 6 subtypes and measures per-category detection rate — IP-Based Pharming detected best (>97%), Social Engineering hardest (~90%).

## Prerequisites
- Python 3.8+
- Experiment 4 cleaned dataset (`phishing.csv`)

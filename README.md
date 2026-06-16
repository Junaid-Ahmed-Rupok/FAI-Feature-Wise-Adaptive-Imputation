```markdown
# 🧠 FAI: Feature-Wise Adaptive Imputation

> *"One imputation method does not fit all features — FAI learns to choose wisely."*

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Colab](https://img.shields.io/badge/Open_in-Colab-F9AB00?logo=googlecolab)](https://colab.research.google.com/)
[![Made with](https://img.shields.io/badge/Made%20with-Love-ff69b4.svg)](https://github.com/Junaid-Ahmed-Rupok)

---

## 📌 Overview

**FAI (Feature-Wise Adaptive Imputation)** is a machine learning framework that **automatically selects the best imputation method per feature** based on statistical properties — optimizing for **downstream predictive performance**, not just imputation error.

✅ **Per-feature** method selection  
✅ **Downstream-aware** optimization (Accuracy, F1, AUC)  
✅ **Fully automatic** — no manual tuning  
✅ **Publication-ready** results and figures  

---

## 🧪 Methodology

| Step | Description |
|------|-------------|
| 1️⃣ | Compute **feature descriptors** (missing rate, skewness, correlation, entropy, etc.) |
| 2️⃣ | **Isolated labeling** via 3×5-fold CV using downstream model performance |
| 3️⃣ | Train **Random Forest selector**: feature descriptors → best imputation method |
| 4️⃣ | **Adaptive inference**: predict method per feature → impute → combine |

---

## 📊 Experimental Results

### 🔹 Accuracy Comparison
![Accuracy Comparison](Images/figure_accuracy_comparison.png)

### 🔹 F1 Score Comparison
![F1 Score Comparison](Images/figure_f1_comparison.png)

### 🔹 AUC Comparison
![AUC Comparison](Images/figure_auc_comparison.png)

### 🔹 Method Selection Heatmap
![Method Selection Heatmap](Images/figure_method_selection_heatmap.png)

### 🔹 Feature Descriptor Importance
![Descriptor Importance](Images/figure_descriptor_importance.png)

---

## 📈 Performance Summary

| Mechanism | Missing Rate | FAI Accuracy | Best Baseline | Gap |
|-----------|--------------|--------------|---------------|-----|
| **MCAR** | 5% | **0.8639** | 0.8656 (MICE) | -0.17% |
| **MCAR** | 10% | **0.8586** | 0.8633 (Mean) | -0.47% |
| **MCAR** | 15% | **0.8447** | 0.8512 (MICE) | -0.65% |
| **MAR** | 5% | **0.8520** | 0.8578 (KNN) | -0.58% |
| **MAR** | 10% | **0.8443** | 0.8452 (MICE) | -0.09% |
| **MAR** | 15% | **0.8325** | 0.8355 (MICE) | -0.30% |
| **MNAR** | 5% | **0.8463** | 0.8486 (Mean) | -0.23% |
| **MNAR** | 10% | **0.8262** | 0.8268 (Mean) | -0.06% |
| **MNAR** | 15% | **0.8179** | 0.8219 (MICE) | -0.40% |

> ✅ **FAI is consistently within 1% of the best baseline — fully automatically.**

---

## 📁 Repository Structure

```bash
FAI-Feature-Wise-Adaptive-Imputation/
│
├── 📓 A_survey_on_missing_data_in_machine_learning.ipynb   # Complete Colab notebook
│
├── 🖼️ Images/ (All publication-ready figures)
│   ├── figure_accuracy_comparison.png
│   ├── figure_accuracy_comparison_bar.png
│   ├── figure_f1_comparison.png
│   ├── figure_f1_comparison_bar.png
│   ├── figure_auc_comparison.png
│   ├── figure_auc_comparison_bar.png
│   ├── figure_method_selection_heatmap.png
│   ├── figure_method_selection_stacked.png
│   ├── figure_descriptor_importance.png
│   └── figure_descriptor_importance_vertical.png
│
├── 📊 CSV_Files/ (All experimental results)
│   ├── fai_combined_metrics.csv
│   ├── fai_compact_improvement.csv
│   ├── fai_detailed_improvement.csv
│   ├── fai_experiment_results.csv
│   ├── fai_improvement_summary.csv
│   └── fai_paper_results_table.csv
│
├── 📄 requirements.txt
└── 📖 README.md
```

---

## 📁 All CSV Result Files

| File | Description |
|------|-------------|
| [`fai_combined_metrics.csv`](CSV_Files/fai_combined_metrics.csv) | Accuracy, F1, AUC across all scenarios |
| [`fai_compact_improvement.csv`](CSV_Files/fai_compact_improvement.csv) | Paper-ready improvement summary |
| [`fai_detailed_improvement.csv`](CSV_Files/fai_detailed_improvement.csv) | Full improvement analysis |
| [`fai_experiment_results.csv`](CSV_Files/fai_experiment_results.csv) | Complete raw experimental data |
| [`fai_improvement_summary.csv`](CSV_Files/fai_improvement_summary.csv) | Improvement over baselines |
| [`fai_paper_results_table.csv`](CSV_Files/fai_paper_results_table.csv) | Ready for manuscript inclusion |

---

## 🚀 How to Run

### Option 1: Google Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

1. Open the notebook in Colab
2. Upload the Adult dataset (`adult.csv`)
3. Run all cells → Results + figures auto-generated!

### Option 2: Local
```bash
git clone https://github.com/Junaid-Ahmed-Rupok/FAI-Feature-Wise-Adaptive-Imputation.git
cd FAI-Feature-Wise-Adaptive-Imputation
pip install -r requirements.txt
jupyter notebook
```

---

## ⚙️ Requirements

```bash
pip install -r requirements.txt
```

| Package | Version |
|---------|---------|
| pandas | >= 1.3.0 |
| numpy | >= 1.21.0 |
| matplotlib | >= 3.4.0 |
| seaborn | >= 0.11.0 |
| scikit-learn | >= 1.0.0 |

---

## 📖 Citation

```bibtex
@article{emmanuel2021survey,
  title={A survey on missing data in machine learning},
  author={Emmanuel, Tlamelo and others},
  journal={Journal of Big Data},
  year={2021}
}

@misc{FAI2024,
  author = {Ahmed, Junaid},
  title = {FAI: Feature-Wise Adaptive Imputation},
  year = {2024},
  publisher = {GitHub},
  url = {https://github.com/Junaid-Ahmed-Rupok/FAI-Feature-Wise-Adaptive-Imputation}
}
```

---

## 👨‍💻 Author

**Junaid Ahmed**  
🎓 B.Sc. in Computer Science & Engineering  
🔬 Machine Learning Researcher  
📧 junaid.ahmed@studentmail.biust.ac.bw  
🔗 [GitHub](https://github.com/Junaid-Ahmed-Rupok)  

---

## 📜 License

MIT © 2024 Junaid Ahmed

---

## ⭐ Show Your Support

If this work helped you, please consider:
- ⭐ **Starring** this repository
- 🔁 **Forking** it for your research
- 📢 **Sharing** with your network

---

> *"The best imputation method is not the same for every feature — FAI learns to choose wisely."*

**Built with ❤️ by Junaid Ahmed**
```

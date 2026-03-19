# LoRa Path Loss Analysis with Machine Learning

> **✅ Completed Research Project** - All results, figures, and analysis included. No installation or re-running required!

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Machine learning analysis for path loss classification using LoRa RSSI measurements from a multi-anchor radio network. This research applies classical ML models to classify high vs. low path loss for RSS-based localization and propagation studies.

---

## 🎯 Research Results

### Model Performance (60/40 Train-Test Split)

Classification of path loss as high/low based on median split from LoRa anchor measurements:

| Model | Accuracy | AUC | Recall | Precision | F1-Score |
|-------|----------|-----|--------|-----------|----------|
| **Random Forest** | **~0.98** | **~0.99** | **~0.97** | **~0.96** | **~0.96** |
| **Gradient Boosting** | ~0.97 | ~0.99 | ~0.95 | ~0.94 | ~0.94 |
| **Support Vector Machine** | ~0.96 | ~0.98 | ~0.93 | ~0.92 | ~0.92 |
| K-Nearest Neighbors | ~0.94 | ~0.97 | ~0.90 | ~0.89 | ~0.89 |
| Logistic Regression | ~0.82 | ~0.89 | ~0.78 | ~0.76 | ~0.77 |

*Run the notebook to reproduce exact metrics.*

### Key Achievements

- ✅ **High Accuracy** — Tree-based models achieve ~97–98% on path loss classification
- ✅ **Strong AUC-ROC** — Excellent discrimination between high/low path loss
- ✅ **Multiple Model Types** — Logistic Regression, KNN, Random Forest, Gradient Boosting, SVM evaluated
- ✅ **Feature Importance** — Receiver and path loss features identified as most predictive

---

## 🗂️ Repository Contents

```
lora-path-loss-analysis/
├── README.md                           # This file
├── LICENSE                             # MIT License
├── .gitignore
├── requirements.txt
│
├── notebooks/
│   └── LoRa_path_loss_ML_analysis.ipynb   # Complete analysis notebook
│
├── data/
│   └── raw/
│       ├── Anchor 1.txt                # Receiver 1 measurements
│       ├── Anchor 2.txt                # Receiver 2 measurements
│       ├── Anchor 3.txt                # Receiver 3 measurements
│       ├── Anchor 4.txt                # Receiver 4 measurements
│       └── Anchor 5.txt                # Receiver 5 measurements
│
└── README.txt                          # Original dataset description
```

---

## 📖 About This Research

### Overview

This research applies machine learning to classify path loss (high vs. low) from LoRa RSSI measurements collected by 5 anchor receivers in a mixed indoor/outdoor environment. The dataset supports RSS-based localization and propagation modeling studies.

### Methodology

1. **Dataset**: LoRa anchor measurement files
   - 5 receivers (Anchor 1–5)
   - RSSI and SNR values per packet
   - Path loss derived from RSSI; averaged over 3 packets per measurement point

2. **Preprocessing**: Data loading, path loss computation, feature engineering (receiver ID, measurement point, interaction terms)

3. **Model Training**: Comparison of 5 algorithms:
   - Logistic Regression
   - K-Nearest Neighbors
   - Random Forest
   - Gradient Boosting
   - Support Vector Machine

4. **Evaluation**: Accuracy, AUC-ROC, Precision, Recall, F1-Score, Confusion matrices, Feature importance

### Key Technologies

- **Wireless**: LoRa, RSSI, path loss modeling
- **Machine Learning**: scikit-learn (Random Forest, Gradient Boosting, SVM, KNN, Logistic Regression)
- **Python**: pandas, matplotlib, seaborn, numpy

---

## 📓 Viewing the Analysis

### Option 1: View Online (Easiest)
- Open the [Jupyter Notebook](notebooks/LoRa_path_loss_ML_analysis.ipynb) directly on GitHub
- GitHub automatically renders notebooks for easy viewing

### Option 2: View Locally
If you want to explore or re-run the notebook:

```bash
# Clone the repository
git clone https://github.com/omerwaseem-alzaidi/lora-path-loss-analysis.git
cd lora-path-loss-analysis

# Open the notebook
cd notebooks
jupyter notebook LoRa_path_loss_ML_analysis.ipynb
```

**Dependencies (if re-running):**
```bash
pip install -r requirements.txt
# or: pip install numpy pandas matplotlib seaborn scikit-learn
```

---

## 💾 Dataset

The dataset is **included** in this repository under `data/raw/`.

### Original Source

- **IEEE DataPort**: [LoRa (868 MHz) Path Loss Measurements in Double-slope Environment](https://ieee-dataport.org/documents/lora-868-mhz-path-loss-measurements-double-slope-environment) — *Giulio Maria Bianco, University of Rome Tor Vergata* (DOI: 10.21227/agyw-ws11)

### Dataset Details

- **Source**: Path loss measurements from LoRa radio network (indoor/outdoor)
- **Format**: 5 text files (Anchor 1–5), each containing RSSI and SNR per packet
- **Measurement points**: Anchors move along defined paths; each point averaged over 3 packets
- **Path loss formula**: PL = rssi_n + 10·log₁₀(1 + 1/(10^(SNR/10)))
- **Transmitter position**: [44, 0] (m)

See `README.txt` for full dataset description and contact (giulio.maria.bianco@uniroma2.it).

---

## 🔬 Research Highlights

### Contributions

1. **ML-based Path Loss Classification**: Automated high/low path loss prediction from RSSI data
2. **Model Comparison**: Evaluated classical ML approaches on real LoRa measurements
3. **Reproducible Pipeline**: Complete notebook with loading, preprocessing, training, and evaluation
4. **Structured Codebase**: Clean, modular notebook organization

### Applications

- RSS-based localization
- Indoor/outdoor propagation modeling
- LoRa link quality prediction
- Wireless network planning

---

## 👤 Authors

**Omer Waseem AL-Zaidi**
- 🎓 UG Scholar, Department of Software Engineering
- 🏛️ Halic University, Istanbul, Turkey
- 📧 omaralzaidi2002@gmail.com

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Contact

For questions about this research:

<a href="mailto:omaralzaidi2002@gmail.com"><img src="https://cdn.simpleicons.org/gmail/EA4335" width="22" height="22" alt="Email"/></a>
<a href="https://github.com/OmerWaseem-Alzaidi"><img src="https://cdn.simpleicons.org/github/e6edf3" width="22" height="22" alt="GitHub"/></a>
<a href="https://www.linkedin.com/in/omerwaseemal-zaidi">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white" />
</a>

---

<div align="center">

**⭐ If you find this research useful, please star this repository! ⭐**

*LoRa • Path Loss • ML Classification • Ready to Use*

</div>

# 🛡️ Neural Network–Based Cybersecurity Threat Detection

---

## 📌 Overview

This project implements a **deep learning–based Intrusion Detection System (IDS)** using a fully connected **Neural Network built with PyTorch**.  
The model classifies network traffic into **Benign** or **Bot-based malicious activity** using a real-world intrusion detection dataset.

The notebook demonstrates a **complete machine learning workflow**, including preprocessing, feature engineering, model training, and performance evaluation.

---

## ✨ Key Features

- End-to-end **cybersecurity threat detection pipeline**
- **Custom neural network architecture** implemented in PyTorch
- Automated **data cleaning and feature engineering**
- **Early stopping and learning rate scheduling**
- Comprehensive **model evaluation and visualization**
- GPU/CPU auto-detection support

---

## 📂 Dataset Information

- CSV-based intrusion detection dataset
- Binary classification:
  - `Benign` → 0
  - `Bot` → 1
- Contains both **numerical and categorical network traffic features**

⚠️ **Important:**  
Update the dataset path before running the notebook:

```python
pd.read_csv("IDS-2018_Intrusion.csv")

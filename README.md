# 🛡️ Neural Network–Based Cybersecurity Threat Detection

## Overview

This project implements a deep learning–based intrusion detection system (IDS) using a fully connected neural network built with PyTorch. The model is trained to classify network traffic as **Benign (0)** or **Bot (1)** using a real-world intrusion detection dataset.

The notebook demonstrates a full machine learning pipeline: data loading, cleaning, feature engineering, exploratory analysis, model definition and training, early stopping and LR scheduling, and detailed evaluation with visualizations and metrics.

---

## ✨ Key Features

- End-to-end cybersecurity threat detection pipeline implemented in a Jupyter Notebook  
- Multi-layer neural network implemented with PyTorch  
- Robust data preprocessing and feature engineering steps  
- Early stopping and ReduceLROnPlateau learning-rate scheduler  
- Detailed evaluation: confusion matrix, ROC/AUC, precision–recall, training curves  
- Designed for realistic intrusion-detection datasets (tabular features, mixed numeric/categorical)

---

## 📂 Dataset

- Format: CSV (IDS 2018–style dataset assumed)  
- Target label encoding:
  - `Benign` → `0`
  - `Bot` → `1`
- Contains a mixture of numeric and categorical network traffic features

Important: The dataset path is currently hardcoded in the notebook. Update it before running:

```python
pd.read_csv("IDS-2018_Intrusion.csv")
```

---

## 🔍 Data Preprocessing & Feature Engineering

The notebook includes the following preprocessing pipeline:

1. Data cleaning
   - Missing value detection and handling
   - Duplicate row/column checks
   - Column name sanitization (trim whitespace)

2. Label encoding
   - Convert human-readable labels to numeric
   - Fallback factorization for unexpected labels

3. Categorical feature handling
   - One-hot encoding for categorical features with ≤ 20 unique values
   - Automatic exclusion of high-cardinality categorical columns
   - Timestamp columns removed if present

4. Feature scaling
   - StandardScaler (zero mean, unit variance) applied to numeric features

5. Train/test split
   - 80% training, 20% testing
   - Stratified split to preserve class balance

---

## 🧠 Neural Network Architecture

A fully connected feedforward neural network (MLP):

- Input → 512 → 256 → 128 → Output (2 classes / logits)

Architecture details:
- Activation: ReLU
- Regularization: Dropout (0.25)
- Weight initialization: uniform and Kaiming (He) initializers supported
- Output: raw logits (use CrossEntropyLoss)

Layer pattern:
```
Linear → ReLU → Dropout
Linear → ReLU → Dropout
Linear → ReLU
Linear → Output
```

---

## ⚙️ Training Configuration

- Loss function: CrossEntropyLoss  
- Optimizer: SGD with momentum  
- Learning rate: 0.001  
- Weight decay: 1e-5  
- Scheduler: ReduceLROnPlateau  
- Max epochs: 50  
- Early stopping patience: 5 epochs  
- Device support: CPU / CUDA (auto-detected)

Training logs per epoch:
- Training loss
- Validation loss
- Training accuracy
- Validation accuracy

The notebook saves the best-performing model (based on validation accuracy).

---

## 📊 Model Evaluation

Evaluation components included in the notebook:

- Classification metrics: accuracy, precision, recall, F1  
- ROC curve and AUC score  
- Precision–Recall curve  
- Confusion matrix visualization  
- Training vs validation loss and accuracy curves

These visualizations help diagnose overfitting, class imbalance issues, and generalization performance.

---

## 🚀 How to Run

1. Clone the repository:
```bash
git clone https://github.com/Nishchal-Panta/Cybersecurity_threat_detection.git
cd Cybersecurity_threat_detection
```

2. Create and activate a Python virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate      # macOS / Linux
.venv\Scripts\activate         # Windows (PowerShell)
```

3. Install required packages:
```bash
pip install torch torchvision torchaudio torchmetrics scikit-learn pandas matplotlib seaborn jupyterlab
```

4. Update the dataset path in the notebook to point to your local CSV file:
```python
pd.read_csv("path/to/IDS-2018_Intrusion.csv")
```

5. Launch Jupyter and run all cells:
```bash
jupyter lab  # or jupyter notebook
```

---

## 🔮 Possible Improvements

- Support for multi-class attack detection (more attack labels beyond Bot/Benign)  
- Use CNN / LSTM / Transformer models for sequence/time-series traffic data  
- Feature selection (mutual information, recursive feature elimination, PCA)  
- Hyperparameter tuning (Optuna, Ray Tune)  
- Deploy as a real-time IDS API (FastAPI + Docker)  
- Integrate with Spark for large-scale traffic logs and streaming ingestion  
- Add explainability (SHAP) to help SOC analysts interpret alerts

---

## 🧪 Technologies Used

- Python  
- PyTorch  
- TorchMetrics  
- Scikit-learn  
- Pandas / NumPy  
- Matplotlib / Seaborn  
- JupyterLab / Jupyter Notebook

---

## 📜 License

This project is provided for academic and educational use. Dataset usage must comply with the original dataset license. Add a LICENSE file (e.g. MIT) if you intend to release code under a permissive license.

---

## 👤 Author

**Nishchal Panta**  
BCS Student | Machine Learning & Data Science Enthusiast

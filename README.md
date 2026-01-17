🛡️ Neural Network–Based Cybersecurity Threat Detection
Overview

This project implements a deep learning–based intrusion detection system (IDS) using a fully connected neural network built with PyTorch. The model is trained to classify network traffic as Benign or Bot-based malicious activity using a real-world intrusion detection dataset.

The notebook demonstrates a complete machine learning pipeline, including data cleaning, feature engineering, exploratory analysis, neural network training, and performance evaluation using industry-standard metrics.

✨ Key Features

End-to-end cybersecurity threat detection pipeline

Multi-layer neural network implemented from scratch using PyTorch

Robust data preprocessing & feature engineering

Early stopping and learning rate scheduling

Detailed model evaluation and visualization

Designed for realistic intrusion detection datasets

📂 Dataset

CSV-based intrusion detection dataset (IDS 2018–style)

Target label:

Benign → 0

Bot → 1

Contains both numeric and categorical network traffic features

⚠️ Dataset path is currently hardcoded. Update it before running:

pd.read_csv("IDS-2018_Intrusion.csv")

🔍 Data Preprocessing & Feature Engineering

The notebook performs the following preprocessing steps:

1. Data Cleaning

Missing value detection

Duplicate row and column checks

Column name sanitization (whitespace removal)

2. Label Encoding

Converts class labels into numerical format

Fallback factorization for unexpected labels

3. Categorical Feature Handling

One-hot encoding for categorical features with ≤20 unique values

Automatic exclusion of high-cardinality categorical columns

Timestamp columns removed if present

4. Feature Scaling

StandardScaler applied to all numeric features

Ensures stable and efficient neural network training

5. Train/Test Split

80% training, 20% testing

Stratified label preservation

🧠 Neural Network Architecture

The model is a fully connected feedforward neural network:

Input Layer → 512 → 256 → 128 → Output (2 classes)

Architecture Details:

Activation: ReLU

Regularization: Dropout (0.25)

Weight Initialization:

Uniform initialization

Kaiming (He) initialization via custom function

Output: Logits for binary classification

Linear → ReLU → Dropout
Linear → ReLU → Dropout
Linear → ReLU
Linear → Output

⚙️ Training Configuration

Loss Function: Cross-Entropy Loss

Optimizer: SGD with momentum

Learning Rate: 0.001

Weight Decay: 1e-5

Scheduler: ReduceLROnPlateau

Max Epochs: 50

Early Stopping: Patience = 5 epochs

Device Support: CPU / CUDA (auto-detected)

📊 Model Evaluation

The notebook evaluates the trained model using:

Classification Metrics

Accuracy (TorchMetrics)

Precision–Recall Curve

ROC Curve & AUC score

Visualizations

Confusion Matrix

Training vs Validation Loss Curve

Training vs Validation Accuracy Curve

These visual tools help diagnose:

Overfitting

Class imbalance

Generalization performance

📈 Results Tracking

During training, the following are logged per epoch:

Training loss

Validation loss

Training accuracy

Validation accuracy

The best-performing model (based on validation accuracy) is automatically saved.

🧪 Technologies Used

Python

PyTorch

TorchMetrics

Scikit-learn

Pandas / NumPy

Matplotlib / Seaborn

🚀 How to Run

Install dependencies:

pip install torch torchvision torchaudio torchmetrics scikit-learn pandas matplotlib seaborn


Update dataset path in the notebook

Run all cells sequentially in Jupyter Notebook or JupyterLab

🔮 Possible Improvements

Support for multi-class attack detection

CNN or LSTM models for sequential traffic data

Feature selection using mutual information or PCA

Deployment as a real-time IDS API

Integration with Spark for large-scale traffic logs

📜 License

This project is for academic and educational purposes.
Dataset usage must comply with the original dataset’s license.

👤 Author

Nishchal Panta
BCS Student | Machine Learning & Data Science Enthusiast

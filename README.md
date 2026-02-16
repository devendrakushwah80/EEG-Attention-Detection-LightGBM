# 🧠 EEG Attention Detection using LightGBM

This project performs classification of EEG signals into two mental states:
- **Relaxed**
- **Attention**

The system processes raw EEG signals, extracts advanced signal-processing features, and trains a LightGBM classifier to detect attention levels.

---

## 🚀 Project Pipeline

### 1️⃣ Data Loading
- EEG data loaded from `sample.csv`
- Raw EEG values cleaned and converted to numeric format

### 2️⃣ Signal Preprocessing
- Sampling Rate: **512 Hz**
- 50 Hz Notch Filter (Powerline noise removal)
- 0.5–30 Hz Bandpass Filter (EEG frequency range)
- Artifact removal (threshold-based)

### 3️⃣ Feature Engineering

Each 2-second window (1024 samples) extracts:

### 🔹 Frequency Domain Features
- Delta Energy (0.5–3 Hz)
- Theta Energy (4–7 Hz)
- Alpha Energy (8–13 Hz)
- Beta Energy (14–30 Hz)
- Alpha/Beta Ratio
- Theta/Beta Ratio

### 🔹 Time Domain Features
- RMS
- Variance
- Zero Crossing Rate
- Skewness
- Kurtosis
- Mean
- Standard Deviation
- Peak-to-Peak

### 🔹 Hjorth Parameters
- Activity
- Mobility
- Complexity

### 🔹 Spectral Feature
- Spectral Entropy

Total Features: **18**

---

## 🧠 Model Used

- **LightGBM Classifier**
- StandardScaler for normalization
- Stratified Train-Test Split
- 5-Fold Stratified Cross Validation
- Threshold Optimization for best F1 score

---

## 📊 Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Classification Report
- Cross-validation F1 Score
- Feature Importance Analysis

---

## 💾 Model Saving

Trained model saved as:

model.pkl


---

## 📁 Project Structure



│── sample.csv
│── test2.ipynb
│── model.pkl
│── README.md
│── requirements.txt


---

## ▶️ How to Run

1. Install dependencies:
```bash
pip install -r requirements.txt
```

Run the notebook:

jupyter notebook test2.ipynb

🎯 Key Highlights

✔ Advanced EEG filtering
✔ Strong handcrafted feature engineering
✔ Optimized LightGBM model
✔ Threshold tuning for maximum F1
✔ Cross-validation for robustness
✔ Feature importance analysis

📌 Future Improvements

Add real-time EEG streaming

Deep Learning (CNN/LSTM) comparison

Hyperparameter tuning with Optuna

Real-world labeled dataset integration

👨‍💻 Author

Devendra Kushwah
Machine Learning & Signal Processing Enthusiast

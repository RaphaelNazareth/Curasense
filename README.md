# 🏥 Disease Prediction from Symptoms

**NLP-based multi-class text classification using TF-IDF and machine learning**

---

## 📌 Overview
This project builds a machine learning system that predicts diseases from natural language symptom descriptions. It leverages NLP preprocessing and multiple classification algorithms to map free-text input into one of 24 disease categories.

---

## 🎯 Problem Statement
Given a natural language description of symptoms, predict the most likely disease from a predefined set of conditions.

---

## 🎯 Goals
- Build a high-accuracy NLP classification model
- Compare multiple machine learning algorithms
- Evaluate performance using standard classification metrics

---

## 📊 Dataset
- **Name:** Symptom2Disease  
- **Size:** 1200 samples (50 per class × 24 diseases)  
- **Features:**
  - `text`: symptom description (free text)
  - `label`: disease name  
- **Balance:** Perfectly balanced dataset  

---

## ⚙️ Methodology

### 🔹 Preprocessing
- Lowercasing (case folding)
- Punctuation removal
- Stopword removal
- Tokenization
- Lemmatization

### 🔹 Feature Engineering
- TF-IDF vectorization

### 🔹 Models Used
- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest
- Decision Tree
- K-Nearest Neighbors (KNN)
- BERT (bert-base-uncased)

### 🔹 Training Strategy
- 80/20 train-test split
- Stratified sampling
- Random state = 42

---

## 📈 Results

| Model               | Accuracy |
|--------------------|---------|
| Logistic Regression| 95%     |
| SVM                | 95%     |
| KNN                | 93%     |
| Random Forest      | 93%     |
| Decision Tree      | 82%     |
| BERT               | 76%     |

### 🔍 Key Findings
- Classical models (Logistic Regression & SVM) outperform BERT on small datasets
- BERT underperforms due to limited data and training epochs
- Decision Tree shows the weakest generalization
- Misclassification occurs in diseases with overlapping symptoms (e.g., diabetes, drug reaction)

---

## 🧠 Insights
- TF-IDF + classical ML is highly effective for structured medical text
- Deep learning models require larger datasets to outperform simpler methods
- Lemmatization helps reduce vocabulary size and improve generalization

---

## 🧪 Features
- Free-text symptom input
- NLP preprocessing pipeline
- TF-IDF feature extraction
- Multi-model comparison
- Confusion matrix visualization
- Probability-based prediction (KNN)
- BERT fine-tuning with HuggingFace

---

## 🛠️ Tech Stack
- Python 3.10
- pandas
- scikit-learn
- nltk
- transformers (HuggingFace)
- datasets (HuggingFace)
- torch (PyTorch)
- matplotlib & seaborn

---

## 📂 Project Structure

# 🏥 Disease Prediction from Symptoms

**NLP-based multi-class text classification using TF-IDF and machine learning**

---
<img width="1408" height="768" alt="Gemini_Generated_Image_318shp318shp318s" src="https://github.com/user-attachments/assets/6932206d-da09-41d1-8ac9-fe92ecbde2d0" />

## 📌 Overview

This project builds a machine learning system that predicts diseases from natural language symptom descriptions. It leverages NLP preprocessing and multiple classification algorithms to map free-text input into one of 24 disease categories.

---

## 🎯 Problem Statement

Given a natural language description of symptoms, predict the most likely disease from a predefined set of conditions.

---

## 🎯 Goals

* Build a high-accuracy NLP classification model
* Compare multiple machine learning algorithms
* Evaluate performance using standard classification metrics

---

## 📊 Dataset

* **Name:** Symptom2Disease
* **Size:** 1200 samples (50 per class × 24 diseases)
* **Features:**

  * `text`: symptom description (free text)
  * `label`: disease name
* **Balance:** Perfectly balanced dataset

---

## ⚙️ Methodology

### 🔹 Preprocessing

* Lowercasing (case folding)
* Punctuation removal
* Stopword removal
* Tokenization
* Lemmatization

### 🔹 Feature Engineering

* TF-IDF vectorization

### 🔹 Models Used

* Logistic Regression
* Support Vector Machine (SVM)
* Random Forest
* Decision Tree
* K-Nearest Neighbors (KNN)
* BERT (bert-base-uncased)

### 🔹 Training Strategy

* 80/20 train-test split
* Stratified sampling
* Random state = 42

---

## 📈 Results

| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | 95%      |
| SVM                 | 95%      |
| KNN                 | 93%      |
| Random Forest       | 93%      |
| Decision Tree       | 82%      |
| BERT                | 76%      |

### 🔍 Key Findings

* Logistic Regression and SVM achieved the highest accuracy (95%)
* BERT underperformed due to limited dataset size and training epochs
* Decision Tree showed the lowest performance
* Overlapping symptoms caused misclassification (e.g., diabetes, drug reaction)
* Balanced dataset removed class imbalance bias

---

## 🧠 Insights

* TF-IDF + classical ML is highly effective for structured medical text
* Deep learning models require larger datasets to outperform simpler models
* Lemmatization improves generalization by reducing vocabulary size
* Stratified splitting ensures fair evaluation

---

## 🧪 Features

* Free-text symptom input for prediction
* NLP preprocessing pipeline
* TF-IDF feature extraction
* Multi-model comparison
* Confusion matrix visualization
* Probability-based predictions (KNN)
* BERT fine-tuning with HuggingFace

---

## 🛠️ Tech Stack

* Python 3.10
* pandas
* scikit-learn
* nltk
* transformers (HuggingFace)
* datasets (HuggingFace)
* torch (PyTorch)
* matplotlib
* seaborn

---

## 📂 Project Structure

```
project/
│
├── disease_prediction.ipynb   # Full pipeline (training & evaluation)
├── data/
│   └── Symptom2Disease.csv
├── utils/
│   └── preprocessing functions
├── assets/
│   └── confusion matrix plots
└── README.md
```

---

## 🚀 Usage

### 🔧 Installation

```bash
pip install pandas scikit-learn nltk transformers datasets torch matplotlib seaborn
python -m nltk.downloader stopwords punkt wordnet
```

### ▶️ Run

Open and run:

```bash
disease_prediction.ipynb
```

Modify input:

```python
symptom = "your symptom text here"
```

---

## 🔮 Future Work

* Deploy as web app (Streamlit / Gradio)
* Improve BERT with more epochs and tuning
* Expand dataset size
* Apply cross-validation
* Use domain-specific models (BioBERT / ClinicalBERT)
* Add explainability (LIME / SHAP)

---

## 👤 Author

**Raphael Nazareth**
Computer Engineer | AI / Data Science

* GitHub: https://github.com/RaphaelNazareth
* LinkedIn: https://www.linkedin.com/in/raphael-nazareth
* Email: [Raph00707@gmail.com](mailto:Raph00707@gmail.com)

---

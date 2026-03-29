{
  "project_meta": {
    "title": "Disease Prediction from Symptoms",
    "subtitle": "NLP-based multi-class text classification using TF-IDF and machine learning",
    "emoji": "🏥",
    "color_from": "#1a73e8",
    "color_to": "#0d47a1",
    "sdk": "gradio",
    "sdk_version": "4.0.0",
    "python_version": "3.10",
    "entry_point": "app.py",
    "pinned": false
  },
  "overview": {
    "description": "A machine learning system that predicts diseases based on natural language symptom descriptions entered by users.",
    "high_level_summary": "This project applies NLP preprocessing and multiple ML classifiers (Logistic Regression, Random Forest, Decision Tree, SVM, KNN, BERT) to classify 24 diseases from free-text symptom input using TF-IDF vectorization."
  },
  "problem": {
    "business_problem": "Early and accurate disease identification is critical in healthcare but often requires expert medical knowledge. A text-based automated system can assist in preliminary diagnosis.",
    "problem_statement": "Given a natural language description of symptoms, predict the most likely disease from a set of 24 possible conditions."
  },
  "goals": {
    "primary": "Build a high-accuracy NLP classification model that maps symptom text to disease labels.",
    "secondary": "Compare multiple ML algorithms to identify the best-performing model for clinical text classification."
  },
  "objectives": [
    "Preprocess raw symptom text using NLP techniques (case folding, stopword removal, lemmatization)",
    "Convert text to numerical features using TF-IDF vectorization",
    "Train and evaluate five classical ML models and one deep learning model (BERT)",
    "Compare model performance using accuracy, precision, recall, and F1-score",
    "Visualize model results using confusion matrices"
  ],
  "dataset": {
    "name": "Symptom2Disease",
    "size": "1200 samples (50 per disease × 24 diseases)",
    "description": "A structured dataset containing free-text symptom descriptions paired with disease labels across 24 common medical conditions.",
    "features": "Two columns: 'text' (symptom description) and 'label' (disease name)",
    "source": "Google Drive (Symptom2Disease.csv, semicolon-delimited)"
  },
  "methodology": {
    "preprocessing": {
      "data_cleaning": "Case folding to lowercase, punctuation removal",
      "feature_engineering": "TF-IDF vectorization on lemmatized token sequences",
      "encoding": "Label encoding for BERT pipeline; original string labels for sklearn models",
      "scaling": "No explicit scaling; TF-IDF inherently normalizes term frequencies",
      "balancing": "Dataset is perfectly balanced with 50 samples per class"
    },
    "feature_selection": "All TF-IDF features retained; no explicit dimensionality reduction applied",
    "model": {
      "algorithm": "Logistic Regression, Random Forest (n=100), Decision Tree, SVM (linear kernel), KNN (k=5), BERT (bert-base-uncased)",
      "training_strategy": "Supervised learning on 80% training split with stratified sampling",
      "validation": "Held-out test set (20%, stratified) used for final evaluation",
      "cross_validation": "Not applied; single train-test split with stratify=True and random_state=42"
    }
  },
  "results": {
    "metrics": {
      "accuracy": "Logistic Regression: 95%, SVM: 95%, KNN: 93%, Random Forest: 93%, Decision Tree: 82%, BERT: 76%",
      "precision": "Macro avg — LR: 0.96, SVM: 0.96, KNN: 0.94, RF: 0.94, DT: 0.84, BERT: 0.82",
      "recall": "Macro avg — LR: 0.95, SVM: 0.95, KNN: 0.93, RF: 0.93, DT: 0.82, BERT: 0.76",
      "f1_score": "Macro avg — LR: 0.95, SVM: 0.95, KNN: 0.93, RF: 0.93, DT: 0.82, BERT: 0.73",
      "roc_auc": "Not computed"
    },
    "key_findings": [
      "Logistic Regression and SVM tied for best performance at 95% accuracy",
      "BERT underperformed classical models despite being a deep learning model, likely due to only 3 training epochs and small dataset size",
      "Decision Tree had the lowest accuracy at 82% among classical models",
      "Drug reaction and diabetes were the most commonly misclassified diseases across models",
      "Perfectly balanced dataset eliminated class imbalance as a confounding factor"
    ]
  },
  "features": [
    "Free-text symptom input for disease prediction",
    "NLP preprocessing pipeline: lowercasing, punctuation removal, stopword filtering, tokenization, lemmatization",
    "TF-IDF feature extraction",
    "Multi-model comparison: LR, RF, DT, SVM, KNN, BERT",
    "Confusion matrix visualization per model",
    "Confidence scores and per-class probabilities for KNN predictions",
    "BERT fine-tuning using HuggingFace Transformers and Trainer API"
  ],
  "tech_stack": [
    "Python 3.10",
    "pandas",
    "scikit-learn",
    "nltk",
    "transformers (HuggingFace)",
    "datasets (HuggingFace)",
    "torch (PyTorch)",
    "matplotlib",
    "seaborn",
    "Google Colab (GPU runtime)"
  ],
  "project_structure": {
    "app": "Not yet deployed",
    "notebook": "disease_prediction.ipynb — full pipeline from data loading to model evaluation",
    "models": "Trained in-memory; no serialized model files",
    "data": "Symptom2Disease.csv loaded from Google Drive",
    "utils": "preprocess_text() function for inference-time text normalization",
    "assets": "Confusion matrix plots generated inline in notebook"
  },
  "usage": {
    "installation": [
      "pip install pandas scikit-learn nltk transformers datasets torch matplotlib seaborn",
      "python -m nltk.downloader stopwords punkt wordnet"
    ],
    "run": "Open and run all cells in disease_prediction.ipynb via Google Colab or Jupyter Notebook",
    "interface": "CLI-style: modify the 'symptom' variable in the prediction cell and run to get output"
  },
  "insights": [
    "TF-IDF with classical ML is highly competitive on structured medical text datasets",
    "BERT requires more epochs and larger data to outperform classical approaches on small datasets",
    "Lemmatization improves generalization by reducing vocabulary size",
    "Diseases with overlapping symptoms (e.g., drug reaction, diabetes) are harder to classify correctly",
    "Stratified splitting is essential to preserve class distribution in small balanced datasets"
  ],
  "future_work": [
    "Deploy model as a web app using Gradio or Streamlit",
    "Fine-tune BERT for more epochs with learning rate scheduling",
    "Expand dataset to include more diseases and symptom variations",
    "Apply cross-validation for more robust performance estimation",
    "Experiment with BioBERT or ClinicalBERT for domain-specific language understanding",
    "Add explainability using LIME or SHAP for model predictions"
  ],
  ## Author
**Raphael Nazareth** Computer Engineer | AI / Data Science

- [GitHub](https://github.com/RaphaelNazareth)
- [LinkedIn](https://www.linkedin.com/in/raphael-nazareth)
- [Email](mailto:Raph00707@gmail.com)

}

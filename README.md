# IntelliChat AI 🤖

### NLP-Based Intelligent Customer Support Chatbot

IntelliChat AI is an NLP-based customer support chatbot designed to understand customer queries, classify their intents, detect uncertain or unsupported queries, and retrieve appropriate responses.

The project combines **Natural Language Processing, TF-IDF feature extraction, multiple machine learning classifiers, calibrated Linear SVM, confidence-based prediction, out-of-domain detection, and response retrieval** to build an intelligent customer-support system.


## 🚀 Features

* Natural Language Processing (NLP)
* Text preprocessing and cleaning
* TF-IDF feature extraction
* Customer intent classification
* Multiple machine learning model comparison
* Multinomial Naive Bayes
* Logistic Regression
* Linear SVM
* Random Forest
* Calibrated Linear SVM
* Confidence-based prediction
* Unknown / unsupported query detection
* Out-of-domain query detection
* Response retrieval
* Interactive chatbot
* Model persistence using Joblib
* Model evaluation
* Confusion matrix analysis
* Error analysis


## 📊 Dataset

This project uses the:

**Bitext Gen AI Chatbot Customer Support Dataset**

The dataset contains customer-support queries, intent categories, and corresponding responses.

The dataset is **not included in this repository**.

To reproduce the project, download the dataset and place it at:

```text
data/
└── Bitext_Sample_Customer_Support_Training_Dataset_27K_responses-v11.csv
```


## 🧠 Machine Learning Pipeline

```text
Customer Query
      ↓
Text Preprocessing
      ↓
TF-IDF Vectorization
      ↓
Train / Validation / Test Split
      ↓
Multiple ML Models
      ↓
Model Comparison
      ↓
Best Model Selection
      ↓
Final Training
      ↓
Confidence Calibration
      ↓
Intent Prediction
      ↓
Confidence & Margin Check
      ↓
Response Retrieval
      ↓
Chatbot Response
```

---

## 🤖 Models Evaluated

The project evaluates four machine learning algorithms:

| Model                   | Purpose                              |
| ----------------------- | ------------------------------------ |
| Multinomial Naive Bayes | Probabilistic text classification    |
| Logistic Regression     | Linear classification                |
| Linear SVM              | High-performance text classification |
| Random Forest           | Non-linear ensemble classification   |

Models are compared using multiple evaluation metrics, with **weighted F1-score** used as an important criterion for model selection.

---

## 📈 Model Evaluation

The models are evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Classification Report
* Confusion Matrix



## 🛡️ Confidence-Based Prediction

The chatbot does not blindly generate a response for every query.

After predicting an intent, the system evaluates the prediction confidence and the difference between the top two predictions.

The current configuration uses:

```text
Confidence Threshold = 0.40
Margin Threshold     = 0.10
```

If a prediction does not meet the required confidence or margin threshold, the query can be classified as:

```text
unknown
```

This helps reduce unreliable responses.

---

## 🔍 Out-of-Domain Detection

The chatbot includes an out-of-domain detection mechanism for queries that do not confidently belong to the supported customer-support intents.

For example, unrelated queries can be rejected instead of forcing them into an incorrect customer-support category.

This makes the chatbot more robust than a simple intent classifier that always returns an intent.

---


### Artifact Description

| File                       | Purpose                                 |
| -------------------------- | --------------------------------------- |
| `tfidf_vectorizer.joblib`  | Converts text into TF-IDF features      |
| `calibrated_svm.joblib`    | Trained calibrated SVM classifier       |
| `response_database.joblib` | Stores intent-response mappings         |
| `threshold_config.joblib`  | Stores confidence and margin thresholds |

These files allow the trained components to be reused without retraining the entire pipeline.




## ⚙️ Installation

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Move into the project directory:

```bash
cd IntelliChat-AI
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

Open the Jupyter Notebook:

```text
ai-chatbot.ipynb
```

Run the notebook cells sequentially.

Before running the notebook, make sure the dataset is available at:

```text
"/kaggle/input/datasets/bitext/bitext-gen-ai-chatbot-customer-support-dataset/Bitext_Sample_Customer_Support_Training_Dataset_27K_responses-v11.csv"
```

---

## 📦 Requirements

The main libraries used in this project are:

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
joblib
```

Install them using:

```bash
pip install -r requirements.txt
```

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **Matplotlib**
* **Seaborn**
* **Joblib**
* **Jupyter Notebook**
* **Natural Language Processing**
* **Machine Learning**

---

## 🔮 Future Improvements

The project can be extended with:

* Transformer-based NLP models
* BERT-based intent classification
* FastAPI REST API
* React-based web interface
* Real-time chat interface
* Conversation history
* Database integration
* User authentication
* Docker containerization
* Cloud deployment
* Model monitoring and logging

---

## 🎯 Project Goal

The goal of IntelliChat AI is to demonstrate how traditional machine learning and NLP techniques can be combined to build a practical customer-support chatbot capable of:

```text
Understanding → Classifying → Validating → Responding
```

The project emphasizes not only model accuracy but also **prediction confidence, unsupported-query handling, model evaluation, and deployment-ready artifact management**.

---

## 👨‍💻 Project

**IntelliChat AI — NLP-Based Intelligent Customer Support Chatbot**

Built as a Machine Learning and NLP portfolio project demonstrating an end-to-end intent classification and chatbot pipeline.

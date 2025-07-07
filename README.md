# phishing-detection-albert  
Detecting phishing emails using transformer-based ALBERT embeddings and deep learning models.

# 🧠 Phishing Detection with ALBERT: Embedding-Powered Deep Learning

## 📌 Project Overview  
Phishing remains a major threat in the cybersecurity landscape. This project leverages **ALBERT (A Lite BERT)** embeddings to build high-performing phishing classifiers. By extracting semantic features from email content using pretrained transformer embeddings, we train deep neural networks such as RNN-LSTM and stacked LSTM to effectively detect phishing attacks with high accuracy.

The pipeline combines classical NLP cleaning with modern transformer embedding techniques and sequential deep learning architectures.

---

## 📂 Dataset & Source

- **Datasets**:
  - `set1.csv` –  [Traditional phishing dataset](https://www.kaggle.com/datasets/subhajournal/phishingemails)
  - `set2.csv` – [Evaluation dataset](https://www.kaggle.com/datasets/naserabdullahalam/phishing-email-dataset/data?select=CEAS_08.csv)
  - `set3.csv` – [CEAS phishing challenge data](https://www.kaggle.com/datasets/naserabdullahalam/phishing-email-dataset/data?select=phishing_email.csv)

- **Combined Format (Preprocessed)**:

  ```csv
  Text,label
  "Update your credentials to avoid account suspension",1
  "Your flight itinerary for this week",0


---

## 🔍 Insights & Findings

- ✂️ Preprocessing removed punctuation and digits to reduce text noise
- 🔡 ALBERT tokenizer handled truncation and padding (max length: 128 tokens)
- 🧠 Embeddings were extracted from the [CLS] token for 768-dimensional vectors
- 📦 Efficient batch embedding was done using TensorFlow datasets
- 📊 RNN-LSTM and Stacked LSTM outperformed other models

| Model                  | Accuracy (Est.) |
|------------------------|-----------------|
| ANN                    | ~97.62%         |
| RNN                    | ~93.30%         |
| CNN                    | ~98.40%         |
| ANN-LSTM               | ~98.02%         |
| CNN-LSTM               | ~96.81%         |
| RNN-LSTM               | ~92.11%         |
| Stacked-LSTM           | ~49.90%         |

---

## 🤖 AI Pipeline Summary

| Stage                | Description                                          |
| -------------------- | ---------------------------------------------------- |
| Preprocessing        | Lowercasing, regex cleaning, digit removal           |
| Embedding Extraction | ALBERT `[CLS]` token, using batched TF inputs        |
| Model Input          | 768-dimensional embedding vectors                    |
| Classification       | Binary label: phishing (1) or legitimate (0)         |
| Evaluation           | Accuracy, F1-score, confusion matrix, visualizations |


---

## 📈 Visualizations (Notebook Output)

- 📉 Training vs Validation Loss
- 📊 Training vs Validation Accuracy
- 📊 Confusion Matrix (per model)
- 📋 Metrics report (Accuracy, Precision, Recall, F1-score)

---

## 🛠️ Models Implemented

- **ANN** — Fully connected dense layers with dropout  
- **CNN** — 1D convolutional layers with flattening  
- **RNN-LSTM** — SimpleRNN stacked with LSTM  
- **ANN-LSTM** — Dense → reshape → LSTM  
- **CNN-LSTM** — Conv1D → LSTM  
- **Stacked LSTM** — Deep 3-layer LSTM with dropout  

**Training Configuration:**

- **Loss**: `binary_crossentropy`  
- **Optimizer**: `adam`  
- **Epochs**: `30`  
- **Batch Size**: `64`  
- **EarlyStopping**: `patience = 3`  


---

## 📁 Project Structure
```
phishing-detection-albert/
├── phishing-detection-albert.ipynb
├── README.md
├── LICENSE
└── result/
```
---

## 🛡️ License

This project is licensed under the [MIT License](./LICENSE).

---

## 👤 Author

**Johristein**  
GitHub: Johristein

---

> 📦 This project demonstrates how hybrid AI systems can be applied to detect phishing content using structured text classification — suitable for research, education, and deployment in security systems.
